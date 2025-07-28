# AuthTokenApiFormRequest

## Example Usage

```typescript
import { AuthTokenApiFormRequest } from "authelete-bundled/models/operations";

let value: AuthTokenApiFormRequest = {
  serviceId: "<id>",
  requestBody: {
    clientLocked: false,
  },
};
```

## Fields

| Field                                                                                            | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `serviceId`                                                                                      | *string*                                                                                         | :heavy_check_mark:                                                                               | A service ID.                                                                                    |
| `requestBody`                                                                                    | [operations.AuthTokenApiFormRequestBody](../../models/operations/authtokenapiformrequestbody.md) | :heavy_check_mark:                                                                               | N/A                                                                                              |