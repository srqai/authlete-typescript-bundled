# ClientRegistrationUpdateApiFormRequest

## Example Usage

```typescript
import { ClientRegistrationUpdateApiFormRequest } from "authelete-bundled/models/operations";

let value: ClientRegistrationUpdateApiFormRequest = {
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
| `requestBody`                                                                                                                  | [operations.ClientRegistrationUpdateApiFormRequestBody](../../models/operations/clientregistrationupdateapiformrequestbody.md) | :heavy_check_mark:                                                                                                             | N/A                                                                                                                            |