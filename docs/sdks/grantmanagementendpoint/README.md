# GrantManagementEndpoint
(*grantManagementEndpoint*)

## Overview

API endpoint for implementing OAuth 2.0 grants, including grant management actions like updating and revoking grants.

### Available Operations

* [grantMApi](#grantmapi) - Process Grant Management Request

## grantMApi

The API is for the implementation of the grant management endpoint which is
defined in "<a href="https://openid.net/specs/fapi-grant-management.html">Grant Management for OAuth 2.0</a>".


### Example Usage

<!-- UsageSnippet language="typescript" operationID="grant_m_api" method="post" path="/api/{serviceId}/gm" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.grantManagementEndpoint.grantMApi({
    serviceId: "<id>",
    requestBody: {
      accessToken: "eyJhbGciOiJFUzI1NiJ9.eyJleHAiOjE1NTk4MTE3NTAsImlzcyI6IjU3Mjk3NDA4ODY3In0K.csmdholMVcmjqHe59YWgLGNvm7I5Whp4phQCoGxyrlRGMnTgsfxtwyxBgMXQqEPD5q5k9FaEWNk37K8uAtSwrA",
      subject: "123457884",
      gmAction: "REVOKE",
      grantId: "57297408867",
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
import { grantManagementEndpointGrantMApi } from "authelete-bundled/funcs/grantManagementEndpointGrantMApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await grantManagementEndpointGrantMApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      accessToken: "eyJhbGciOiJFUzI1NiJ9.eyJleHAiOjE1NTk4MTE3NTAsImlzcyI6IjU3Mjk3NDA4ODY3In0K.csmdholMVcmjqHe59YWgLGNvm7I5Whp4phQCoGxyrlRGMnTgsfxtwyxBgMXQqEPD5q5k9FaEWNk37K8uAtSwrA",
      subject: "123457884",
      gmAction: "REVOKE",
      grantId: "57297408867",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("grantManagementEndpointGrantMApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GrantMApiRequest](../../models/operations/grantmapirequest.md)                                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.GrantMApiResponse](../../models/operations/grantmapiresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.GrantMApiBadRequestError     | 400                                 | application/json                    |
| errors.GrantMApiUnauthorizedError   | 401                                 | application/json                    |
| errors.GrantMApiForbiddenError      | 403                                 | application/json                    |
| errors.GrantMApiInternalServerError | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |