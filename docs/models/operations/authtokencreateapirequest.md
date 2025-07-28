# AuthTokenCreateApiRequest

## Example Usage

```typescript
import { AuthTokenCreateApiRequest } from "authelete-bundled/models/operations";

let value: AuthTokenCreateApiRequest = {
  serviceId: "<id>",
  requestBody: {
    grantType: "DEVICE_CODE",
    clientId: 622368,
  },
};
```

## Fields

| Field                                                                                                | Type                                                                                                 | Required                                                                                             | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                          | *string*                                                                                             | :heavy_check_mark:                                                                                   | A service ID.                                                                                        |
| `requestBody`                                                                                        | [operations.AuthTokenCreateApiRequestBody](../../models/operations/authtokencreateapirequestbody.md) | :heavy_check_mark:                                                                                   | N/A                                                                                                  |