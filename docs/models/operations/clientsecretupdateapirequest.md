# ClientSecretUpdateApiRequest

## Example Usage

```typescript
import { ClientSecretUpdateApiRequest } from "authelete-bundled/models/operations";

let value: ClientSecretUpdateApiRequest = {
  serviceId: "<id>",
  clientIdentifier: "<value>",
  requestBody: {
    clientSecret: "<value>",
  },
};
```

## Fields

| Field                                                                                                      | Type                                                                                                       | Required                                                                                                   | Description                                                                                                |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                                | *string*                                                                                                   | :heavy_check_mark:                                                                                         | A service ID.                                                                                              |
| `clientIdentifier`                                                                                         | *string*                                                                                                   | :heavy_check_mark:                                                                                         | The client ID or the client ID alias of a client.<br/>                                                     |
| `requestBody`                                                                                              | [operations.ClientSecretUpdateApiRequestBody](../../models/operations/clientsecretupdateapirequestbody.md) | :heavy_check_mark:                                                                                         | N/A                                                                                                        |