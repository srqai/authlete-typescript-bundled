# AuthIntrospectionApiFormRequest

## Example Usage

```typescript
import { AuthIntrospectionApiFormRequest } from "authelete-bundled/models/operations";

let value: AuthIntrospectionApiFormRequest = {
  serviceId: "<id>",
  requestBody: {
    clientLocked: true,
  },
};
```

## Fields

| Field                                                                                                            | Type                                                                                                             | Required                                                                                                         | Description                                                                                                      |
| ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                                      | *string*                                                                                                         | :heavy_check_mark:                                                                                               | A service ID.                                                                                                    |
| `requestBody`                                                                                                    | [operations.AuthIntrospectionApiFormRequestBody](../../models/operations/authintrospectionapiformrequestbody.md) | :heavy_check_mark:                                                                                               | N/A                                                                                                              |