# PushedAuthorizationEndpoint
(*pushedAuthorizationEndpoint*)

## Overview

API endpoints for implementing OAuth 2.0 Pushed Authorization Requests (PAR).

### Available Operations

* [pushedAuthReqApi](#pushedauthreqapi) - Process Pushed Authorization Request
* [pushedAuthReqApiForm](#pushedauthreqapiform) - Process Pushed Authorization Request

## pushedAuthReqApi

This API creates a pushed request authorization. It authenticates the client and creates a authorization_uri to be returned by the authorization server.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="pushed_auth_req_api" method="post" path="/api/{serviceId}/pushed_auth_req" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.pushedAuthorizationEndpoint.pushedAuthReqApi({
    serviceId: "<id>",
    requestBody: {
      parameters: "response_type=code%20id_token&client_id=5921531358155430&redirect_uri=https%3A%2F%2Fserver.example.com%2Fcb&state=SOME_VALUE_ABLE_TO_PREVENT_CSRF&scope=openid&nonce=SOME_VALUE_ABLE_TO_PREVENT_REPLAY_ATTACK&code_challenge=5ZWDQJiryK3eaLtSeFV8y1XySMCWtyITxICLaTwvK8g&code_challenge_method=S256",
      clientId: "5921531358155430",
      clientSecret: "P_FouxWlI7zcOep_9vBwR9qMAVJQiCiUiK1HrAP4GziOyezHQpqY0f5dHXK4JT4tnvI51OkbWVoEM9GnOyJViA",
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
import { pushedAuthorizationEndpointPushedAuthReqApi } from "authelete-bundled/funcs/pushedAuthorizationEndpointPushedAuthReqApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await pushedAuthorizationEndpointPushedAuthReqApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      parameters: "response_type=code%20id_token&client_id=5921531358155430&redirect_uri=https%3A%2F%2Fserver.example.com%2Fcb&state=SOME_VALUE_ABLE_TO_PREVENT_CSRF&scope=openid&nonce=SOME_VALUE_ABLE_TO_PREVENT_REPLAY_ATTACK&code_challenge=5ZWDQJiryK3eaLtSeFV8y1XySMCWtyITxICLaTwvK8g&code_challenge_method=S256",
      clientId: "5921531358155430",
      clientSecret: "P_FouxWlI7zcOep_9vBwR9qMAVJQiCiUiK1HrAP4GziOyezHQpqY0f5dHXK4JT4tnvI51OkbWVoEM9GnOyJViA",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("pushedAuthorizationEndpointPushedAuthReqApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PushedAuthReqApiRequest](../../models/operations/pushedauthreqapirequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.PushedAuthReqApiResponse](../../models/operations/pushedauthreqapiresponse.md)\>**

### Errors

| Error Type                                 | Status Code                                | Content Type                               |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| errors.PushedAuthReqApiBadRequestError     | 400                                        | application/json                           |
| errors.PushedAuthReqApiUnauthorizedError   | 401                                        | application/json                           |
| errors.PushedAuthReqApiForbiddenError      | 403                                        | application/json                           |
| errors.PushedAuthReqApiInternalServerError | 500                                        | application/json                           |
| errors.AutheleteBundledDefaultError        | 4XX, 5XX                                   | \*/\*                                      |

## pushedAuthReqApiForm

This API creates a pushed request authorization. It authenticates the client and creates a authorization_uri to be returned by the authorization server.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="pushed_auth_req_api_form" method="post" path="/api/{serviceId}/pushed_auth_req" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.pushedAuthorizationEndpoint.pushedAuthReqApiForm({
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
import { pushedAuthorizationEndpointPushedAuthReqApiForm } from "authelete-bundled/funcs/pushedAuthorizationEndpointPushedAuthReqApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await pushedAuthorizationEndpointPushedAuthReqApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("pushedAuthorizationEndpointPushedAuthReqApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PushedAuthReqApiFormRequest](../../models/operations/pushedauthreqapiformrequest.md)                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.PushedAuthReqApiFormResponse](../../models/operations/pushedauthreqapiformresponse.md)\>**

### Errors

| Error Type                                     | Status Code                                    | Content Type                                   |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| errors.PushedAuthReqApiFormBadRequestError     | 400                                            | application/json                               |
| errors.PushedAuthReqApiFormUnauthorizedError   | 401                                            | application/json                               |
| errors.PushedAuthReqApiFormForbiddenError      | 403                                            | application/json                               |
| errors.PushedAuthReqApiFormInternalServerError | 500                                            | application/json                               |
| errors.AutheleteBundledDefaultError            | 4XX, 5XX                                       | \*/\*                                          |