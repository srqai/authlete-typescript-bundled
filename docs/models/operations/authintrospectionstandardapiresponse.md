# AuthIntrospectionStandardApiResponse

## Example Usage

```typescript
import { AuthIntrospectionStandardApiResponse } from "authelete-bundled/models/operations";

let value: AuthIntrospectionStandardApiResponse = {};
```

## Fields

| Field                                                                                                          | Type                                                                                                           | Required                                                                                                       | Description                                                                                                    |
| -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `resultCode`                                                                                                   | *string*                                                                                                       | :heavy_minus_sign:                                                                                             | The code which represents the result of the API call.                                                          |
| `resultMessage`                                                                                                | *string*                                                                                                       | :heavy_minus_sign:                                                                                             | A short message which explains the result of the API call.                                                     |
| `action`                                                                                                       | [operations.AuthIntrospectionStandardApiAction](../../models/operations/authintrospectionstandardapiaction.md) | :heavy_minus_sign:                                                                                             | The next action that the authorization server implementation should take.                                      |
| `responseContent`                                                                                              | *string*                                                                                                       | :heavy_minus_sign:                                                                                             | The content that the authorization server implementation is to return to the client<br/>application.<br/>      |