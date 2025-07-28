# DynamicClientRegistration
(*dynamicClientRegistration*)

## Overview

API endpoints for implementing OAuth 2.0 Dynamic Client Registration.

### Available Operations

* [clientRegistrationApi](#clientregistrationapi) - Register Client
* [clientRegistrationApiForm](#clientregistrationapiform) - Register Client
* [clientRegistrationGetApi](#clientregistrationgetapi) - Get Client
* [clientRegistrationUpdateApi](#clientregistrationupdateapi) - Update Client
* [clientRegistrationUpdateApiForm](#clientregistrationupdateapiform) - Update Client
* [clientRegistrationDeleteApi](#clientregistrationdeleteapi) - Delete Client
* [clientRegistrationDeleteApiForm](#clientregistrationdeleteapiform) - Delete Client

## clientRegistrationApi

Register a client. This API is supposed to be used to implement a client registration endpoint that
complies with [RFC 7591](https://datatracker.ietf.org/doc/html/rfc7591) (OAuth 2.0 Dynamic Client
Registration Protocol).

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from the within the implementation of the client registration
endpoint of the authorization server. The authorization server implementation should retrieve
the value of `action` from the response and take the following steps according to the value.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the API call from the authorization
server implementation was wrong or that an error occurred in Authlete.

In either case, from a viewpoint of the client or developer, it is an error on the server side.
Therefore, the authorization server implementation should generate a response with "500 Internal
Server Error"s and `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 500 Internal Server Error
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client or developer since
"500 Internal Server Error" is not required by the specification.

**BAD_REQUEST**

When the value of `action` is `BAD_REQUEST`, it means that the request from the client or developer
was wrong.

The authorization server implementation should generate a response with "400 Bad Request" and `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used
as the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 400 Bad Request
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

**CREATED**

When the value of `action` is `CREATED`, it means that the request from the client or developer is
valid.

The authorization server implementation should generate a response to the client or developer with
"201 CREATED" and `application/json`.

The `responseContent` a JSON string which can be used as the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 201 CREATED
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_registration_api" method="post" path="/api/{serviceId}/client/registration" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.dynamicClientRegistration.clientRegistrationApi({
    serviceId: "<id>",
    requestBody: {
      json: "{ \"client_name\": \"My Dynamic Client\" }",
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
import { dynamicClientRegistrationClientRegistrationApi } from "authelete-bundled/funcs/dynamicClientRegistrationClientRegistrationApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await dynamicClientRegistrationClientRegistrationApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      json: "{ \"client_name\": \"My Dynamic Client\" }",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("dynamicClientRegistrationClientRegistrationApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientRegistrationApiRequest](../../models/operations/clientregistrationapirequest.md)                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientRegistrationApiResponse](../../models/operations/clientregistrationapiresponse.md)\>**

### Errors

| Error Type                                      | Status Code                                     | Content Type                                    |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| errors.ClientRegistrationApiBadRequestError     | 400                                             | application/json                                |
| errors.ClientRegistrationApiUnauthorizedError   | 401                                             | application/json                                |
| errors.ClientRegistrationApiForbiddenError      | 403                                             | application/json                                |
| errors.ClientRegistrationApiInternalServerError | 500                                             | application/json                                |
| errors.AutheleteBundledDefaultError             | 4XX, 5XX                                        | \*/\*                                           |

## clientRegistrationApiForm

Register a client. This API is supposed to be used to implement a client registration endpoint that
complies with [RFC 7591](https://datatracker.ietf.org/doc/html/rfc7591) (OAuth 2.0 Dynamic Client
Registration Protocol).

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from the within the implementation of the client registration
endpoint of the authorization server. The authorization server implementation should retrieve
the value of `action` from the response and take the following steps according to the value.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the API call from the authorization
server implementation was wrong or that an error occurred in Authlete.

In either case, from a viewpoint of the client or developer, it is an error on the server side.
Therefore, the authorization server implementation should generate a response with "500 Internal
Server Error"s and `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 500 Internal Server Error
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client or developer since
"500 Internal Server Error" is not required by the specification.

**BAD_REQUEST**

When the value of `action` is `BAD_REQUEST`, it means that the request from the client or developer
was wrong.

The authorization server implementation should generate a response with "400 Bad Request" and `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used
as the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 400 Bad Request
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

**CREATED**

When the value of `action` is `CREATED`, it means that the request from the client or developer is
valid.

The authorization server implementation should generate a response to the client or developer with
"201 CREATED" and `application/json`.

The `responseContent` a JSON string which can be used as the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 201 CREATED
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_registration_api_form" method="post" path="/api/{serviceId}/client/registration" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.dynamicClientRegistration.clientRegistrationApiForm({
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
import { dynamicClientRegistrationClientRegistrationApiForm } from "authelete-bundled/funcs/dynamicClientRegistrationClientRegistrationApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await dynamicClientRegistrationClientRegistrationApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("dynamicClientRegistrationClientRegistrationApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientRegistrationApiFormRequest](../../models/operations/clientregistrationapiformrequest.md)                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientRegistrationApiFormResponse](../../models/operations/clientregistrationapiformresponse.md)\>**

### Errors

| Error Type                                          | Status Code                                         | Content Type                                        |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| errors.ClientRegistrationApiFormBadRequestError     | 400                                                 | application/json                                    |
| errors.ClientRegistrationApiFormUnauthorizedError   | 401                                                 | application/json                                    |
| errors.ClientRegistrationApiFormForbiddenError      | 403                                                 | application/json                                    |
| errors.ClientRegistrationApiFormInternalServerError | 500                                                 | application/json                                    |
| errors.AutheleteBundledDefaultError                 | 4XX, 5XX                                            | \*/\*                                               |

## clientRegistrationGetApi

Get a dynamically registered client. This API is supposed to be used to implement a client registration
management endpoint that complies with [RFC 7592](https://datatracker.ietf.org/doc/html/rfc7592)
(OAuth 2.0 Dynamic Registration Management).

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from the within the implementation of the client registration
management endpoint of the authorization server. The authorization server implementation should
retrieve the value of `action` from the response and take the following steps according to the value.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the API call from the authorization
server implementation was wrong or that an error occurred in Authlete.

In either case, from a viewpoint of the client or developer, it is an error on the server side.
Therefore, the authorization server implementation should generate a response to the client or developer
with "500 Internal Server Error"s and `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 500 Internal Server Error
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client or developer since
"500 Internal Server Error" is not required by the specification.

**BAD_REQUEST**

When the value of `action` is `BAD_REQUEST`, it means that the request from the client or developer
was wrong.

The authorization server implementation should generate a response to the client or developer with
"400 Bad Request" and `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 400 Bad Request
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

**UNAUTHORIZED**

When the value of `action` is `UNAUTHORIZED`, it means that the registration access token used by
the client configuration request (RFC 7592) is invalid, or the client application which the token
is tied to does not exist any longer or is invalid.

The HTTP status of the response returned to the client application must be "401 Unauthorized" and
the content type must be `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the endpoint implementation should generate and return
to the client application.

```
HTTP/1.1 401 Unauthorized
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

NOTE: The `UNAUTHORIZED` value was added in October, 2021. See the description of
`Service.unauthorizedOnClientConfigSupported` for details.

**OK**

When the value of `action` is `OK`, it means that the request from the client or developer is valid.

The authorization server implementation should generate a response to the client or developer with
"200 OK" and `application/json`.

The `responseContent` a JSON string which can be used as the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 200 OK
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_registration_get_api" method="post" path="/api/{serviceId}/client/registration/get" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.dynamicClientRegistration.clientRegistrationGetApi({
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
import { dynamicClientRegistrationClientRegistrationGetApi } from "authelete-bundled/funcs/dynamicClientRegistrationClientRegistrationGetApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await dynamicClientRegistrationClientRegistrationGetApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("dynamicClientRegistrationClientRegistrationGetApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientRegistrationGetApiRequest](../../models/operations/clientregistrationgetapirequest.md)                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientRegistrationGetApiResponse](../../models/operations/clientregistrationgetapiresponse.md)\>**

### Errors

| Error Type                                         | Status Code                                        | Content Type                                       |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| errors.ClientRegistrationGetApiBadRequestError     | 400                                                | application/json                                   |
| errors.ClientRegistrationGetApiUnauthorizedError   | 401                                                | application/json                                   |
| errors.ClientRegistrationGetApiForbiddenError      | 403                                                | application/json                                   |
| errors.ClientRegistrationGetApiInternalServerError | 500                                                | application/json                                   |
| errors.AutheleteBundledDefaultError                | 4XX, 5XX                                           | \*/\*                                              |

## clientRegistrationUpdateApi

Update a dynamically registered client. This API is supposed to be used to implement a client
registration management endpoint that complies with [RFC 7592](https://datatracker.ietf.org/doc/html/rfc7592)
(OAuth 2.0 Dynamic Registration Management).

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from the within the implementation of the client registration
management endpoint of the authorization server. The authorization server implementation should
retrieve the value of `action` from the response and take the following steps according to the value.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the API call from the authorization
server implementation was wrong or that an error occurred in Authlete.

In either case, from a viewpoint of the client or developer, it is an error on the server side.
Therefore, the authorization server implementation should generate a response with "500 Internal
Server Error"s and `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 500 Internal Server Error
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client or developer since
"500 Internal Server Error" is not required by the specification.

**BAD_REQUEST**

When the value of `action` is `BAD_REQUEST`, it means that the request from the client or developer
was wrong.

The authorization server implementation should generate a response with "400 Bad Request" and `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 400 Bad Request
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

**UNAUTHORIZED**

When the value of `action` is `UNAUTHORIZED`, it means that the registration access token used by
the client configuration request (RFC 7592) is invalid, or the client application which the token
is tied to does not exist any longer or is invalid.

The HTTP status of the response returned to the client application must be "401 Unauthorized" and
the content type must be `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the endpoint implementation should generate and return
to the client application.

```
HTTP/1.1 401 Unauthorized
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

NOTE: The `UNAUTHORIZED` value was added in October, 2021. See the description of
`Service.unauthorizedOnClientConfigSupported` for details.

**UPDATED**

When the value of `action` is `UPDATED`, it means that the request from the client or developer is
valid.

The authorization server implementation should generate a response to the client or developer with
"200 OK" and `application/json`.

The `responseContent` a JSON string which can be used as the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 200 OK
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_registration_update_api" method="post" path="/api/{serviceId}/client/registration/update" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.dynamicClientRegistration.clientRegistrationUpdateApi({
    serviceId: "<id>",
    requestBody: {
      clientId: "26837717140341",
      token: "qs4Tu5TV7qqDYT93bFs6ISyhTByMF9o-54GY4JU5vTA",
      json: "{\"client_name\":\"My Updated Dynamic Client\",\"default_max_age\":0,\"registration_client_uri\":\"https://my-service.example.com/dcr/register/26837717140341\",\"client_id\":\"26837717140341\",\"token_endpoint_auth_method\":\"client_secret_basic\",\"require_pushed_authorization_requests\":false,\"backchannel_user_code_parameter\":false,\"client_secret\":\"bMsjvZm2FE1_mqJgxhmYj_Wr8rA0Pia_A_j-V076qQm6-P1edKB055W579GBe7MSbOdxZ3dJKsKinCtdIFwxpw\",\"tls_client_certificate_bound_access_tokens\":false,\"id_token_signed_response_alg\":\"RS256\",\"subject_type\":\"public\",\"require_signed_request_object\":false}",
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
import { dynamicClientRegistrationClientRegistrationUpdateApi } from "authelete-bundled/funcs/dynamicClientRegistrationClientRegistrationUpdateApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await dynamicClientRegistrationClientRegistrationUpdateApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientId: "26837717140341",
      token: "qs4Tu5TV7qqDYT93bFs6ISyhTByMF9o-54GY4JU5vTA",
      json: "{\"client_name\":\"My Updated Dynamic Client\",\"default_max_age\":0,\"registration_client_uri\":\"https://my-service.example.com/dcr/register/26837717140341\",\"client_id\":\"26837717140341\",\"token_endpoint_auth_method\":\"client_secret_basic\",\"require_pushed_authorization_requests\":false,\"backchannel_user_code_parameter\":false,\"client_secret\":\"bMsjvZm2FE1_mqJgxhmYj_Wr8rA0Pia_A_j-V076qQm6-P1edKB055W579GBe7MSbOdxZ3dJKsKinCtdIFwxpw\",\"tls_client_certificate_bound_access_tokens\":false,\"id_token_signed_response_alg\":\"RS256\",\"subject_type\":\"public\",\"require_signed_request_object\":false}",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("dynamicClientRegistrationClientRegistrationUpdateApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientRegistrationUpdateApiRequest](../../models/operations/clientregistrationupdateapirequest.md)                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientRegistrationUpdateApiResponse](../../models/operations/clientregistrationupdateapiresponse.md)\>**

### Errors

| Error Type                                            | Status Code                                           | Content Type                                          |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| errors.ClientRegistrationUpdateApiBadRequestError     | 400                                                   | application/json                                      |
| errors.ClientRegistrationUpdateApiUnauthorizedError   | 401                                                   | application/json                                      |
| errors.ClientRegistrationUpdateApiForbiddenError      | 403                                                   | application/json                                      |
| errors.ClientRegistrationUpdateApiInternalServerError | 500                                                   | application/json                                      |
| errors.AutheleteBundledDefaultError                   | 4XX, 5XX                                              | \*/\*                                                 |

## clientRegistrationUpdateApiForm

Update a dynamically registered client. This API is supposed to be used to implement a client
registration management endpoint that complies with [RFC 7592](https://datatracker.ietf.org/doc/html/rfc7592)
(OAuth 2.0 Dynamic Registration Management).

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from the within the implementation of the client registration
management endpoint of the authorization server. The authorization server implementation should
retrieve the value of `action` from the response and take the following steps according to the value.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the API call from the authorization
server implementation was wrong or that an error occurred in Authlete.

In either case, from a viewpoint of the client or developer, it is an error on the server side.
Therefore, the authorization server implementation should generate a response with "500 Internal
Server Error"s and `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 500 Internal Server Error
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client or developer since
"500 Internal Server Error" is not required by the specification.

**BAD_REQUEST**

When the value of `action` is `BAD_REQUEST`, it means that the request from the client or developer
was wrong.

The authorization server implementation should generate a response with "400 Bad Request" and `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 400 Bad Request
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

**UNAUTHORIZED**

When the value of `action` is `UNAUTHORIZED`, it means that the registration access token used by
the client configuration request (RFC 7592) is invalid, or the client application which the token
is tied to does not exist any longer or is invalid.

The HTTP status of the response returned to the client application must be "401 Unauthorized" and
the content type must be `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the endpoint implementation should generate and return
to the client application.

```
HTTP/1.1 401 Unauthorized
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

NOTE: The `UNAUTHORIZED` value was added in October, 2021. See the description of
`Service.unauthorizedOnClientConfigSupported` for details.

**UPDATED**

When the value of `action` is `UPDATED`, it means that the request from the client or developer is
valid.

The authorization server implementation should generate a response to the client or developer with
"200 OK" and `application/json`.

The `responseContent` a JSON string which can be used as the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 200 OK
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_registration_update_api_form" method="post" path="/api/{serviceId}/client/registration/update" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.dynamicClientRegistration.clientRegistrationUpdateApiForm({
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
import { dynamicClientRegistrationClientRegistrationUpdateApiForm } from "authelete-bundled/funcs/dynamicClientRegistrationClientRegistrationUpdateApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await dynamicClientRegistrationClientRegistrationUpdateApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("dynamicClientRegistrationClientRegistrationUpdateApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientRegistrationUpdateApiFormRequest](../../models/operations/clientregistrationupdateapiformrequest.md)                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientRegistrationUpdateApiFormResponse](../../models/operations/clientregistrationupdateapiformresponse.md)\>**

### Errors

| Error Type                                                | Status Code                                               | Content Type                                              |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| errors.ClientRegistrationUpdateApiFormBadRequestError     | 400                                                       | application/json                                          |
| errors.ClientRegistrationUpdateApiFormUnauthorizedError   | 401                                                       | application/json                                          |
| errors.ClientRegistrationUpdateApiFormForbiddenError      | 403                                                       | application/json                                          |
| errors.ClientRegistrationUpdateApiFormInternalServerError | 500                                                       | application/json                                          |
| errors.AutheleteBundledDefaultError                       | 4XX, 5XX                                                  | \*/\*                                                     |

## clientRegistrationDeleteApi

Delete a dynamically registered client. This API is supposed to be used to implement a client
registration management endpoint that complies with [RFC 7592](https://datatracker.ietf.org/doc/html/rfc7592)
(OAuth 2.0 Dynamic Registration Management).

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from the within the implementation of the client registration
management endpoint of the authorization server. The authorization server implementation should
retrieve the value of `action` from the response and take the following steps according to the value.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the API call from the authorization
server implementation was wrong or that an error occurred in Authlete.

In either case, from a viewpoint of the client or developer, it is an error on the server side.
Therefore, the authorization server implementation should generate a response with "500 Internal
Server Error"s and `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 500 Internal Server Error
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client or developer since
"500 Internal Server Error" is not required by the specification.

**BAD_REQUEST**

When the value of `action` is `BAD_REQUEST`, it means that the request from the client or developer
was wrong.

The authorization server implementation should generate a response with "400 Bad Request" and `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 400 Bad Request
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

**UNAUTHORIZED**

When the value of `action` is `UNAUTHORIZED`, it means that the registration access token used by
the client configuration request (RFC 7592) is invalid, or the client application which the token
is tied to does not exist any longer or is invalid.

The HTTP status of the response returned to the client application must be "401 Unauthorized" and
the content type must be `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the endpoint implementation should generate and return
to the client application.

```
HTTP/1.1 401 Unauthorized
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

NOTE: The `UNAUTHORIZED` value was added in October, 2021. See the description of
`Service.unauthorizedOnClientConfigSupported` for details.

**DELETED**

When the value of `action` is `DELETED`, it means that the request from the client or developer is
valid.

The authorization server implementation should generate a response to the client or developer with
"204 No Content".

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 204 No Content
Cache-Control: no-store
Pragma: no-cache
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_registration_delete_api" method="post" path="/api/{serviceId}/client/registration/delete" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.dynamicClientRegistration.clientRegistrationDeleteApi({
    serviceId: "<id>",
    requestBody: {
      clientId: "26837717140341",
      token: "qs4Tu5TV7qqDYT93bFs6ISyhTByMF9o-54GY4JU5vTA",
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
import { dynamicClientRegistrationClientRegistrationDeleteApi } from "authelete-bundled/funcs/dynamicClientRegistrationClientRegistrationDeleteApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await dynamicClientRegistrationClientRegistrationDeleteApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientId: "26837717140341",
      token: "qs4Tu5TV7qqDYT93bFs6ISyhTByMF9o-54GY4JU5vTA",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("dynamicClientRegistrationClientRegistrationDeleteApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientRegistrationDeleteApiRequest](../../models/operations/clientregistrationdeleteapirequest.md)                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientRegistrationDeleteApiResponse](../../models/operations/clientregistrationdeleteapiresponse.md)\>**

### Errors

| Error Type                                            | Status Code                                           | Content Type                                          |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| errors.ClientRegistrationDeleteApiBadRequestError     | 400                                                   | application/json                                      |
| errors.ClientRegistrationDeleteApiUnauthorizedError   | 401                                                   | application/json                                      |
| errors.ClientRegistrationDeleteApiForbiddenError      | 403                                                   | application/json                                      |
| errors.ClientRegistrationDeleteApiInternalServerError | 500                                                   | application/json                                      |
| errors.AutheleteBundledDefaultError                   | 4XX, 5XX                                              | \*/\*                                                 |

## clientRegistrationDeleteApiForm

Delete a dynamically registered client. This API is supposed to be used to implement a client
registration management endpoint that complies with [RFC 7592](https://datatracker.ietf.org/doc/html/rfc7592)
(OAuth 2.0 Dynamic Registration Management).

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from the within the implementation of the client registration
management endpoint of the authorization server. The authorization server implementation should
retrieve the value of `action` from the response and take the following steps according to the value.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the API call from the authorization
server implementation was wrong or that an error occurred in Authlete.

In either case, from a viewpoint of the client or developer, it is an error on the server side.
Therefore, the authorization server implementation should generate a response with "500 Internal
Server Error"s and `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 500 Internal Server Error
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client or developer since
"500 Internal Server Error" is not required by the specification.

**BAD_REQUEST**

When the value of `action` is `BAD_REQUEST`, it means that the request from the client or developer
was wrong.

The authorization server implementation should generate a response with "400 Bad Request" and `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 400 Bad Request
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

**UNAUTHORIZED**

When the value of `action` is `UNAUTHORIZED`, it means that the registration access token used by
the client configuration request (RFC 7592) is invalid, or the client application which the token
is tied to does not exist any longer or is invalid.

The HTTP status of the response returned to the client application must be "401 Unauthorized" and
the content type must be `application/json`.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the endpoint implementation should generate and return
to the client application.

```
HTTP/1.1 401 Unauthorized
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

NOTE: The `UNAUTHORIZED` value was added in October, 2021. See the description of
`Service.unauthorizedOnClientConfigSupported` for details.

**DELETED**

When the value of `action` is `DELETED`, it means that the request from the client or developer is
valid.

The authorization server implementation should generate a response to the client or developer with
"204 No Content".

The following illustrates the response which the authorization server implementation should generate
and return to the client or developer.

```
HTTP/1.1 204 No Content
Cache-Control: no-store
Pragma: no-cache
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_registration_delete_api_form" method="post" path="/api/{serviceId}/client/registration/delete" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.dynamicClientRegistration.clientRegistrationDeleteApiForm({
    serviceId: "<id>",
    requestBody: {
      clientLocked: true,
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
import { dynamicClientRegistrationClientRegistrationDeleteApiForm } from "authelete-bundled/funcs/dynamicClientRegistrationClientRegistrationDeleteApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await dynamicClientRegistrationClientRegistrationDeleteApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("dynamicClientRegistrationClientRegistrationDeleteApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientRegistrationDeleteApiFormRequest](../../models/operations/clientregistrationdeleteapiformrequest.md)                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientRegistrationDeleteApiFormResponse](../../models/operations/clientregistrationdeleteapiformresponse.md)\>**

### Errors

| Error Type                                                | Status Code                                               | Content Type                                              |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| errors.ClientRegistrationDeleteApiFormBadRequestError     | 400                                                       | application/json                                          |
| errors.ClientRegistrationDeleteApiFormUnauthorizedError   | 401                                                       | application/json                                          |
| errors.ClientRegistrationDeleteApiFormForbiddenError      | 403                                                       | application/json                                          |
| errors.ClientRegistrationDeleteApiFormInternalServerError | 500                                                       | application/json                                          |
| errors.AutheleteBundledDefaultError                       | 4XX, 5XX                                                  | \*/\*                                                     |