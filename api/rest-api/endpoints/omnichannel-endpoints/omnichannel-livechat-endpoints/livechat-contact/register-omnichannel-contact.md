---
description: Registers a guest user as a new omnichannel contact.
---

# Register Omnichannel Contact

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/omnichannel/contact` | `YES` | `PUT` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Parameters

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Example</th>
      <th style="text-align:left">Required</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>&lt;code&gt;&lt;/code&gt;</p>
        <p><code>_Id</code>
        </p>
      </td>
      <td style="text-align:left"><code>7ipCD6NDtkkRDCiNM</code>
      </td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Contact ID</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>token</code>
      </td>
      <td style="text-align:left"><code>4WcmeBE4spXx6AxrC</code>
      </td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Contact Token</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>name</code>
      </td>
      <td style="text-align:left"><code>Chris</code>
      </td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Contact Name</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>email</code>
      </td>
      <td style="text-align:left"><code> chris@gmail.com</code>
      </td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Contact Email</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>phone</code>
      </td>
      <td style="text-align:left"><code>+93334432224444</code>
      </td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Contact Phone</td>
    </tr>
  </tbody>
</table>

## Example Call

```bash
curl --location --request PUT 'http://localhost:3000/api/v1/omnichannel/contact'\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
-d '{
"_id": "7ipCD6NDtkkRDCiNM",
"token" : "434lxd7iss8yh8c4m80wh",
"name" :  "Chris",
"email" : "chris@gmail.com",
"phone" : "+93334432224444"

 }'
```

## Result

```javascript
{
    "contact": "7ipCD6NDtkkRDCiNM",
    "success": true
}
```

