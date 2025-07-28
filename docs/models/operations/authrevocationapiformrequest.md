# AuthRevocationApiFormRequest

## Example Usage

```typescript
import { AuthRevocationApiFormRequest } from "authelete-bundled/models/operations";

let value: AuthRevocationApiFormRequest = {
  serviceId: "<id>",
  requestBody: {
    clientLocked: false,
  },
};
```

## Fields

| Field                                                                                                      | Type                                                                                                       | Required                                                                                                   | Description                                                                                                |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                                | *string*                                                                                                   | :heavy_check_mark:                                                                                         | A service ID.                                                                                              |
| `requestBody`                                                                                              | [operations.AuthRevocationApiFormRequestBody](../../models/operations/authrevocationapiformrequestbody.md) | :heavy_check_mark:                                                                                         | N/A                                                                                                        |