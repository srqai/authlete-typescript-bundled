# DeviceVerificationApiGrantAuthorizationDetails

The authorization details. This represents the value of the `authorization_details`
request parameter in the preceding device authorization request which is defined in
"OAuth 2.0 Rich Authorization Requests".


## Example Usage

```typescript
import { DeviceVerificationApiGrantAuthorizationDetails } from "authelete-bundled/models/operations";

let value: DeviceVerificationApiGrantAuthorizationDetails = {};
```

## Fields

| Field                                                                                                          | Type                                                                                                           | Required                                                                                                       | Description                                                                                                    |
| -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `elements`                                                                                                     | [operations.DeviceVerificationApiGrantElement](../../models/operations/deviceverificationapigrantelement.md)[] | :heavy_minus_sign:                                                                                             | Elements of this authorization details.<br/>                                                                   |