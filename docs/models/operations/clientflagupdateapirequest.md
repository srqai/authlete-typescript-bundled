# ClientFlagUpdateApiRequest

## Example Usage

```typescript
import { ClientFlagUpdateApiRequest } from "authelete-bundled/models/operations";

let value: ClientFlagUpdateApiRequest = {
  serviceId: "<id>",
  clientIdentifier: "<value>",
};
```

## Fields

| Field                                                                                                  | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `serviceId`                                                                                            | *string*                                                                                               | :heavy_check_mark:                                                                                     | A service ID.                                                                                          |
| `clientIdentifier`                                                                                     | *string*                                                                                               | :heavy_check_mark:                                                                                     | A client ID.                                                                                           |
| `requestBody`                                                                                          | [operations.ClientFlagUpdateApiRequestBody](../../models/operations/clientflagupdateapirequestbody.md) | :heavy_minus_sign:                                                                                     | N/A                                                                                                    |