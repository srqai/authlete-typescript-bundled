# DeviceVerificationApiFormRequest

## Example Usage

```typescript
import { DeviceVerificationApiFormRequest } from "authelete-bundled/models/operations";

let value: DeviceVerificationApiFormRequest = {
  serviceId: "<id>",
  requestBody: {
    clientLocked: true,
  },
};
```

## Fields

| Field                                                                                                              | Type                                                                                                               | Required                                                                                                           | Description                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| `serviceId`                                                                                                        | *string*                                                                                                           | :heavy_check_mark:                                                                                                 | A service ID.                                                                                                      |
| `requestBody`                                                                                                      | [operations.DeviceVerificationApiFormRequestBody](../../models/operations/deviceverificationapiformrequestbody.md) | :heavy_check_mark:                                                                                                 | N/A                                                                                                                |