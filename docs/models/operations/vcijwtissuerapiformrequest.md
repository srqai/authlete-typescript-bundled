# VciJwtissuerApiFormRequest

## Example Usage

```typescript
import { VciJwtissuerApiFormRequest } from "authelete-bundled/models/operations";

let value: VciJwtissuerApiFormRequest = {
  serviceId: "<id>",
  requestBody: {
    clientLocked: false,
  },
};
```

## Fields

| Field                                                                                                  | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `serviceId`                                                                                            | *string*                                                                                               | :heavy_check_mark:                                                                                     | A service ID.                                                                                          |
| `requestBody`                                                                                          | [operations.VciJwtissuerApiFormRequestBody](../../models/operations/vcijwtissuerapiformrequestbody.md) | :heavy_check_mark:                                                                                     | N/A                                                                                                    |