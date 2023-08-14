# Bulk User Import Endpoints

This endpoint facilitates bulk user import. It allows you to add a payload with more than one user per request.

### Workflow for importing users through the REST API

1. Create a new import operation with [`import.new`](new.md)
2. Add users to the operation with [`import.addusers`](add-users.md)
3. Trigger the import process with [`import.run`](run.md)
4. Check the state of the import process with [`import.status`](status.md)

| Url                       | Short Description                                                                       | Details Page         |
| ------------------------- | --------------------------------------------------------------------------------------- | -------------------- |
| `/api/v1/import.addUsers` | Adds user data to the import staging area.                                              | [Link](add-users.md) |
| `/api/v1/import.clear`    | Abort any import operation currently in progress                                        | [Link](clear.md)     |
| `/api/v1/import.run`      | Process the data from the current import operation and create  the users on Rocket.Chat | [Link](run.md)       |
| `/api/v1/import.new`      | Creates a new import operation.                                                         | [Link](new.md)       |
| `/api/v1/import.status`   | Get the status of the current import operation                                          | [Link](status.md)    |
