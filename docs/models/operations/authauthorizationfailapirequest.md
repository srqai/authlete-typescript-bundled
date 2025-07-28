# AuthAuthorizationFailApiRequest

## Example Usage

```typescript
import { AuthAuthorizationFailApiRequest } from "authelete-bundled/models/operations";

let value: AuthAuthorizationFailApiRequest = {
  serviceId: "<id>",
  requestBody: {
    ticket: "<value>",
    reason: "CONSENT_REQUIRED",
  },
};
```

## Fields

| Field                                                                                                            | Type                                                                                                             | Required                                                                                                         | Description                                                                                                      |
| ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                                      | *string*                                                                                                         | :heavy_check_mark:                                                                                               | A service ID.                                                                                                    |
| `requestBody`                                                                                                    | [operations.AuthAuthorizationFailApiRequestBody](../../models/operations/authauthorizationfailapirequestbody.md) | :heavy_check_mark:                                                                                               | N/A                                                                                                              |