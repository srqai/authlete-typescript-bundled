# AuthTokenCreateApiFormRequest

## Example Usage

```typescript
import { AuthTokenCreateApiFormRequest } from "authelete-bundled/models/operations";

let value: AuthTokenCreateApiFormRequest = {
  serviceId: "<id>",
  requestBody: {
    clientLocked: true,
  },
};
```

## Fields

| Field                                                                                                        | Type                                                                                                         | Required                                                                                                     | Description                                                                                                  |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| `serviceId`                                                                                                  | *string*                                                                                                     | :heavy_check_mark:                                                                                           | A service ID.                                                                                                |
| `requestBody`                                                                                                | [operations.AuthTokenCreateApiFormRequestBody](../../models/operations/authtokencreateapiformrequestbody.md) | :heavy_check_mark:                                                                                           | N/A                                                                                                          |