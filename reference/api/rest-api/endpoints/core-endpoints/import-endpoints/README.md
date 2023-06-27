# Import Endpoints

The import process comprises these endpoints in this sequence to import data from files:&#x20;

* &#x20;[`uploadImportFile`](upload-import-file.md)
* [`getImportFileData`](get-import-file-data.md)&#x20;
* [`startImport`](start-import.md)&#x20;

The function `uploadImportFile` receives the binary content of the imported file and additional information about its content. It then stores this data in a buffer for use in subsequent steps. Although the raw data is available at this stage, the specific contents of the file remain unknown.

During the `getImportFileData` , we extract the file's content, determine the number of records within it, and internally generate an intermediate representation of the data within the Rocket.Chat database. This involves extracting information related to users, rooms, and messages, which is then stored in the database. It allows users to choose what they wish to import in the following step.

In the `startImport` step, we receive the selected rooms and users, then import their data using the pre-prepared internal format of Rocket.Chat. Notably, the payload of `startImport` does not include messages, as they are imported automatically.

{% hint style="info" %}
Only one import operation is supported at a time. This is why there is no required `importId.`&#x20;
{% endhint %}
