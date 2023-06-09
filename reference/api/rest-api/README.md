# REST API

Welcome to the Rocket.Chat REST API documentation! This guide provides all the information you need to understand and use the REST API endpoints in Rocket.Chat. It allows you to interact with the Rocket.Chat server using code, enabling you to automate tasks and integrate Rocket.Chat with other systems.  It also allows you to control and extend Rocket.Chat with ease.

The API is designed to follow the principles of [**Representational State Transfer (REST)**](https://en.wikipedia.org/wiki/Representational\_state\_transfer). It uses standard HTTP methods like **GET**, **POST**, **PUT**, and **DELETE** to perform operations on different resources.

## Production Security Concerns

Using HTTPS with a valid SSL certificate when accessing the production server is vital to guarantee a secure connection with the Rocket.Chat REST API. It encrypts the communication and protects sensitive information. During [authentication](endpoints/other-important-endpoints/authentication-endpoints/), always use the[ login API](endpoints/other-important-endpoints/authentication-endpoints/login.md) over HTTPS to keep usernames and passwords confidential during transmission.

Additionally, implement a strategy to regularly expire and refresh authorization tokens, reducing the risk of unauthorized access. Finally, configure user permissions carefully, granting only the necessary access rights for specific API operations to prevent unauthorized actions or data leakage.

## Rate Limiting

Rate limiting is a vital mechanism implemented in the Rocket.Chat API to manage and control the rate at which API requests can be made. It helps maintain server stability, prevent abuse, and ensure fair usage among different API consumers. The rate limiter is enabled for all endpoints by default.

To enable Rate Limiter,&#x20;

* Navigate to **Administration > Workspace > Settings > Rate Limiter > API Rate Limiter**.
* Update the settings according to your needs:
  * **Enable Rate Limiter**
  * **Enable Rate Limiter in Development Mode**
  * **Default number calls to the rate limiter:** Number of default calls for each endpoint, allowed within the time range defined.
  * **Default time limit for the rate limiter (in ms):** Default timeout to limit the number of calls at each endpoint (in milliseconds).
* Click **Save Changes.**

To disable the rate limiter, assign the `api-bypass-rate-limit` [permission ](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions)for your user group role.

To modify or disable the rate limiter for an API endpoint in your code, you can use the `.addRoute` function and provide the desired configuration within the existing options object. By setting the `rateLimiterOptions` property to `false`, you can disable the rate limiter for that specific endpoint. Alternatively, you can specify a valid configuration object in the format `{numRequestsAllowed: 10, intervalTimeInMS: 60000}` to adjust the number of allowed requests and the interval time for the rate limiter.

When making requests to an API endpoint with a rate limiter, the response headers will include three additional properties:

* `x-ratelimit-limit`: This indicates the number of calls allowed within a specific period.
* `x-ratelimit-remaining`: It represents the number of remaining requests that can be made within the current rate limit window.
* `x-ratelimit-reset`: This specifies the time in [UTC epoch milliseconds](https://en.wikipedia.org/wiki/Unix\_time) when the current rate limit window will reset.

These properties provide information about the rate limit constraints and help you track the usage and availability of the API calls within the defined limits.

{% hint style="info" %}
Specific endpoints, such as `/api/v1/users.updateOwnBasicInfo`, may trigger the rate limiter and currently cannot be customized or disabled through the administration panel.
{% endhint %}

## Access Tokens

To utilize the Rocket.Chat REST API without signing in, you can use personal access tokens. However, the administrator must grant your user role the `create-personal-access-tokens` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).

To generate personal access tokens, see[ **Personal Access Tokens** user guide](https://docs.rocket.chat/use-rocket.chat/user-guides/user-panel/my-account#personal-access-tokens). It's important to note that the generated tokens are irrecoverable, so storing them safely is essential. If a token is lost or forgotten, it can be regenerated or deleted.&#x20;

{% hint style="info" %}
When making calls to the API, include the generated token in the `X-Auth-Token` header and your user ID in the `X-User-Id` header to authenticate the requests.
{% endhint %}

## Pagination

Starting from version `0.49`, specific endpoints in the Rocket.Chat API support query parameters such as **offset**, **count**, and **sort**. However, the default values for these parameters can vary depending on the server's configuration settings.

### Query Parameter Information

| Parameter | Example                   | Description                                                                                                   | Format                                                                                                          |
| --------- | ------------------------- | ------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| `offset`  | `50`                      | Number of items to "skip" in the query, i.e. requests return `count` items, skipping the first `offset` items | Positive integer                                                                                                |
| `count`   | `50`                      | How many items to return.                                                                                     | Integer                                                                                                         |
| `sort`    | `{"value": -1, "_id": 1}` | List of fields to order by, and in which direction                                                            | JSON object, with properties listed in desired order, with values of `1` for ascending, or `-1` for descending. |

### Settings

To modify the offset and count behavior, you can access the **REST API** settings in **Administration > Workspace > Settings > General > REST API.**

* **Default Count**: The default count for REST API results if the count parameter is not provided.
* **Max Record Amount**: The maximum limit for the count parameter. If a higher count is specified, this limit will be applied.
* **Allow Getting Everything**: This setting determines whether passing `0` as the count parameter is allowed to retrieve all records.

This feature provides flexibility in controlling the number of results, pagination, and sorting in the Rocket.Chat API.

### Sample Use Case

To retrieve a specific page of results with five items per page, use the `count=5` and `offset=10` parameters in the API request.&#x20;

```
http://localhost:3000/api/v1/channels.list?count=5&offset=10
```

To sort the results by `name` in descending order and `status` in ascending order,  use the sort parameter with the appropriate JSON syntax.

```
 http://localhost:3000/api/v1/users.list?sort={"name":-1,"status":1}
```

## Query and Fields

Starting from version `0.49`, some endpoints in the Rocket.Chat API support query parameters called "query" and "fields". These parameters accept JSON objects, but the request will fail if an invalid JSON object is provided.

### Query Parameters

* "**query**": This parameter allows you to use [MongoDB](https://docs.mongodb.com/manual/reference/operator/query/) query operators to search for specific data. For example, to query users with a name that contains the letter "g":

```
https://localhost:3000/api/v1/users.list?query={ "name": { "$regex": "g" } } 
```

* "**fields**": This parameter accepts a JSON object with properties that have a value of 1 or 0 to include or exclude them in the response. For example, to only retrieve the usernames of users:&#x20;

```
http://localhost:3000/api/v1/users.list?fields={ "username": 1 }
```

It's important to note that the query parameter follows the [EJSON](https://docs.meteor.com/api/ejson.html) structure, similar to JSON, but with some differences in handling date and binary fields.&#x20;

For queries involving date fields, you can use the following examples:

```
query={"_updatedAt": {"$gt": { "$date": 1542814057 } }}
```

```
 query={"_updatedAt":{"$gt":{"$date":"2018-11-21T15:27:28.202Z"}}}
```

{% hint style="info" %}
If you provide a field value of `{"_id": false, "value": false}`, you can retrieve all other fields except for `_id` and `value`.
{% endhint %}

These query and field parameters enhance the flexibility and precision of data retrieval in the Rocket.Chat API.

## Language-specific wrappers

{% hint style="warning" %}
Rocket.Chat is not the maintainer of these wrappers. They are owned and supported by community members.
{% endhint %}

| Language | Wrapper                                                                                                                                                  |
| -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Java     | [rocket-chat-rest-client](https://github.com/baloise/rocket-chat-rest-client)                                                                            |
| PHP      | [rocketchat-php](https://github.com/alekseykuleshov/rocket-chat)                                                                                         |
| Python   | <p><a href="https://github.com/jadolg/rocketchat_API">rocketchat_API</a></p><p><a href="https://github.com/Pipoline/rocket-python">rocket-python</a></p> |
| Ruby     | [rocketchat-ruby](https://github.com/abrom/rocketchat-ruby)                                                                                              |
| Clojure  | [rocketchat-clojure](https://github.com/MalloZup/missile)                                                                                                |
| Golang   | [rocketchat-golang](https://github.com/badkaktus/gorocket)                                                                                               |

{% hint style="info" %}
As an end-user, you can submit a [New Feature Request](https://forums.rocket.chat/c/feature-requests/8) to request new APIs in Rocket.Chat. Additionally, you can consider [donating](zhttps://www.paypal.com/donate/?cmd=\_s-xclick\&hosted\_button\_id=ZL94ZE6LGVUSN\&ssrt=1686298281408) to support the project.
{% endhint %}
