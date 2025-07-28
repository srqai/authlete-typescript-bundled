# HskCreateApiFormRequest

## Example Usage

```typescript
import { HskCreateApiFormRequest } from "authelete-bundled/models/operations";

let value: HskCreateApiFormRequest = {
  serviceId: "<id>",
  requestBody: {
    clientLocked: true,
  },
};
```

## Fields

| Field                                                                                            | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `serviceId`                                                                                      | *string*                                                                                         | :heavy_check_mark:                                                                               | A service ID.                                                                                    |
| `requestBody`                                                                                    | [operations.HskCreateApiFormRequestBody](../../models/operations/hskcreateapiformrequestbody.md) | :heavy_check_mark:                                                                               | N/A                                                                                              |