# DeviceCompleteApiRequest

## Example Usage

```typescript
import { DeviceCompleteApiRequest } from "authelete-bundled/models/operations";

let value: DeviceCompleteApiRequest = {
  serviceId: "<id>",
  requestBody: {
    userCode: "<value>",
    result: "AUTHORIZED",
    subject: "<value>",
  },
};
```

## Fields

| Field                                                                                              | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                        | *string*                                                                                           | :heavy_check_mark:                                                                                 | A service ID.                                                                                      |
| `requestBody`                                                                                      | [operations.DeviceCompleteApiRequestBody](../../models/operations/devicecompleteapirequestbody.md) | :heavy_check_mark:                                                                                 | N/A                                                                                                |