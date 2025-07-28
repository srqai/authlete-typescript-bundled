# HskGetListApiResponse

## Example Usage

```typescript
import { HskGetListApiResponse } from "authelete-bundled/models/operations";

let value: HskGetListApiResponse = {};
```

## Fields

| Field                                                                            | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `resultCode`                                                                     | *string*                                                                         | :heavy_minus_sign:                                                               | The code which represents the result of the API call.                            |
| `resultMessage`                                                                  | *string*                                                                         | :heavy_minus_sign:                                                               | A short message which explains the result of the API call.                       |
| `action`                                                                         | [operations.HskGetListApiAction](../../models/operations/hskgetlistapiaction.md) | :heavy_minus_sign:                                                               | Result of the API call                                                           |
| `hsks`                                                                           | [operations.HskGetListApiHsk](../../models/operations/hskgetlistapihsk.md)[]     | :heavy_minus_sign:                                                               | List of HSK                                                                      |