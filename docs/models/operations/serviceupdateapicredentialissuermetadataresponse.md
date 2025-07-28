# ServiceUpdateApiCredentialIssuerMetadataResponse

## Example Usage

```typescript
import { ServiceUpdateApiCredentialIssuerMetadataResponse } from "authelete-bundled/models/operations";

let value: ServiceUpdateApiCredentialIssuerMetadataResponse = {};
```

## Fields

| Field                                                                                               | Type                                                                                                | Required                                                                                            | Description                                                                                         |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| `credentialIssuer`                                                                                  | *string*                                                                                            | :heavy_minus_sign:                                                                                  | The identifier of a credential request.                                                             |
| `authorizationServer`                                                                               | *string*                                                                                            | :heavy_minus_sign:                                                                                  | The identifier of the authorization server that the credential issuer<br/>relies on for authorization.<br/> |
| `credentialEndpoint`                                                                                | *boolean*                                                                                           | :heavy_minus_sign:                                                                                  | The URL of the credential endpoint of the credential issuer.                                        |
| `batchCredentialEndpoint`                                                                           | *number*                                                                                            | :heavy_minus_sign:                                                                                  | The URL of the batch credential endpoint of the credential issuer.                                  |
| `deferredCredentialEndpoint`                                                                        | *string*                                                                                            | :heavy_minus_sign:                                                                                  | The URL of the deferred credential endpoint of the credential issuer.                               |
| `credentialsSupported`                                                                              | *boolean*                                                                                           | :heavy_minus_sign:                                                                                  | A JSON array describing supported credentials.                                                      |