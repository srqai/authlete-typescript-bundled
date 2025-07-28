# DeviceCompleteApiFormRequest

## Example Usage

```typescript
import { DeviceCompleteApiFormRequest } from "authelete-bundled/models/operations";

let value: DeviceCompleteApiFormRequest = {
  serviceId: "<id>",
  requestBody: {
    clientLocked: false,
  },
};
```

## Fields

| Field                                                                                                      | Type                                                                                                       | Required                                                                                                   | Description                                                                                                |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                                | *string*                                                                                                   | :heavy_check_mark:                                                                                         | A service ID.                                                                                              |
| `requestBody`                                                                                              | [operations.DeviceCompleteApiFormRequestBody](../../models/operations/devicecompleteapiformrequestbody.md) | :heavy_check_mark:                                                                                         | N/A                                                                                                        |