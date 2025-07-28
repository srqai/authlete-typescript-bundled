# JoseObject
(*joseObject*)

## Overview

API endpoints for JOSE objects.

### Available Operations

* [joseVerifyApi](#joseverifyapi) - Verify JOSE
* [joseVerifyApiForm](#joseverifyapiform) - Verify JOSE

## joseVerifyApi

This API verifies a JOSE object.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="jose_verify_api" method="post" path="/api/{serviceId}/jose/verify" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.joseObject.joseVerifyApi({
    serviceId: "<id>",
    requestBody: {
      jose: "eyJhbGciOiJFUzI1NiJ9.eyJleHAiOjE1NTk4MTE3NTAsImlzcyI6IjU3Mjk3NDA4ODY3In0K.csmdholMVcmjqHe59YWgLGNvm7I5Whp4phQCoGxyrlRGMnTgsfxtwyxBgMXQqEPD5q5k9FaEWNk37K8uAtSwrA",
      clockSkew: 100,
      clientIdentifier: "57297408867",
      signedByClient: true,
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
import { joseObjectJoseVerifyApi } from "authelete-bundled/funcs/joseObjectJoseVerifyApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await joseObjectJoseVerifyApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      jose: "eyJhbGciOiJFUzI1NiJ9.eyJleHAiOjE1NTk4MTE3NTAsImlzcyI6IjU3Mjk3NDA4ODY3In0K.csmdholMVcmjqHe59YWgLGNvm7I5Whp4phQCoGxyrlRGMnTgsfxtwyxBgMXQqEPD5q5k9FaEWNk37K8uAtSwrA",
      clockSkew: 100,
      clientIdentifier: "57297408867",
      signedByClient: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("joseObjectJoseVerifyApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.JoseVerifyApiRequest](../../models/operations/joseverifyapirequest.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.JoseVerifyApiResponse](../../models/operations/joseverifyapiresponse.md)\>**

### Errors

| Error Type                              | Status Code                             | Content Type                            |
| --------------------------------------- | --------------------------------------- | --------------------------------------- |
| errors.JoseVerifyApiBadRequestError     | 400                                     | application/json                        |
| errors.JoseVerifyApiUnauthorizedError   | 401                                     | application/json                        |
| errors.JoseVerifyApiForbiddenError      | 403                                     | application/json                        |
| errors.JoseVerifyApiInternalServerError | 500                                     | application/json                        |
| errors.AutheleteBundledDefaultError     | 4XX, 5XX                                | \*/\*                                   |

## joseVerifyApiForm

This API verifies a JOSE object.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="jose_verify_api_form" method="post" path="/api/{serviceId}/jose/verify" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.joseObject.joseVerifyApiForm({
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
import { joseObjectJoseVerifyApiForm } from "authelete-bundled/funcs/joseObjectJoseVerifyApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await joseObjectJoseVerifyApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("joseObjectJoseVerifyApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.JoseVerifyApiFormRequest](../../models/operations/joseverifyapiformrequest.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.JoseVerifyApiFormResponse](../../models/operations/joseverifyapiformresponse.md)\>**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| errors.JoseVerifyApiFormBadRequestError     | 400                                         | application/json                            |
| errors.JoseVerifyApiFormUnauthorizedError   | 401                                         | application/json                            |
| errors.JoseVerifyApiFormForbiddenError      | 403                                         | application/json                            |
| errors.JoseVerifyApiFormInternalServerError | 500                                         | application/json                            |
| errors.AutheleteBundledDefaultError         | 4XX, 5XX                                    | \*/\*                                       |