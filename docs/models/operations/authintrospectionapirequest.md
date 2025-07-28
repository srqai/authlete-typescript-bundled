# AuthIntrospectionApiRequest

## Example Usage

```typescript
import { AuthIntrospectionApiRequest } from "authelete-bundled/models/operations";

let value: AuthIntrospectionApiRequest = {
  serviceId: "<id>",
  requestBody: {
    token: "<value>",
  },
};
```

## Fields

| Field                                                                                                    | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                              | *string*                                                                                                 | :heavy_check_mark:                                                                                       | A service ID.                                                                                            |
| `requestBody`                                                                                            | [operations.AuthIntrospectionApiRequestBody](../../models/operations/authintrospectionapirequestbody.md) | :heavy_check_mark:                                                                                       | N/A                                                                                                      |