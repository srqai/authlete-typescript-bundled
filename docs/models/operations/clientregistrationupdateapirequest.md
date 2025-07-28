# ClientRegistrationUpdateApiRequest

## Example Usage

```typescript
import { ClientRegistrationUpdateApiRequest } from "authelete-bundled/models/operations";

let value: ClientRegistrationUpdateApiRequest = {
  serviceId: "<id>",
  requestBody: {
    clientId: "<id>",
    token: "<value>",
    json: "{key: 1707899379638283, key1: null, key2: \"<value>\"}",
  },
};
```

## Fields

| Field                                                                                                                  | Type                                                                                                                   | Required                                                                                                               | Description                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                                            | *string*                                                                                                               | :heavy_check_mark:                                                                                                     | A service ID.                                                                                                          |
| `requestBody`                                                                                                          | [operations.ClientRegistrationUpdateApiRequestBody](../../models/operations/clientregistrationupdateapirequestbody.md) | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |