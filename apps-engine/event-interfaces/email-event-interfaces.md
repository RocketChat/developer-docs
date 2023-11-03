# Email - Event Interfaces

The table below contains the email-related events, as well as the purpose of each event. If you want to execute actions based on email events, you can use any of the events mentioned below as an event interface.

<table><thead><tr><th width="250.5">Interface</th><th>Description</th></tr></thead><tbody><tr><td><code>IPreEmailSent</code></td><td><p>The event interface allows apps to register as a handler of the <code>IPreEmailSent</code> event.</p><p></p><p>This event is triggered before the mailer sends an email.</p><p></p><p>To prevent the email from being sent, you can throw an error with a message specifying the reason for rejection.</p></td></tr></tbody></table>
