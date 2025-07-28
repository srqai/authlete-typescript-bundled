# DeviceCompleteApiResponse

## Example Usage

```typescript
import { DeviceCompleteApiResponse } from "authelete-bundled/models/operations";

let value: DeviceCompleteApiResponse = {};
```

## Fields

| Field                                                                                    | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `resultCode`                                                                             | *string*                                                                                 | :heavy_minus_sign:                                                                       | The code which represents the result of the API call.                                    |
| `resultMessage`                                                                          | *string*                                                                                 | :heavy_minus_sign:                                                                       | A short message which explains the result of the API call.                               |
| `action`                                                                                 | [operations.DeviceCompleteApiAction](../../models/operations/devicecompleteapiaction.md) | :heavy_minus_sign:                                                                       | The next action that the authorization server implementation should take.<br/>           |