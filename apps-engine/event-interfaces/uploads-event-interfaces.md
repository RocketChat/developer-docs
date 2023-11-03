# Uploads - Event Interfaces

The table below contains the upload-related events, as well as the purpose of each event. If you want to execute actions based on upload events, you can use any of the events mentioned below as an event interface.&#x20;

<table><thead><tr><th width="238.5">Interface</th><th>Description</th></tr></thead><tbody><tr><td><code>IPreFileUpload</code></td><td><p>Event interface that allows an app to register as a handler of the <code>IPreFileUpload</code> event. </p><p></p><p>This event is triggered prior to an upload successfully being saved to the database, but only after all its contents have been retrieved by Rocket.Chat. To prevent the upload from completing, an app should throw a <code>FileUploadNotAllowedException</code> with a message specifying the reason for rejection.</p></td></tr></tbody></table>
