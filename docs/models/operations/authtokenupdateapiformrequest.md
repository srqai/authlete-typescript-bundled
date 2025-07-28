# AuthTokenUpdateApiFormRequest

## Example Usage

```typescript
import { AuthTokenUpdateApiFormRequest } from "authelete-bundled/models/operations";

let value: AuthTokenUpdateApiFormRequest = {
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
| `requestBody`                                                                                                | [operations.AuthTokenUpdateApiFormRequestBody](../../models/operations/authtokenupdateapiformrequestbody.md) | :heavy_check_mark:                                                                                           | N/A                                                                                                          |