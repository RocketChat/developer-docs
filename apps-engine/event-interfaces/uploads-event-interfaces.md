# Uploads - Event Interfaces

The table below contains all of the upload-related events, as well as the purpose of each event. If you want to execute actions based on upload events, you may use any of the events mentioned below as an event interface.&#x20;

<table><thead><tr><th width="265.5">Interface</th><th>Purpose</th></tr></thead><tbody><tr><td><code>IPreFileUpload</code></td><td><p>Event interface that allows an app to register as a handler of the `IPreFileUpload` event. This event is triggered prior to an upload successfully</p><p>being saved to the database, but *after* all its contents have been retrieved by Rocket.Chat. To prevent the upload from completing, an app should throw a `FileUploadNotAllowedException` with a message specifying the reason for rejection.</p></td></tr></tbody></table>
