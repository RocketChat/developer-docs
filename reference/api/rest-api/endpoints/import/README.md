# Import

## Workflow for importing users through the Rest API:

1. Create a new import operation with `import.new`
2. Add users to the operation with `import.addusers`
3. Trigger the import process with `import.run`
4. Check the state of the import process with `import.status`