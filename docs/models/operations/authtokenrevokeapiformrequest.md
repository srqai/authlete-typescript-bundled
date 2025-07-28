# AuthTokenRevokeApiFormRequest

## Example Usage

```typescript
import { AuthTokenRevokeApiFormRequest } from "authelete-bundled/models/operations";

let value: AuthTokenRevokeApiFormRequest = {
  serviceId: "<id>",
  requestBody: {
    clientLocked: false,
  },
};
```

## Fields

| Field                                                                                                        | Type                                                                                                         | Required                                                                                                     | Description                                                                                                  |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| `serviceId`                                                                                                  | *string*                                                                                                     | :heavy_check_mark:                                                                                           | A service ID.                                                                                                |
| `requestBody`                                                                                                | [operations.AuthTokenRevokeApiFormRequestBody](../../models/operations/authtokenrevokeapiformrequestbody.md) | :heavy_check_mark:                                                                                           | N/A                                                                                                          |