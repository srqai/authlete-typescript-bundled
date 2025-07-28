# UtilityEndpoints
(*utilityEndpoints*)

## Overview

API endpoints for various utility operations.

### Available Operations

* [infoApi](#infoapi) - Get Server Metadata
* [miscEchoApi](#miscechoapi) - Echo

## infoApi

get the server version and enabled features


### Example Usage

<!-- UsageSnippet language="typescript" operationID="info_api" method="get" path="/api/info" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.utilityEndpoints.infoApi();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { utilityEndpointsInfoApi } from "authelete-bundled/funcs/utilityEndpointsInfoApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await utilityEndpointsInfoApi(autheleteBundled);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("utilityEndpointsInfoApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.InfoApiResponse](../../models/operations/infoapiresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.InfoApiBadRequestError       | 400                                 | application/json                    |
| errors.InfoApiUnauthorizedError     | 401                                 | application/json                    |
| errors.InfoApiForbiddenError        | 403                                 | application/json                    |
| errors.InfoApiInternalServerError   | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## miscEchoApi

Echo test endpoint. Will return all path parameters in the request


### Example Usage

<!-- UsageSnippet language="typescript" operationID="misc_echo_api" method="get" path="/api/misc/echo" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  await autheleteBundled.utilityEndpoints.miscEchoApi();


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { utilityEndpointsMiscEchoApi } from "authelete-bundled/funcs/utilityEndpointsMiscEchoApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await utilityEndpointsMiscEchoApi(autheleteBundled);
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("utilityEndpointsMiscEchoApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<void\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |