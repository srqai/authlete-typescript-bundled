# TokenOperations
(*tokenOperations*)

## Overview

API endpoints for various token related operations, including creating, revoking and deleting access_tokens with specified scopes.

### Available Operations

* [authTokenGetListApi](#authtokengetlistapi) - List Issued Tokens
* [authTokenCreateApi](#authtokencreateapi) - Create Access Token
* [authTokenCreateApiForm](#authtokencreateapiform) - Create Access Token
* [authTokenUpdateApi](#authtokenupdateapi) - Update Access Token
* [authTokenUpdateApiForm](#authtokenupdateapiform) - Update Access Token
* [authTokenDeleteApi](#authtokendeleteapi) - Delete Access Token
* [authTokenRevokeApi](#authtokenrevokeapi) - Revoke Access Token
* [authTokenRevokeApiForm](#authtokenrevokeapiform) - Revoke Access Token

## authTokenGetListApi

Get the list of access tokens that are associated with the service.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_token_get_list_api" method="get" path="/api/{serviceId}/auth/token/get/list" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.tokenOperations.authTokenGetListApi({
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
import { tokenOperationsAuthTokenGetListApi } from "authelete-bundled/funcs/tokenOperationsAuthTokenGetListApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await tokenOperationsAuthTokenGetListApi(autheleteBundled, {
    serviceId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokenOperationsAuthTokenGetListApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthTokenGetListApiRequest](../../models/operations/authtokengetlistapirequest.md)                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthTokenGetListApiResponse](../../models/operations/authtokengetlistapiresponse.md)\>**

### Errors

| Error Type                                    | Status Code                                   | Content Type                                  |
| --------------------------------------------- | --------------------------------------------- | --------------------------------------------- |
| errors.AuthTokenGetListApiBadRequestError     | 400                                           | application/json                              |
| errors.AuthTokenGetListApiUnauthorizedError   | 401                                           | application/json                              |
| errors.AuthTokenGetListApiForbiddenError      | 403                                           | application/json                              |
| errors.AuthTokenGetListApiInternalServerError | 500                                           | application/json                              |
| errors.AutheleteBundledDefaultError           | 4XX, 5XX                                      | \*/\*                                         |

## authTokenCreateApi

Create an access token.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_token_create_api" method="post" path="/api/{serviceId}/auth/token/create" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.tokenOperations.authTokenCreateApi({
    serviceId: "<id>",
    requestBody: {
      grantType: "AUTHORIZATION_CODE",
      clientId: 26888344961664,
      subject: "john",
      scopes: [
        "history.read",
        "timeline.read",
      ],
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
import { tokenOperationsAuthTokenCreateApi } from "authelete-bundled/funcs/tokenOperationsAuthTokenCreateApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await tokenOperationsAuthTokenCreateApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      grantType: "AUTHORIZATION_CODE",
      clientId: 26888344961664,
      subject: "john",
      scopes: [
        "history.read",
        "timeline.read",
      ],
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokenOperationsAuthTokenCreateApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthTokenCreateApiRequest](../../models/operations/authtokencreateapirequest.md)                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthTokenCreateApiResponse](../../models/operations/authtokencreateapiresponse.md)\>**

### Errors

| Error Type                                   | Status Code                                  | Content Type                                 |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| errors.AuthTokenCreateApiBadRequestError     | 400                                          | application/json                             |
| errors.AuthTokenCreateApiUnauthorizedError   | 401                                          | application/json                             |
| errors.AuthTokenCreateApiForbiddenError      | 403                                          | application/json                             |
| errors.AuthTokenCreateApiInternalServerError | 500                                          | application/json                             |
| errors.AutheleteBundledDefaultError          | 4XX, 5XX                                     | \*/\*                                        |

## authTokenCreateApiForm

Create an access token.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_token_create_api_form" method="post" path="/api/{serviceId}/auth/token/create" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.tokenOperations.authTokenCreateApiForm({
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
import { tokenOperationsAuthTokenCreateApiForm } from "authelete-bundled/funcs/tokenOperationsAuthTokenCreateApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await tokenOperationsAuthTokenCreateApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokenOperationsAuthTokenCreateApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthTokenCreateApiFormRequest](../../models/operations/authtokencreateapiformrequest.md)                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthTokenCreateApiFormResponse](../../models/operations/authtokencreateapiformresponse.md)\>**

### Errors

| Error Type                                       | Status Code                                      | Content Type                                     |
| ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ |
| errors.AuthTokenCreateApiFormBadRequestError     | 400                                              | application/json                                 |
| errors.AuthTokenCreateApiFormUnauthorizedError   | 401                                              | application/json                                 |
| errors.AuthTokenCreateApiFormForbiddenError      | 403                                              | application/json                                 |
| errors.AuthTokenCreateApiFormInternalServerError | 500                                              | application/json                                 |
| errors.AutheleteBundledDefaultError              | 4XX, 5XX                                         | \*/\*                                            |

## authTokenUpdateApi

Update an access token.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_token_update_api" method="post" path="/api/{serviceId}/auth/token/update" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.tokenOperations.authTokenUpdateApi({
    serviceId: "<id>",
    requestBody: {
      accessToken: "Z5a40U6dWvw2gMoCOAFbZcM85q4HC0Z--0YKD9-Nf6Q",
      scopes: [
        "history.read",
      ],
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
import { tokenOperationsAuthTokenUpdateApi } from "authelete-bundled/funcs/tokenOperationsAuthTokenUpdateApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await tokenOperationsAuthTokenUpdateApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      accessToken: "Z5a40U6dWvw2gMoCOAFbZcM85q4HC0Z--0YKD9-Nf6Q",
      scopes: [
        "history.read",
      ],
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokenOperationsAuthTokenUpdateApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthTokenUpdateApiRequest](../../models/operations/authtokenupdateapirequest.md)                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthTokenUpdateApiResponse](../../models/operations/authtokenupdateapiresponse.md)\>**

### Errors

| Error Type                                   | Status Code                                  | Content Type                                 |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| errors.AuthTokenUpdateApiBadRequestError     | 400                                          | application/json                             |
| errors.AuthTokenUpdateApiUnauthorizedError   | 401                                          | application/json                             |
| errors.AuthTokenUpdateApiForbiddenError      | 403                                          | application/json                             |
| errors.AuthTokenUpdateApiInternalServerError | 500                                          | application/json                             |
| errors.AutheleteBundledDefaultError          | 4XX, 5XX                                     | \*/\*                                        |

## authTokenUpdateApiForm

Update an access token.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_token_update_api_form" method="post" path="/api/{serviceId}/auth/token/update" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.tokenOperations.authTokenUpdateApiForm({
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
import { tokenOperationsAuthTokenUpdateApiForm } from "authelete-bundled/funcs/tokenOperationsAuthTokenUpdateApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await tokenOperationsAuthTokenUpdateApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokenOperationsAuthTokenUpdateApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthTokenUpdateApiFormRequest](../../models/operations/authtokenupdateapiformrequest.md)                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthTokenUpdateApiFormResponse](../../models/operations/authtokenupdateapiformresponse.md)\>**

### Errors

| Error Type                                       | Status Code                                      | Content Type                                     |
| ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ |
| errors.AuthTokenUpdateApiFormBadRequestError     | 400                                              | application/json                                 |
| errors.AuthTokenUpdateApiFormUnauthorizedError   | 401                                              | application/json                                 |
| errors.AuthTokenUpdateApiFormForbiddenError      | 403                                              | application/json                                 |
| errors.AuthTokenUpdateApiFormInternalServerError | 500                                              | application/json                                 |
| errors.AutheleteBundledDefaultError              | 4XX, 5XX                                         | \*/\*                                            |

## authTokenDeleteApi

Delete an access token.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_token_delete_api" method="delete" path="/api/{serviceId}/auth/token/delete/{accessTokenIdentifier}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  await autheleteBundled.tokenOperations.authTokenDeleteApi({
    serviceId: "<id>",
    accessTokenIdentifier: "<value>",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { tokenOperationsAuthTokenDeleteApi } from "authelete-bundled/funcs/tokenOperationsAuthTokenDeleteApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await tokenOperationsAuthTokenDeleteApi(autheleteBundled, {
    serviceId: "<id>",
    accessTokenIdentifier: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("tokenOperationsAuthTokenDeleteApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthTokenDeleteApiRequest](../../models/operations/authtokendeleteapirequest.md)                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<void\>**

### Errors

| Error Type                                   | Status Code                                  | Content Type                                 |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| errors.AuthTokenDeleteApiBadRequestError     | 400                                          | application/json                             |
| errors.AuthTokenDeleteApiUnauthorizedError   | 401                                          | application/json                             |
| errors.AuthTokenDeleteApiForbiddenError      | 403                                          | application/json                             |
| errors.AuthTokenDeleteApiInternalServerError | 500                                          | application/json                             |
| errors.AutheleteBundledDefaultError          | 4XX, 5XX                                     | \*/\*                                        |

## authTokenRevokeApi

Revoke an access token.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_token_revoke_api" method="post" path="/api/{serviceId}/auth/token/revoke" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.tokenOperations.authTokenRevokeApi({
    serviceId: "<id>",
    requestBody: {
      accessTokenIdentifier: "Z5a40U6dWvw2gMoCOAFbZcM85q4HC0Z--0YKD9-Nf6Q",
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
import { tokenOperationsAuthTokenRevokeApi } from "authelete-bundled/funcs/tokenOperationsAuthTokenRevokeApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await tokenOperationsAuthTokenRevokeApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      accessTokenIdentifier: "Z5a40U6dWvw2gMoCOAFbZcM85q4HC0Z--0YKD9-Nf6Q",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokenOperationsAuthTokenRevokeApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthTokenRevokeApiRequest](../../models/operations/authtokenrevokeapirequest.md)                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthTokenRevokeApiResponse](../../models/operations/authtokenrevokeapiresponse.md)\>**

### Errors

| Error Type                                   | Status Code                                  | Content Type                                 |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| errors.AuthTokenRevokeApiBadRequestError     | 400                                          | application/json                             |
| errors.AuthTokenRevokeApiUnauthorizedError   | 401                                          | application/json                             |
| errors.AuthTokenRevokeApiForbiddenError      | 403                                          | application/json                             |
| errors.AuthTokenRevokeApiInternalServerError | 500                                          | application/json                             |
| errors.AutheleteBundledDefaultError          | 4XX, 5XX                                     | \*/\*                                        |

## authTokenRevokeApiForm

Revoke an access token.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_token_revoke_api_form" method="post" path="/api/{serviceId}/auth/token/revoke" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.tokenOperations.authTokenRevokeApiForm({
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
import { tokenOperationsAuthTokenRevokeApiForm } from "authelete-bundled/funcs/tokenOperationsAuthTokenRevokeApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await tokenOperationsAuthTokenRevokeApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokenOperationsAuthTokenRevokeApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthTokenRevokeApiFormRequest](../../models/operations/authtokenrevokeapiformrequest.md)                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthTokenRevokeApiFormResponse](../../models/operations/authtokenrevokeapiformresponse.md)\>**

### Errors

| Error Type                                       | Status Code                                      | Content Type                                     |
| ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ |
| errors.AuthTokenRevokeApiFormBadRequestError     | 400                                              | application/json                                 |
| errors.AuthTokenRevokeApiFormUnauthorizedError   | 401                                              | application/json                                 |
| errors.AuthTokenRevokeApiFormForbiddenError      | 403                                              | application/json                                 |
| errors.AuthTokenRevokeApiFormInternalServerError | 500                                              | application/json                                 |
| errors.AutheleteBundledDefaultError              | 4XX, 5XX                                         | \*/\*                                            |