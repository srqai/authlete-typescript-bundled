# JWKSetEndpoint
(*jwkSetEndpoint*)

## Overview

API endpoints for to generate JSON Web Key Set (JWKS) for a service.

### Available Operations

* [serviceJwksGetApi](#servicejwksgetapi) - Get JWK Set

## serviceJwksGetApi

This API gathers JWK Set information for a service so that its client applications can verify
signatures by the service and encrypt their requests to the service.

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from within the implementation of the jwk set endpoint of the
service where the service that supports OpenID Connect must expose its JWK Set information so that
client applications can verify signatures by the service and encrypt their requests to the service.
The URI of the endpoint can be found as the value of `jwks_uri` in [OpenID Provider Metadata](https://openid.net/specs/openid-connect-discovery-1_0.html#ProviderMetadata)
if the service supports [OpenID Connect Discovery 1.0](https://openid.net/specs/openid-connect-discovery-1_0.html).

</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="service_jwks_get_api" method="get" path="/api/{serviceId}/service/jwks/get" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.jwkSetEndpoint.serviceJwksGetApi({
    serviceId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { jwkSetEndpointServiceJwksGetApi } from "authelete-bundled/funcs/jwkSetEndpointServiceJwksGetApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await jwkSetEndpointServiceJwksGetApi(autheleteBundled, {
    serviceId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("jwkSetEndpointServiceJwksGetApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ServiceJwksGetApiRequest](../../models/operations/servicejwksgetapirequest.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ServiceJwksGetApiResponse](../../models/operations/servicejwksgetapiresponse.md)\>**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| errors.ServiceJwksGetApiBadRequestError     | 400                                         | application/json                            |
| errors.ServiceJwksGetApiUnauthorizedError   | 401                                         | application/json                            |
| errors.ServiceJwksGetApiForbiddenError      | 403                                         | application/json                            |
| errors.ServiceJwksGetApiInternalServerError | 500                                         | application/json                            |
| errors.AutheleteBundledDefaultError         | 4XX, 5XX                                    | \*/\*                                       |