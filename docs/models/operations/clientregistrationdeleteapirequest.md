# ClientRegistrationDeleteApiRequest

## Example Usage

```typescript
import { ClientRegistrationDeleteApiRequest } from "authelete-bundled/models/operations";

let value: ClientRegistrationDeleteApiRequest = {
  serviceId: "<id>",
  requestBody: {
    clientId: "<id>",
    token: "<value>",
  },
};
```

## Fields

| Field                                                                                                                  | Type                                                                                                                   | Required                                                                                                               | Description                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                                            | *string*                                                                                                               | :heavy_check_mark:                                                                                                     | A service ID.                                                                                                          |
| `requestBody`                                                                                                          | [operations.ClientRegistrationDeleteApiRequestBody](../../models/operations/clientregistrationdeleteapirequestbody.md) | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |