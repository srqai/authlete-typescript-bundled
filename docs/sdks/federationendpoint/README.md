# FederationEndpoint
(*federationEndpoint*)

## Overview

API endpoints for implementing OpenID Federation using Authlete.

### Available Operations

* [federationConfigurationApi](#federationconfigurationapi) - Process Entity Configuration Request
* [federationRegistrationApi](#federationregistrationapi) - Process Federation Registration Request
* [federationRegistrationApiForm](#federationregistrationapiform) - Process Federation Registration Request

## federationConfigurationApi

This API gathers the federation configuration about a service.

The authorization server implementation should
retrieve the value of the <code>action</code>
response parameter from the API response and take the following steps
according to the value.

<h3><code>OK</code></h3>

When the value of the <code> action</code> response
parameter is <code>OK</code>, it means that Authlete
could prepare an entity configuration successfully.

In this case, the implementation of the entity configuration endpoint of the
authorization server should return an HTTP response to the client application
with the HTTP status code "`200 OK`" and the content type
"`application/entity-statement+jwt`". The message body (= an entity
configuration in the JWT format) of the response has been prepared by
Authlete's `/federation/configuration` API and it is available as the
<code>responseContent</code> response parameter.

The implementation of the entity configuration endpoint can construct an
HTTP response by doing like below.

<pre style="border: solid 1px black; padding: 0.5em;">
200 OK
Content-Type: application/entity-statement+jwt
(Other HTTP headers)

<i>(the value of the responseContent response parameter)</i></pre>

<h3><code>NOT_FOUND</code></h3>

When the value of the <code> action</code> response
parameter is <code>NOT_FOUND</code>, it means that
the service configuration has not enabled the feature of <a href=
"https://openid.net/specs/openid-connect-federation-1_0.html">OpenID Connect
Federation 1.0</a> and so the client application should have not access the
entity configuration endpoint.

In this case, the implementation of the entity configuration endpoint of the
authorization server should return an HTTP response to the client application
with the HTTP status code "`404 Not Found`" and the content type
"`application/json`". The message body (= error information in the JSON
format) of the response has been prepared by Authlete's
`/federation/configuration` API and it is available as the
<code>responseContent</code> response parameter.

The implementation of the entity configuration endpoint can construct an
HTTP response by doing like below.

<pre style="border: solid 1px black; padding: 0.5em;">
404 Not Found
Content-Type: application/json
(Other HTTP headers)

<i>(the value of the responseContent response parameter)</i></pre>

<h3><code>INTERNAL_SERVER_ERROR</code></h3>

could prepare an entity configuration successfully.

In this case, the implementation of the entity configuration endpoint of the
authorization server should return an HTTP response to the client application
with the HTTP status code "`200 OK`" and the content type
"`application/entity-statement+jwt`". The message body (= an entity
configuration in the JWT format) of the response has been prepared by
Authlete's `/federation/configuration` API and it is available as the
<code>responseContent</code> response parameter.

The implementation of the entity configuration endpoint can construct an
HTTP response by doing like below.

<pre style="border: solid 1px black; padding: 0.5em;">
200 OK
Content-Type: application/entity-statement+jwt
(Other HTTP headers)

<i>(the value of the responseContent response parameter)</i></pre>


</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="federation_configuration_api" method="post" path="/api/{serviceId}/federation/configuration" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.federationEndpoint.federationConfigurationApi({
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
import { federationEndpointFederationConfigurationApi } from "authelete-bundled/funcs/federationEndpointFederationConfigurationApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await federationEndpointFederationConfigurationApi(autheleteBundled, {
    serviceId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("federationEndpointFederationConfigurationApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.FederationConfigurationApiRequest](../../models/operations/federationconfigurationapirequest.md)                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.FederationConfigurationApiResponse](../../models/operations/federationconfigurationapiresponse.md)\>**

### Errors

| Error Type                                           | Status Code                                          | Content Type                                         |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| errors.FederationConfigurationApiBadRequestError     | 400                                                  | application/json                                     |
| errors.FederationConfigurationApiUnauthorizedError   | 401                                                  | application/json                                     |
| errors.FederationConfigurationApiForbiddenError      | 403                                                  | application/json                                     |
| errors.FederationConfigurationApiInternalServerError | 500                                                  | application/json                                     |
| errors.AutheleteBundledDefaultError                  | 4XX, 5XX                                             | \*/\*                                                |

## federationRegistrationApi

The Authlete API is for implementations of the <b>federation registration
endpoint</b> that accepts "explicit client registration". Its details are
defined in <a href="https://openid.net/specs/openid-connect-federation-1_0.html"
>OpenID Connect Federation 1.0</a>.
</p>

<p>
The endpoint accepts `POST` requests whose `Content-Type`
is either of the following.
</p>

<ol>
  <li>`application/entity-statement+jwt`
  <li>`application/trust-chain+json`
</ol>

<p>
When the `Content-Type` of a request is
`application/entity-statement+jwt`, the content of the request is
the entity configuration of a relying party that is to be registered.
In this case, the implementation of the federation registration endpoint
should call Authlete's `/federation/registration` API with the
entity configuration set to the `entityConfiguration` request
parameter.
</p>

<p>
On the other hand, when the `Content-Type` of a request is
`application/trust-chain+json`, the content of the request is a
JSON array that contains entity statements in JWT format. The sequence
of the entity statements composes the trust chain of a relying party
that is to be registered. In this case, the implementation of the
federation registration endpoint should call Authlete's
`/federation/registration` API with the trust chain set to the
`trustChain` request parameter.
</p>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="federation_registration_api" method="post" path="/api/{serviceId}/federation/registration" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.federationEndpoint.federationRegistrationApi({
    serviceId: "<id>",
    requestBody: {},
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { federationEndpointFederationRegistrationApi } from "authelete-bundled/funcs/federationEndpointFederationRegistrationApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await federationEndpointFederationRegistrationApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {},
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("federationEndpointFederationRegistrationApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.FederationRegistrationApiRequest](../../models/operations/federationregistrationapirequest.md)                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.FederationRegistrationApiResponse](../../models/operations/federationregistrationapiresponse.md)\>**

### Errors

| Error Type                                          | Status Code                                         | Content Type                                        |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| errors.FederationRegistrationApiBadRequestError     | 400                                                 | application/json                                    |
| errors.FederationRegistrationApiUnauthorizedError   | 401                                                 | application/json                                    |
| errors.FederationRegistrationApiForbiddenError      | 403                                                 | application/json                                    |
| errors.FederationRegistrationApiInternalServerError | 500                                                 | application/json                                    |
| errors.AutheleteBundledDefaultError                 | 4XX, 5XX                                            | \*/\*                                               |

## federationRegistrationApiForm

The Authlete API is for implementations of the <b>federation registration
endpoint</b> that accepts "explicit client registration". Its details are
defined in <a href="https://openid.net/specs/openid-connect-federation-1_0.html"
>OpenID Connect Federation 1.0</a>.
</p>

<p>
The endpoint accepts `POST` requests whose `Content-Type`
is either of the following.
</p>

<ol>
  <li>`application/entity-statement+jwt`
  <li>`application/trust-chain+json`
</ol>

<p>
When the `Content-Type` of a request is
`application/entity-statement+jwt`, the content of the request is
the entity configuration of a relying party that is to be registered.
In this case, the implementation of the federation registration endpoint
should call Authlete's `/federation/registration` API with the
entity configuration set to the `entityConfiguration` request
parameter.
</p>

<p>
On the other hand, when the `Content-Type` of a request is
`application/trust-chain+json`, the content of the request is a
JSON array that contains entity statements in JWT format. The sequence
of the entity statements composes the trust chain of a relying party
that is to be registered. In this case, the implementation of the
federation registration endpoint should call Authlete's
`/federation/registration` API with the trust chain set to the
`trustChain` request parameter.
</p>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="federation_registration_api_form" method="post" path="/api/{serviceId}/federation/registration" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.federationEndpoint.federationRegistrationApiForm({
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { federationEndpointFederationRegistrationApiForm } from "authelete-bundled/funcs/federationEndpointFederationRegistrationApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await federationEndpointFederationRegistrationApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("federationEndpointFederationRegistrationApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.FederationRegistrationApiFormRequest](../../models/operations/federationregistrationapiformrequest.md)                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.FederationRegistrationApiFormResponse](../../models/operations/federationregistrationapiformresponse.md)\>**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| errors.FederationRegistrationApiFormBadRequestError     | 400                                                     | application/json                                        |
| errors.FederationRegistrationApiFormUnauthorizedError   | 401                                                     | application/json                                        |
| errors.FederationRegistrationApiFormForbiddenError      | 403                                                     | application/json                                        |
| errors.FederationRegistrationApiFormInternalServerError | 500                                                     | application/json                                        |
| errors.AutheleteBundledDefaultError                     | 4XX, 5XX                                                | \*/\*                                                   |