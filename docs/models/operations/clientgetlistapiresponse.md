# ClientGetListApiResponse

## Example Usage

```typescript
import { ClientGetListApiResponse } from "authelete-bundled/models/operations";

let value: ClientGetListApiResponse = {};
```

## Fields

| Field                                                                                                                   | Type                                                                                                                    | Required                                                                                                                | Description                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `start`                                                                                                                 | *number*                                                                                                                | :heavy_minus_sign:                                                                                                      | Start index (inclusive) of the result set of the query.<br/>                                                            |
| `end`                                                                                                                   | *number*                                                                                                                | :heavy_minus_sign:                                                                                                      | End index (exclusive) of the result set of the query.<br/>                                                              |
| `totalCount`                                                                                                            | *number*                                                                                                                | :heavy_minus_sign:                                                                                                      | Total number of clients that belong to the service. This doesn't mean the number of clients<br/>contained in the response.<br/> |
| `clients`                                                                                                               | [operations.ClientGetListApiClient](../../models/operations/clientgetlistapiclient.md)[]                                | :heavy_minus_sign:                                                                                                      | An array of clients.<br/>                                                                                               |