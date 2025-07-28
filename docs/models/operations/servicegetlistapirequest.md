# ServiceGetListApiRequest

## Example Usage

```typescript
import { ServiceGetListApiRequest } from "authelete-bundled/models/operations";

let value: ServiceGetListApiRequest = {};
```

## Fields

| Field                                                                                             | Type                                                                                              | Required                                                                                          | Description                                                                                       |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| `start`                                                                                           | *number*                                                                                          | :heavy_minus_sign:                                                                                | Start index (inclusive) of the result set. The default value is 0. Must not be a negative number. |
| `end`                                                                                             | *number*                                                                                          | :heavy_minus_sign:                                                                                | End index (exclusive) of the result set. The default value is 5. Must not be a negative number.   |