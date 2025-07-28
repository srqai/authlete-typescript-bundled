# ClientUpdateApiRequest

## Example Usage

```typescript
import { ClientUpdateApiRequest } from "authelete-bundled/models/operations";

let value: ClientUpdateApiRequest = {
  serviceId: "<id>",
  clientId: "<id>",
};
```

## Fields

| Field                                                                                          | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                    | *string*                                                                                       | :heavy_check_mark:                                                                             | A service ID.                                                                                  |
| `clientId`                                                                                     | *string*                                                                                       | :heavy_check_mark:                                                                             | A client ID.                                                                                   |
| `requestBody`                                                                                  | [operations.ClientUpdateApiRequestBody](../../models/operations/clientupdateapirequestbody.md) | :heavy_minus_sign:                                                                             | N/A                                                                                            |