# DeviceAuthorizationApiGrantAuthorizationDetails

The authorization details. This represents the value of the `authorization_details`
request parameter in the preceding device authorization request which is defined in
"OAuth 2.0 Rich Authorization Requests".


## Example Usage

```typescript
import { DeviceAuthorizationApiGrantAuthorizationDetails } from "authelete-bundled/models/operations";

let value: DeviceAuthorizationApiGrantAuthorizationDetails = {};
```

## Fields

| Field                                                                                                            | Type                                                                                                             | Required                                                                                                         | Description                                                                                                      |
| ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `elements`                                                                                                       | [operations.DeviceAuthorizationApiGrantElement](../../models/operations/deviceauthorizationapigrantelement.md)[] | :heavy_minus_sign:                                                                                               | Elements of this authorization details.<br/>                                                                     |