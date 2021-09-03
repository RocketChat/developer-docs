# REST API

The REST API allows you to control and extend Rocket.Chat with ease.

> **This API is a work in progress, so feel free to test, ask us questions, and submit Pull Requests!**

If you are an end-user and not a dev or a tester, [create a New Feature Request](https://forums.rocket.chat/c/feature-requests) to request new APIs -- and consider [making a donation](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=ZL94ZE6LGVUSN) to the project.

> All API calls in the documentation are made using `curl`. However, you are free to use Java / Python / PHP / Golang / Ruby / Swift / Objective-C / Rust / Scala / C\# or any other programming languages.

## Production Security Concerns

When calling a production Rocket.Chat server, ensure it is running via HTTPS and has a valid SSL Certificate. The login method requires you to post your username and password in plaintext, which is why we highly suggest only calling the REST login API over HTTPS. Also, few things to note:

* Only call via HTTPS
* Implement a timed authorization token expiration strategy
* Ensure the calling user only has permissions for what they are calling and no more

### Authentication

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/login` | Authenticate with the REST API. | [Link](endpoints/team-collaboration-endpoints/others/authentication-endpoints/login.md) |
| `/api/v1/login` | Authenticate with google. | [Link](endpoints/team-collaboration-endpoints/others/authentication-endpoints/google.md) |
| `/api/v1/login` | Authenticate with facebook. | [Link](endpoints/team-collaboration-endpoints/others/authentication-endpoints/facebook.md) |
| `/api/v1/login` | Authenticate with twitter. | [Link](endpoints/team-collaboration-endpoints/others/authentication-endpoints/twitter.md) |
| `/api/v1/logout` | Invalidate your REST API authentication token. | [Link](endpoints/team-collaboration-endpoints/others/authentication-endpoints/logout.md) |
| `/api/v1/me` | Displays information about the authenticated user. | [Link](endpoints/team-collaboration-endpoints/others/authentication-endpoints/me.md) |

### Licenses

| Url | Method | Short Description | Details Page |
| :--- | :--- | :--- | :--- |
| `/api/v1/licenses.get` | `GET` | Gets all active licenses. | [Link](https://github.com/RocketChat/docs/tree/06af028aecca9430169baa3f517704a68deb6278/api/rest-api/methods/licenses/get.md) |
| `/api/v1/licenses.add` | `POST` | Adds a new license. | [Link](https://github.com/RocketChat/docs/tree/06af028aecca9430169baa3f517704a68deb6278/api/rest-api/methods/licenses/add.md) |

## Language-specific wrappers

<table>
  <thead>
    <tr>
      <th style="text-align:left">Language</th>
      <th style="text-align:left">Wrapper</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Java</td>
      <td style="text-align:left">
        <p></p>
        <p><a href="https://github.com/baloise/rocket-chat-rest-client">rocket-chat-rest-client</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">PHP</td>
      <td style="text-align:left">
        <p></p>
        <p><a href="https://github.com/alekseykuleshov/rocket-chat">rocketchat-php</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Python</td>
      <td style="text-align:left">
        <p></p>
        <p><a href="https://github.com/jadolg/rocketchat_API">rocketchat_API</a>
        </p>
        <p><a href="https://github.com/Pipoline/rocket-python">rocket-python</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Ruby</td>
      <td style="text-align:left">
        <p></p>
        <p><a href="https://github.com/abrom/rocketchat-ruby">rocketchat-ruby</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Clojure</td>
      <td style="text-align:left">
        <p></p>
        <p><a href="https://github.com/MalloZup/missile">rocketchat-clojure</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Golang</td>
      <td style="text-align:left">
        <p></p>
        <p><a href="https://github.com/badkaktus/gorocket">rocketchat-golang</a>
        </p>
      </td>
    </tr>
  </tbody>
</table>

