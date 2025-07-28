# AuthTokenUpdateApiRequest

## Example Usage

```typescript
import { AuthTokenUpdateApiRequest } from "authelete-bundled/models/operations";

let value: AuthTokenUpdateApiRequest = {
  serviceId: "<id>",
  requestBody: {
    accessToken: "<value>",
  },
};
```

## Fields

| Field                                                                                                | Type                                                                                                 | Required                                                                                             | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                          | *string*                                                                                             | :heavy_check_mark:                                                                                   | A service ID.                                                                                        |
| `requestBody`                                                                                        | [operations.AuthTokenUpdateApiRequestBody](../../models/operations/authtokenupdateapirequestbody.md) | :heavy_check_mark:                                                                                   | N/A                                                                                                  |