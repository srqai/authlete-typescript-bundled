# ClientSecretUpdateApiResponse

## Example Usage

```typescript
import { ClientSecretUpdateApiResponse } from "authelete-bundled/models/operations";

let value: ClientSecretUpdateApiResponse = {};
```

## Fields

| Field                                                      | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `resultCode`                                               | *string*                                                   | :heavy_minus_sign:                                         | The code which represents the result of the API call.      |
| `resultMessage`                                            | *string*                                                   | :heavy_minus_sign:                                         | A short message which explains the result of the API call. |
| `newClientSecret`                                          | *string*                                                   | :heavy_minus_sign:                                         | The new client secret.<br/>                                |
| `oldClientSecret`                                          | *string*                                                   | :heavy_minus_sign:                                         | The old client secret.<br/>                                |