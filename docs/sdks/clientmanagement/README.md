# ClientManagement
(*clientManagement*)

## Overview

### Available Operations

* [deleteClient](#deleteclient) - Delete Client ⚡
* [updateClientLock](#updateclientlock) - Update Client Lock
* [updateSecret](#updatesecret) - Update Client Secret
* [updateSecretForm](#updatesecretform) - Update Client Secret
* [getAuthorizedApplications](#getauthorizedapplications) - Get Authorized Applications
* [updateTokens](#updatetokens) - Update Client Tokens
* [updateTokensForm](#updatetokensform) - Update Client Tokens
* [deleteAuthorization](#deleteauthorization) - Delete Client Tokens
* [getGrantedScopes](#getgrantedscopes) - Get Granted Scopes
* [deleteGrantedScopes](#deletegrantedscopes) - Delete Granted Scopes
* [getRequestableScopes](#getrequestablescopes) - Get Requestable Scopes
* [updateRequestableScopes](#updaterequestablescopes) - Update Requestable Scopes
* [deleteRequestableScopes](#deleterequestablescopes) - Delete Requestable Scopes

## deleteClient

Delete a client.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_delete_api" method="delete" path="/api/{serviceId}/client/delete/{clientId}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  await autheleteBundled.clientManagement.deleteClient({
    serviceId: "<id>",
    clientId: "<id>",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { clientManagementDeleteClient } from "authelete-bundled/funcs/clientManagementDeleteClient.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementDeleteClient(autheleteBundled, {
    serviceId: "<id>",
    clientId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("clientManagementDeleteClient failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientDeleteApiRequest](../../models/operations/clientdeleteapirequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<void\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## updateClientLock

Lock and unlock a client


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_flag_update_api" method="post" path="/api/{serviceId}/client/lock_flag/update/{clientIdentifier}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.updateClientLock({
    serviceId: "<id>",
    clientIdentifier: "<value>",
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
import { clientManagementUpdateClientLock } from "authelete-bundled/funcs/clientManagementUpdateClientLock.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementUpdateClientLock(autheleteBundled, {
    serviceId: "<id>",
    clientIdentifier: "<value>",
    requestBody: {
      clientLocked: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementUpdateClientLock failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientFlagUpdateApiRequest](../../models/operations/clientflagupdateapirequest.md)                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientFlagUpdateApiResponse](../../models/operations/clientflagupdateapiresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## updateSecret

Update the client secret of a client.

If you want to have the Authlete server generate a new value of the client secret, use `/api/client/secret/refresh`
API.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_secret_update_api" method="post" path="/api/{serviceId}/client/secret/update/{clientIdentifier}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.updateSecret({
    serviceId: "<id>",
    clientIdentifier: "<value>",
    requestBody: {
      clientSecret: "my_updated_client_secret",
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
import { clientManagementUpdateSecret } from "authelete-bundled/funcs/clientManagementUpdateSecret.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementUpdateSecret(autheleteBundled, {
    serviceId: "<id>",
    clientIdentifier: "<value>",
    requestBody: {
      clientSecret: "my_updated_client_secret",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementUpdateSecret failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientSecretUpdateApiRequest](../../models/operations/clientsecretupdateapirequest.md)                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientSecretUpdateApiResponse](../../models/operations/clientsecretupdateapiresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## updateSecretForm

Update the client secret of a client.

If you want to have the Authlete server generate a new value of the client secret, use `/api/client/secret/refresh`
API.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_secret_update_api_form" method="post" path="/api/{serviceId}/client/secret/update/{clientIdentifier}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.updateSecretForm({
    serviceId: "<id>",
    clientIdentifier: "<value>",
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
import { clientManagementUpdateSecretForm } from "authelete-bundled/funcs/clientManagementUpdateSecretForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementUpdateSecretForm(autheleteBundled, {
    serviceId: "<id>",
    clientIdentifier: "<value>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementUpdateSecretForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientSecretUpdateApiFormRequest](../../models/operations/clientsecretupdateapiformrequest.md)                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientSecretUpdateApiFormResponse](../../models/operations/clientsecretupdateapiformresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## getAuthorizedApplications

Get a list of client applications that an end-user has authorized.

The subject parameter is required and can be provided either in the path or as a query parameter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_authorization_get_list_api" method="get" path="/api/{serviceId}/client/authorization/get/list" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.getAuthorizedApplications({
    subject: "<value>",
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
import { clientManagementGetAuthorizedApplications } from "authelete-bundled/funcs/clientManagementGetAuthorizedApplications.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementGetAuthorizedApplications(autheleteBundled, {
    subject: "<value>",
    serviceId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementGetAuthorizedApplications failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientAuthorizationGetListApiRequest](../../models/operations/clientauthorizationgetlistapirequest.md)                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientAuthorizationGetListApiResponse](../../models/operations/clientauthorizationgetlistapiresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## updateTokens

Update attributes of all existing access tokens given to a client application.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_authorization_update_api" method="post" path="/api/{serviceId}/client/authorization/update/{clientId}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.updateTokens({
    serviceId: "<id>",
    clientId: "<id>",
    requestBody: {
      subject: "john",
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
import { clientManagementUpdateTokens } from "authelete-bundled/funcs/clientManagementUpdateTokens.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementUpdateTokens(autheleteBundled, {
    serviceId: "<id>",
    clientId: "<id>",
    requestBody: {
      subject: "john",
      scopes: [
        "history.read",
      ],
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementUpdateTokens failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientAuthorizationUpdateApiRequest](../../models/operations/clientauthorizationupdateapirequest.md)                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientAuthorizationUpdateApiResponse](../../models/operations/clientauthorizationupdateapiresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## updateTokensForm

Update attributes of all existing access tokens given to a client application.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_authorization_update_api_form" method="post" path="/api/{serviceId}/client/authorization/update/{clientId}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.updateTokensForm({
    serviceId: "<id>",
    clientId: "<id>",
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
import { clientManagementUpdateTokensForm } from "authelete-bundled/funcs/clientManagementUpdateTokensForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementUpdateTokensForm(autheleteBundled, {
    serviceId: "<id>",
    clientId: "<id>",
    requestBody: {
      clientLocked: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementUpdateTokensForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientAuthorizationUpdateApiFormRequest](../../models/operations/clientauthorizationupdateapiformrequest.md)                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientAuthorizationUpdateApiFormResponse](../../models/operations/clientauthorizationupdateapiformresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## deleteAuthorization

Delete all existing access tokens issued to a client application by an end-user.

The subject parameter is required and can be provided either in the path or as a query parameter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_authorization_delete_api" method="delete" path="/api/{serviceId}/client/authorization/delete/{clientId}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.deleteAuthorization({
    subject: "<value>",
    serviceId: "<id>",
    clientId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { clientManagementDeleteAuthorization } from "authelete-bundled/funcs/clientManagementDeleteAuthorization.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementDeleteAuthorization(autheleteBundled, {
    subject: "<value>",
    serviceId: "<id>",
    clientId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementDeleteAuthorization failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientAuthorizationDeleteApiRequest](../../models/operations/clientauthorizationdeleteapirequest.md)                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientAuthorizationDeleteApiResponse](../../models/operations/clientauthorizationdeleteapiresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## getGrantedScopes

Get the set of scopes that a user has granted to a client application.

<br>
<details>
<summary>Description</summary>

Possible values for `requestableScopes` parameter in the response from this API are as follows.

**null**

The user has not granted authorization to the client application in the past, or records about the
combination of the user and the client application have been deleted from Authlete's DB.

**An empty set**

The user has granted authorization to the client application in the past, but no scopes are associated
with the authorization.

**A set with at least one element**

The user has granted authorization to the client application in the past and some scopes are associated
with the authorization. These scopes are returned.
Example: `[ "profile", "email" ]`

The subject parameter is required and can be provided either in the path or as a query parameter.
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_granted_scopes_get_api" method="get" path="/api/{serviceId}/client/granted_scopes/get/{clientId}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.getGrantedScopes({
    subject: "<value>",
    serviceId: "<id>",
    clientId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { clientManagementGetGrantedScopes } from "authelete-bundled/funcs/clientManagementGetGrantedScopes.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementGetGrantedScopes(autheleteBundled, {
    subject: "<value>",
    serviceId: "<id>",
    clientId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementGetGrantedScopes failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientGrantedScopesGetApiRequest](../../models/operations/clientgrantedscopesgetapirequest.md)                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientGrantedScopesGetApiResponse](../../models/operations/clientgrantedscopesgetapiresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## deleteGrantedScopes

Delete the set of scopes that an end-user has granted to a client application.

<br>
<details>
<summary>Description</summary>

Even if records about granted scopes are deleted by calling this API, existing access tokens are
not deleted and scopes of existing access tokens are not changed.
</details>

The subject parameter is required and can be provided either in the path or as a query parameter.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_granted_scopes_delete_api" method="delete" path="/api/{serviceId}/client/granted_scopes/delete/{clientId}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.deleteGrantedScopes({
    subject: "<value>",
    serviceId: "<id>",
    clientId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { clientManagementDeleteGrantedScopes } from "authelete-bundled/funcs/clientManagementDeleteGrantedScopes.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementDeleteGrantedScopes(autheleteBundled, {
    subject: "<value>",
    serviceId: "<id>",
    clientId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementDeleteGrantedScopes failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientGrantedScopesDeleteApiRequest](../../models/operations/clientgrantedscopesdeleteapirequest.md)                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientGrantedScopesDeleteApiResponse](../../models/operations/clientgrantedscopesdeleteapiresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## getRequestableScopes

Get the requestable scopes per client


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_extension_requestables_scopes_get_api" method="get" path="/api/{serviceId}/client/extension/requestable_scopes/get/{clientId}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.getRequestableScopes({
    serviceId: "<id>",
    clientId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { clientManagementGetRequestableScopes } from "authelete-bundled/funcs/clientManagementGetRequestableScopes.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementGetRequestableScopes(autheleteBundled, {
    serviceId: "<id>",
    clientId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementGetRequestableScopes failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientExtensionRequestablesScopesGetApiRequest](../../models/operations/clientextensionrequestablesscopesgetapirequest.md)                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientExtensionRequestablesScopesGetApiResponse](../../models/operations/clientextensionrequestablesscopesgetapiresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## updateRequestableScopes

Update requestable scopes of a client


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_extension_requestables_scopes_update_api" method="put" path="/api/{serviceId}/client/extension/requestable_scopes/update/{clientId}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.updateRequestableScopes({
    serviceId: "<id>",
    clientId: "<id>",
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
import { clientManagementUpdateRequestableScopes } from "authelete-bundled/funcs/clientManagementUpdateRequestableScopes.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementUpdateRequestableScopes(autheleteBundled, {
    serviceId: "<id>",
    clientId: "<id>",
    requestBody: {},
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementUpdateRequestableScopes failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientExtensionRequestablesScopesUpdateApiRequest](../../models/operations/clientextensionrequestablesscopesupdateapirequest.md)                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientExtensionRequestablesScopesUpdateApiResponse](../../models/operations/clientextensionrequestablesscopesupdateapiresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## deleteRequestableScopes

Delete requestable scopes of a client


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_extension_requestables_scopes_delete_api" method="delete" path="/api/{serviceId}/client/extension/requestable_scopes/delete/{clientId}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  await autheleteBundled.clientManagement.deleteRequestableScopes({
    serviceId: "<id>",
    clientId: "<id>",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { clientManagementDeleteRequestableScopes } from "authelete-bundled/funcs/clientManagementDeleteRequestableScopes.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementDeleteRequestableScopes(autheleteBundled, {
    serviceId: "<id>",
    clientId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("clientManagementDeleteRequestableScopes failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientExtensionRequestablesScopesDeleteApiRequest](../../models/operations/clientextensionrequestablesscopesdeleteapirequest.md)                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<void\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |