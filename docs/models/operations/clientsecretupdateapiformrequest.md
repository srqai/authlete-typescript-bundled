# ClientSecretUpdateApiFormRequest

## Example Usage

```typescript
import { ClientSecretUpdateApiFormRequest } from "authelete-bundled/models/operations";

let value: ClientSecretUpdateApiFormRequest = {
  serviceId: "<id>",
  clientIdentifier: "<value>",
  requestBody: {
    clientLocked: false,
  },
};
```

## Fields

| Field                                                                                                              | Type                                                                                                               | Required                                                                                                           | Description                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| `serviceId`                                                                                                        | *string*                                                                                                           | :heavy_check_mark:                                                                                                 | A service ID.                                                                                                      |
| `clientIdentifier`                                                                                                 | *string*                                                                                                           | :heavy_check_mark:                                                                                                 | The client ID or the client ID alias of a client.<br/>                                                             |
| `requestBody`                                                                                                      | [operations.ClientSecretUpdateApiFormRequestBody](../../models/operations/clientsecretupdateapiformrequestbody.md) | :heavy_check_mark:                                                                                                 | N/A                                                                                                                |