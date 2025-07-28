# BackchannelAuthenticationCompleteApiRequest

## Example Usage

```typescript
import { BackchannelAuthenticationCompleteApiRequest } from "authelete-bundled/models/operations";

let value: BackchannelAuthenticationCompleteApiRequest = {
  serviceId: "<id>",
  requestBody: {
    ticket: "<value>",
    result: "TRANSACTION_FAILED",
    subject: "<value>",
  },
};
```

## Fields

| Field                                                                                                                                    | Type                                                                                                                                     | Required                                                                                                                                 | Description                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                                                              | *string*                                                                                                                                 | :heavy_check_mark:                                                                                                                       | A service ID.                                                                                                                            |
| `requestBody`                                                                                                                            | [operations.BackchannelAuthenticationCompleteApiRequestBody](../../models/operations/backchannelauthenticationcompleteapirequestbody.md) | :heavy_check_mark:                                                                                                                       | N/A                                                                                                                                      |