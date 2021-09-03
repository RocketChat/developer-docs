# REST API

The REST API allows you to control and extend Rocket.Chat with ease.

If you are an end-user and not a dev or a tester, [create a New Feature Request](https://forums.rocket.chat/c/feature-requests) to request new APIs -- and consider [making a donation](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=ZL94ZE6LGVUSN) to the project.  


{% hint style="info" %}
All API calls in the documentation are made using curl. However, you are free to use Java / Python / PHP / Golang / Ruby / Swift / Objective-C / Rust / Scala / C\# or any other programming languages.
{% endhint %}

## Production Security Concerns

When calling a production Rocket.Chat server, ensure it is running via HTTPS and has a valid SSL Certificate. The login method requires you to post your username and password in plaintext, which is why we highly suggest only calling the REST login API over HTTPS. Also, few things to note:

* Only call via HTTPS
* Implement a timed authorization token expiration strategy
* Ensure the calling user only has permissions for what they are calling and no more

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

