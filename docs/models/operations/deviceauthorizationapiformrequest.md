# DeviceAuthorizationApiFormRequest

## Example Usage

```typescript
import { DeviceAuthorizationApiFormRequest } from "authelete-bundled/models/operations";

let value: DeviceAuthorizationApiFormRequest = {
  serviceId: "<id>",
  requestBody: {
    clientLocked: false,
  },
};
```

## Fields

| Field                                                                                                                | Type                                                                                                                 | Required                                                                                                             | Description                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                                          | *string*                                                                                                             | :heavy_check_mark:                                                                                                   | A service ID.                                                                                                        |
| `requestBody`                                                                                                        | [operations.DeviceAuthorizationApiFormRequestBody](../../models/operations/deviceauthorizationapiformrequestbody.md) | :heavy_check_mark:                                                                                                   | N/A                                                                                                                  |