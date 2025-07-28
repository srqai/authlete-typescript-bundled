# ClientRegistrationDeleteApiFormRequest

## Example Usage

```typescript
import { ClientRegistrationDeleteApiFormRequest } from "authelete-bundled/models/operations";

let value: ClientRegistrationDeleteApiFormRequest = {
  serviceId: "<id>",
  requestBody: {
    clientLocked: false,
  },
};
```

## Fields

| Field                                                                                                                          | Type                                                                                                                           | Required                                                                                                                       | Description                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ |
| `serviceId`                                                                                                                    | *string*                                                                                                                       | :heavy_check_mark:                                                                                                             | A service ID.                                                                                                                  |
| `requestBody`                                                                                                                  | [operations.ClientRegistrationDeleteApiFormRequestBody](../../models/operations/clientregistrationdeleteapiformrequestbody.md) | :heavy_check_mark:                                                                                                             | N/A                                                                                                                            |