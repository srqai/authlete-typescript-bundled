# ClientRegistrationGetApiRequest

## Example Usage

```typescript
import { ClientRegistrationGetApiRequest } from "authelete-bundled/models/operations";

let value: ClientRegistrationGetApiRequest = {
  serviceId: "<id>",
  requestBody: {
    clientLocked: false,
  },
};
```

## Fields

| Field                                                                                                            | Type                                                                                                             | Required                                                                                                         | Description                                                                                                      |
| ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                                      | *string*                                                                                                         | :heavy_check_mark:                                                                                               | A service ID.                                                                                                    |
| `requestBody`                                                                                                    | [operations.ClientRegistrationGetApiRequestBody](../../models/operations/clientregistrationgetapirequestbody.md) | :heavy_check_mark:                                                                                               | N/A                                                                                                              |