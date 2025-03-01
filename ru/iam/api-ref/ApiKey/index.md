---
editable: false
sourcePath: en/_api-ref/iam/api-ref/ApiKey/index.md
---

# Identity and Access Management API, REST: ApiKey methods
A set of methods for managing API keys.
## JSON Representation {#representation}
```json 
{
  "id": "string",
  "serviceAccountId": "string",
  "createdAt": "string",
  "description": "string"
}
```
 
Field | Description
--- | ---
id | **string**<br><p>ID of the API Key.</p> 
serviceAccountId | **string**<br><p>ID of the service account that the API key belongs to.</p> 
createdAt | **string** (date-time)<br><p>Creation timestamp.</p> <p>String in <a href="https://www.ietf.org/rfc/rfc3339.txt">RFC3339</a> text format. The range of possible values is from ``0001-01-01T00:00:00Z`` to ``9999-12-31T23:59:59.999999999Z``, i.e. from 0 to 9 digits for fractions of a second.</p> <p>To work with values in this field, use the APIs described in the <a href="https://developers.google.com/protocol-buffers/docs/reference/overview">Protocol Buffers reference</a>. In some languages, built-in datetime utilities do not support nanosecond precision (9 digits).</p> 
description | **string**<br><p>Description of the API key. 0-256 characters long.</p> 

## Methods {#methods}
Method | Description
--- | ---
[create](create.md) | Creates an API key for the specified service account.
[delete](delete.md) | Deletes the specified API key.
[get](get.md) | Returns the specified API key.
[list](list.md) | Retrieves the list of API keys for the specified service account.
[listOperations](listOperations.md) | Retrieves the list of operations for the specified API key.
[update](update.md) | Updates the specified API key.