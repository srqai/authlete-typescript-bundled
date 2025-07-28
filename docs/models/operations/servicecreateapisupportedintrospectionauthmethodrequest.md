# ServiceCreateApiSupportedIntrospectionAuthMethodRequest

The client authentication method that the client application declares that it uses at the token
endpoint. This property corresponds to `token_endpoint_auth_method` in [OpenID Connect Dynamic
Client Registration 1.0, 2. Client Metadata](https://openid.net/specs/openid-connect-registration-1_0.html#ClientMetadata).


## Example Usage

```typescript
import { ServiceCreateApiSupportedIntrospectionAuthMethodRequest } from "authelete-bundled/models/operations";

let value: ServiceCreateApiSupportedIntrospectionAuthMethodRequest =
  "SELF_SIGNED_TLS_CLIENT_AUTH";
```

## Values

```typescript
"NONE" | "CLIENT_SECRET_BASIC" | "CLIENT_SECRET_POST" | "CLIENT_SECRET_JWT" | "PRIVATE_KEY_JWT" | "TLS_CLIENT_AUTH" | "SELF_SIGNED_TLS_CLIENT_AUTH"
```