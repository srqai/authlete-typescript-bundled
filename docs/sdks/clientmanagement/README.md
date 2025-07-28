# ClientManagement
(*clientManagement*)

## Overview

API endpoints for managing OAuth clients, including creation, update, and deletion of clients.

### Available Operations

* [clientGetApi](#clientgetapi) - Get Client
* [clientGetListApi](#clientgetlistapi) - List Clients
* [clientCreateApi](#clientcreateapi) - Create Client
* [clientUpdateApi](#clientupdateapi) - Update Client
* [clientDeleteApi](#clientdeleteapi) - Delete Client ⚡
* [clientFlagUpdateApi](#clientflagupdateapi) - Update Client Lock
* [clientSecretRefreshApi](#clientsecretrefreshapi) - Rotate Client Secret
* [clientSecretUpdateApi](#clientsecretupdateapi) - Update Client Secret
* [clientSecretUpdateApiForm](#clientsecretupdateapiform) - Update Client Secret
* [clientAuthorizationGetListApi](#clientauthorizationgetlistapi) - Get Authorized Applications
* [clientAuthorizationUpdateApi](#clientauthorizationupdateapi) - Update Client Tokens
* [clientAuthorizationUpdateApiForm](#clientauthorizationupdateapiform) - Update Client Tokens
* [clientAuthorizationDeleteApi](#clientauthorizationdeleteapi) - Delete Client Tokens
* [clientGrantedScopesGetApi](#clientgrantedscopesgetapi) - Get Granted Scopes
* [clientGrantedScopesDeleteApi](#clientgrantedscopesdeleteapi) - Delete Granted Scopes
* [clientExtensionRequestablesScopesGetApi](#clientextensionrequestablesscopesgetapi) - Get Requestable Scopes
* [clientExtensionRequestablesScopesUpdateApi](#clientextensionrequestablesscopesupdateapi) - Update Requestable Scopes
* [clientExtensionRequestablesScopesDeleteApi](#clientextensionrequestablesscopesdeleteapi) - Delete Requestable Scopes

## clientGetApi

Get a client.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_get_api" method="get" path="/api/{serviceId}/client/get/{clientId}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.clientGetApi({
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
import { clientManagementClientGetApi } from "authelete-bundled/funcs/clientManagementClientGetApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientGetApi(autheleteBundled, {
    serviceId: "<id>",
    clientId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementClientGetApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientGetApiRequest](../../models/operations/clientgetapirequest.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientGetApiResponse](../../models/operations/clientgetapiresponse.md)\>**

### Errors

| Error Type                             | Status Code                            | Content Type                           |
| -------------------------------------- | -------------------------------------- | -------------------------------------- |
| errors.ClientGetApiBadRequestError     | 400                                    | application/json                       |
| errors.ClientGetApiUnauthorizedError   | 401                                    | application/json                       |
| errors.ClientGetApiForbiddenError      | 403                                    | application/json                       |
| errors.ClientGetApiInternalServerError | 500                                    | application/json                       |
| errors.AutheleteBundledDefaultError    | 4XX, 5XX                               | \*/\*                                  |

## clientGetListApi

Get a list of clients on a service.

If the access token can view a full service (including an admin), all clients within the
service are returned. Otherwise, only clients that the access token can view within the
service are returned.
- ViewClient: []


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_get_list_api" method="get" path="/api/{serviceId}/client/get/list" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.clientGetListApi({
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
import { clientManagementClientGetListApi } from "authelete-bundled/funcs/clientManagementClientGetListApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientGetListApi(autheleteBundled, {
    serviceId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementClientGetListApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientGetListApiRequest](../../models/operations/clientgetlistapirequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientGetListApiResponse](../../models/operations/clientgetlistapiresponse.md)\>**

### Errors

| Error Type                                 | Status Code                                | Content Type                               |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| errors.ClientGetListApiBadRequestError     | 400                                        | application/json                           |
| errors.ClientGetListApiUnauthorizedError   | 401                                        | application/json                           |
| errors.ClientGetListApiForbiddenError      | 403                                        | application/json                           |
| errors.ClientGetListApiInternalServerError | 500                                        | application/json                           |
| errors.AutheleteBundledDefaultError        | 4XX, 5XX                                   | \*/\*                                      |

## clientCreateApi

Create a new client.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_create_api" method="post" path="/api/{serviceId}/client/create" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.clientCreateApi({
    serviceId: "<id>",
    requestBody: {
      clientName: "My Client",
      clientIdAlias: "my-client",
      clientIdAliasEnabled: true,
      clientType: "CONFIDENTIAL",
      applicationType: "WEB",
      grantTypes: [
        "AUTHORIZATION_CODE",
        "REFRESH_TOKEN",
      ],
      responseTypes: [
        "CODE",
        "TOKEN",
      ],
      redirectUris: [
        "https://my-client.example.com/cb1",
        "https://my-client.example.com/cb2",
      ],
      tokenAuthMethod: "CLIENT_SECRET_BASIC",
      attributes: [
        {
          key: "attribute1-key",
          value: "attribute1-value",
        },
        {
          key: "attribute2-key",
          value: "attribute2-value",
        },
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
import { clientManagementClientCreateApi } from "authelete-bundled/funcs/clientManagementClientCreateApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientCreateApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientName: "My Client",
      clientIdAlias: "my-client",
      clientIdAliasEnabled: true,
      clientType: "CONFIDENTIAL",
      applicationType: "WEB",
      grantTypes: [
        "AUTHORIZATION_CODE",
        "REFRESH_TOKEN",
      ],
      responseTypes: [
        "CODE",
        "TOKEN",
      ],
      redirectUris: [
        "https://my-client.example.com/cb1",
        "https://my-client.example.com/cb2",
      ],
      tokenAuthMethod: "CLIENT_SECRET_BASIC",
      attributes: [
        {
          key: "attribute1-key",
          value: "attribute1-value",
        },
        {
          key: "attribute2-key",
          value: "attribute2-value",
        },
      ],
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementClientCreateApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientCreateApiRequest](../../models/operations/clientcreateapirequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientCreateApiResponse](../../models/operations/clientcreateapiresponse.md)\>**

### Errors

| Error Type                                | Status Code                               | Content Type                              |
| ----------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| errors.ClientCreateApiBadRequestError     | 400                                       | application/json                          |
| errors.ClientCreateApiUnauthorizedError   | 401                                       | application/json                          |
| errors.ClientCreateApiForbiddenError      | 403                                       | application/json                          |
| errors.ClientCreateApiInternalServerError | 500                                       | application/json                          |
| errors.AutheleteBundledDefaultError       | 4XX, 5XX                                  | \*/\*                                     |

## clientUpdateApi

Update a client.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_update_api" method="post" path="/api/{serviceId}/client/update/{clientId}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.clientUpdateApi({
    serviceId: "<id>",
    clientId: "<id>",
    requestBody: {
      clientName: "My updated client",
      clientIdAlias: "my-client",
      clientIdAliasEnabled: true,
      clientType: "CONFIDENTIAL",
      applicationType: "WEB",
      tlsClientCertificateBoundAccessTokens: false,
      grantTypes: [
        "AUTHORIZATION_CODE",
        "REFRESH_TOKEN",
      ],
      responseTypes: [
        "CODE",
        "TOKEN",
      ],
      redirectUris: [
        "https://my-client.example.com/cb1",
        "https://my-client.example.com/cb2",
      ],
      tokenAuthMethod: "CLIENT_SECRET_BASIC",
      parRequired: false,
      requestObjectRequired: false,
      defaultMaxAge: 0,
      idTokenSignAlg: "RS256",
      authTimeRequired: false,
      subjectType: "PUBLIC",
      bcUserCodeRequired: false,
      attributes: [
        {
          key: "attribute1-key",
          value: "attribute1-value",
        },
        {
          key: "attribute2-key",
          value: "attribute2-value",
        },
      ],
      frontChannelRequestObjectEncryptionRequired: false,
      requestObjectEncryptionAlgMatchRequired: false,
      requestObjectEncryptionEncMatchRequired: false,
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
import { clientManagementClientUpdateApi } from "authelete-bundled/funcs/clientManagementClientUpdateApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientUpdateApi(autheleteBundled, {
    serviceId: "<id>",
    clientId: "<id>",
    requestBody: {
      clientName: "My updated client",
      clientIdAlias: "my-client",
      clientIdAliasEnabled: true,
      clientType: "CONFIDENTIAL",
      applicationType: "WEB",
      tlsClientCertificateBoundAccessTokens: false,
      grantTypes: [
        "AUTHORIZATION_CODE",
        "REFRESH_TOKEN",
      ],
      responseTypes: [
        "CODE",
        "TOKEN",
      ],
      redirectUris: [
        "https://my-client.example.com/cb1",
        "https://my-client.example.com/cb2",
      ],
      tokenAuthMethod: "CLIENT_SECRET_BASIC",
      parRequired: false,
      requestObjectRequired: false,
      defaultMaxAge: 0,
      idTokenSignAlg: "RS256",
      authTimeRequired: false,
      subjectType: "PUBLIC",
      bcUserCodeRequired: false,
      attributes: [
        {
          key: "attribute1-key",
          value: "attribute1-value",
        },
        {
          key: "attribute2-key",
          value: "attribute2-value",
        },
      ],
      frontChannelRequestObjectEncryptionRequired: false,
      requestObjectEncryptionAlgMatchRequired: false,
      requestObjectEncryptionEncMatchRequired: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementClientUpdateApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientUpdateApiRequest](../../models/operations/clientupdateapirequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientUpdateApiResponse](../../models/operations/clientupdateapiresponse.md)\>**

### Errors

| Error Type                                | Status Code                               | Content Type                              |
| ----------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| errors.ClientUpdateApiBadRequestError     | 400                                       | application/json                          |
| errors.ClientUpdateApiUnauthorizedError   | 401                                       | application/json                          |
| errors.ClientUpdateApiForbiddenError      | 403                                       | application/json                          |
| errors.ClientUpdateApiInternalServerError | 500                                       | application/json                          |
| errors.AutheleteBundledDefaultError       | 4XX, 5XX                                  | \*/\*                                     |

## clientDeleteApi

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
  await autheleteBundled.clientManagement.clientDeleteApi({
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
import { clientManagementClientDeleteApi } from "authelete-bundled/funcs/clientManagementClientDeleteApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientDeleteApi(autheleteBundled, {
    serviceId: "<id>",
    clientId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("clientManagementClientDeleteApi failed:", res.error);
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

| Error Type                                | Status Code                               | Content Type                              |
| ----------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| errors.ClientDeleteApiBadRequestError     | 400                                       | application/json                          |
| errors.ClientDeleteApiUnauthorizedError   | 401                                       | application/json                          |
| errors.ClientDeleteApiForbiddenError      | 403                                       | application/json                          |
| errors.ClientDeleteApiInternalServerError | 500                                       | application/json                          |
| errors.AutheleteBundledDefaultError       | 4XX, 5XX                                  | \*/\*                                     |

## clientFlagUpdateApi

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
  const result = await autheleteBundled.clientManagement.clientFlagUpdateApi({
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
import { clientManagementClientFlagUpdateApi } from "authelete-bundled/funcs/clientManagementClientFlagUpdateApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientFlagUpdateApi(autheleteBundled, {
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
    console.log("clientManagementClientFlagUpdateApi failed:", res.error);
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

| Error Type                                    | Status Code                                   | Content Type                                  |
| --------------------------------------------- | --------------------------------------------- | --------------------------------------------- |
| errors.ClientFlagUpdateApiBadRequestError     | 400                                           | application/json                              |
| errors.ClientFlagUpdateApiUnauthorizedError   | 401                                           | application/json                              |
| errors.ClientFlagUpdateApiForbiddenError      | 403                                           | application/json                              |
| errors.ClientFlagUpdateApiInternalServerError | 500                                           | application/json                              |
| errors.AutheleteBundledDefaultError           | 4XX, 5XX                                      | \*/\*                                         |

## clientSecretRefreshApi

Refresh the client secret of a client. A new value of the client secret will be generated by the
Authlete server.

If you want to specify a new value, use `/api/client/secret/update` API.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="client_secret_refresh_api" method="get" path="/api/{serviceId}/client/secret/refresh/{clientIdentifier}" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.clientManagement.clientSecretRefreshApi({
    serviceId: "<id>",
    clientIdentifier: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { clientManagementClientSecretRefreshApi } from "authelete-bundled/funcs/clientManagementClientSecretRefreshApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientSecretRefreshApi(autheleteBundled, {
    serviceId: "<id>",
    clientIdentifier: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementClientSecretRefreshApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ClientSecretRefreshApiRequest](../../models/operations/clientsecretrefreshapirequest.md)                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ClientSecretRefreshApiResponse](../../models/operations/clientsecretrefreshapiresponse.md)\>**

### Errors

| Error Type                                       | Status Code                                      | Content Type                                     |
| ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ |
| errors.ClientSecretRefreshApiBadRequestError     | 400                                              | application/json                                 |
| errors.ClientSecretRefreshApiUnauthorizedError   | 401                                              | application/json                                 |
| errors.ClientSecretRefreshApiForbiddenError      | 403                                              | application/json                                 |
| errors.ClientSecretRefreshApiInternalServerError | 500                                              | application/json                                 |
| errors.AutheleteBundledDefaultError              | 4XX, 5XX                                         | \*/\*                                            |

## clientSecretUpdateApi

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
  const result = await autheleteBundled.clientManagement.clientSecretUpdateApi({
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
import { clientManagementClientSecretUpdateApi } from "authelete-bundled/funcs/clientManagementClientSecretUpdateApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientSecretUpdateApi(autheleteBundled, {
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
    console.log("clientManagementClientSecretUpdateApi failed:", res.error);
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

| Error Type                                      | Status Code                                     | Content Type                                    |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| errors.ClientSecretUpdateApiBadRequestError     | 400                                             | application/json                                |
| errors.ClientSecretUpdateApiUnauthorizedError   | 401                                             | application/json                                |
| errors.ClientSecretUpdateApiForbiddenError      | 403                                             | application/json                                |
| errors.ClientSecretUpdateApiInternalServerError | 500                                             | application/json                                |
| errors.AutheleteBundledDefaultError             | 4XX, 5XX                                        | \*/\*                                           |

## clientSecretUpdateApiForm

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
  const result = await autheleteBundled.clientManagement.clientSecretUpdateApiForm({
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
import { clientManagementClientSecretUpdateApiForm } from "authelete-bundled/funcs/clientManagementClientSecretUpdateApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientSecretUpdateApiForm(autheleteBundled, {
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
    console.log("clientManagementClientSecretUpdateApiForm failed:", res.error);
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

| Error Type                                          | Status Code                                         | Content Type                                        |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| errors.ClientSecretUpdateApiFormBadRequestError     | 400                                                 | application/json                                    |
| errors.ClientSecretUpdateApiFormUnauthorizedError   | 401                                                 | application/json                                    |
| errors.ClientSecretUpdateApiFormForbiddenError      | 403                                                 | application/json                                    |
| errors.ClientSecretUpdateApiFormInternalServerError | 500                                                 | application/json                                    |
| errors.AutheleteBundledDefaultError                 | 4XX, 5XX                                            | \*/\*                                               |

## clientAuthorizationGetListApi

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
  const result = await autheleteBundled.clientManagement.clientAuthorizationGetListApi({
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
import { clientManagementClientAuthorizationGetListApi } from "authelete-bundled/funcs/clientManagementClientAuthorizationGetListApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientAuthorizationGetListApi(autheleteBundled, {
    subject: "<value>",
    serviceId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementClientAuthorizationGetListApi failed:", res.error);
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

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| errors.ClientAuthorizationGetListApiBadRequestError     | 400                                                     | application/json                                        |
| errors.ClientAuthorizationGetListApiUnauthorizedError   | 401                                                     | application/json                                        |
| errors.ClientAuthorizationGetListApiForbiddenError      | 403                                                     | application/json                                        |
| errors.ClientAuthorizationGetListApiInternalServerError | 500                                                     | application/json                                        |
| errors.AutheleteBundledDefaultError                     | 4XX, 5XX                                                | \*/\*                                                   |

## clientAuthorizationUpdateApi

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
  const result = await autheleteBundled.clientManagement.clientAuthorizationUpdateApi({
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
import { clientManagementClientAuthorizationUpdateApi } from "authelete-bundled/funcs/clientManagementClientAuthorizationUpdateApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientAuthorizationUpdateApi(autheleteBundled, {
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
    console.log("clientManagementClientAuthorizationUpdateApi failed:", res.error);
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

| Error Type                                             | Status Code                                            | Content Type                                           |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| errors.ClientAuthorizationUpdateApiBadRequestError     | 400                                                    | application/json                                       |
| errors.ClientAuthorizationUpdateApiUnauthorizedError   | 401                                                    | application/json                                       |
| errors.ClientAuthorizationUpdateApiForbiddenError      | 403                                                    | application/json                                       |
| errors.ClientAuthorizationUpdateApiInternalServerError | 500                                                    | application/json                                       |
| errors.AutheleteBundledDefaultError                    | 4XX, 5XX                                               | \*/\*                                                  |

## clientAuthorizationUpdateApiForm

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
  const result = await autheleteBundled.clientManagement.clientAuthorizationUpdateApiForm({
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
import { clientManagementClientAuthorizationUpdateApiForm } from "authelete-bundled/funcs/clientManagementClientAuthorizationUpdateApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientAuthorizationUpdateApiForm(autheleteBundled, {
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
    console.log("clientManagementClientAuthorizationUpdateApiForm failed:", res.error);
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

| Error Type                                                 | Status Code                                                | Content Type                                               |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| errors.ClientAuthorizationUpdateApiFormBadRequestError     | 400                                                        | application/json                                           |
| errors.ClientAuthorizationUpdateApiFormUnauthorizedError   | 401                                                        | application/json                                           |
| errors.ClientAuthorizationUpdateApiFormForbiddenError      | 403                                                        | application/json                                           |
| errors.ClientAuthorizationUpdateApiFormInternalServerError | 500                                                        | application/json                                           |
| errors.AutheleteBundledDefaultError                        | 4XX, 5XX                                                   | \*/\*                                                      |

## clientAuthorizationDeleteApi

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
  const result = await autheleteBundled.clientManagement.clientAuthorizationDeleteApi({
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
import { clientManagementClientAuthorizationDeleteApi } from "authelete-bundled/funcs/clientManagementClientAuthorizationDeleteApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientAuthorizationDeleteApi(autheleteBundled, {
    subject: "<value>",
    serviceId: "<id>",
    clientId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementClientAuthorizationDeleteApi failed:", res.error);
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

| Error Type                                             | Status Code                                            | Content Type                                           |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| errors.ClientAuthorizationDeleteApiBadRequestError     | 400                                                    | application/json                                       |
| errors.ClientAuthorizationDeleteApiUnauthorizedError   | 401                                                    | application/json                                       |
| errors.ClientAuthorizationDeleteApiForbiddenError      | 403                                                    | application/json                                       |
| errors.ClientAuthorizationDeleteApiInternalServerError | 500                                                    | application/json                                       |
| errors.AutheleteBundledDefaultError                    | 4XX, 5XX                                               | \*/\*                                                  |

## clientGrantedScopesGetApi

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
  const result = await autheleteBundled.clientManagement.clientGrantedScopesGetApi({
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
import { clientManagementClientGrantedScopesGetApi } from "authelete-bundled/funcs/clientManagementClientGrantedScopesGetApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientGrantedScopesGetApi(autheleteBundled, {
    subject: "<value>",
    serviceId: "<id>",
    clientId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementClientGrantedScopesGetApi failed:", res.error);
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

| Error Type                                          | Status Code                                         | Content Type                                        |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| errors.ClientGrantedScopesGetApiBadRequestError     | 400                                                 | application/json                                    |
| errors.ClientGrantedScopesGetApiUnauthorizedError   | 401                                                 | application/json                                    |
| errors.ClientGrantedScopesGetApiForbiddenError      | 403                                                 | application/json                                    |
| errors.ClientGrantedScopesGetApiInternalServerError | 500                                                 | application/json                                    |
| errors.AutheleteBundledDefaultError                 | 4XX, 5XX                                            | \*/\*                                               |

## clientGrantedScopesDeleteApi

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
  const result = await autheleteBundled.clientManagement.clientGrantedScopesDeleteApi({
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
import { clientManagementClientGrantedScopesDeleteApi } from "authelete-bundled/funcs/clientManagementClientGrantedScopesDeleteApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientGrantedScopesDeleteApi(autheleteBundled, {
    subject: "<value>",
    serviceId: "<id>",
    clientId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementClientGrantedScopesDeleteApi failed:", res.error);
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

| Error Type                                             | Status Code                                            | Content Type                                           |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| errors.ClientGrantedScopesDeleteApiBadRequestError     | 400                                                    | application/json                                       |
| errors.ClientGrantedScopesDeleteApiUnauthorizedError   | 401                                                    | application/json                                       |
| errors.ClientGrantedScopesDeleteApiForbiddenError      | 403                                                    | application/json                                       |
| errors.ClientGrantedScopesDeleteApiInternalServerError | 500                                                    | application/json                                       |
| errors.AutheleteBundledDefaultError                    | 4XX, 5XX                                               | \*/\*                                                  |

## clientExtensionRequestablesScopesGetApi

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
  const result = await autheleteBundled.clientManagement.clientExtensionRequestablesScopesGetApi({
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
import { clientManagementClientExtensionRequestablesScopesGetApi } from "authelete-bundled/funcs/clientManagementClientExtensionRequestablesScopesGetApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientExtensionRequestablesScopesGetApi(autheleteBundled, {
    serviceId: "<id>",
    clientId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementClientExtensionRequestablesScopesGetApi failed:", res.error);
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

| Error Type                                                        | Status Code                                                       | Content Type                                                      |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| errors.ClientExtensionRequestablesScopesGetApiBadRequestError     | 400                                                               | application/json                                                  |
| errors.ClientExtensionRequestablesScopesGetApiUnauthorizedError   | 401                                                               | application/json                                                  |
| errors.ClientExtensionRequestablesScopesGetApiForbiddenError      | 403                                                               | application/json                                                  |
| errors.ClientExtensionRequestablesScopesGetApiInternalServerError | 500                                                               | application/json                                                  |
| errors.AutheleteBundledDefaultError                               | 4XX, 5XX                                                          | \*/\*                                                             |

## clientExtensionRequestablesScopesUpdateApi

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
  const result = await autheleteBundled.clientManagement.clientExtensionRequestablesScopesUpdateApi({
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
import { clientManagementClientExtensionRequestablesScopesUpdateApi } from "authelete-bundled/funcs/clientManagementClientExtensionRequestablesScopesUpdateApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientExtensionRequestablesScopesUpdateApi(autheleteBundled, {
    serviceId: "<id>",
    clientId: "<id>",
    requestBody: {},
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("clientManagementClientExtensionRequestablesScopesUpdateApi failed:", res.error);
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

| Error Type                                                           | Status Code                                                          | Content Type                                                         |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| errors.ClientExtensionRequestablesScopesUpdateApiBadRequestError     | 400                                                                  | application/json                                                     |
| errors.ClientExtensionRequestablesScopesUpdateApiUnauthorizedError   | 401                                                                  | application/json                                                     |
| errors.ClientExtensionRequestablesScopesUpdateApiForbiddenError      | 403                                                                  | application/json                                                     |
| errors.ClientExtensionRequestablesScopesUpdateApiInternalServerError | 500                                                                  | application/json                                                     |
| errors.AutheleteBundledDefaultError                                  | 4XX, 5XX                                                             | \*/\*                                                                |

## clientExtensionRequestablesScopesDeleteApi

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
  await autheleteBundled.clientManagement.clientExtensionRequestablesScopesDeleteApi({
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
import { clientManagementClientExtensionRequestablesScopesDeleteApi } from "authelete-bundled/funcs/clientManagementClientExtensionRequestablesScopesDeleteApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await clientManagementClientExtensionRequestablesScopesDeleteApi(autheleteBundled, {
    serviceId: "<id>",
    clientId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("clientManagementClientExtensionRequestablesScopesDeleteApi failed:", res.error);
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

| Error Type                                                           | Status Code                                                          | Content Type                                                         |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| errors.ClientExtensionRequestablesScopesDeleteApiBadRequestError     | 400                                                                  | application/json                                                     |
| errors.ClientExtensionRequestablesScopesDeleteApiUnauthorizedError   | 401                                                                  | application/json                                                     |
| errors.ClientExtensionRequestablesScopesDeleteApiForbiddenError      | 403                                                                  | application/json                                                     |
| errors.ClientExtensionRequestablesScopesDeleteApiInternalServerError | 500                                                                  | application/json                                                     |
| errors.AutheleteBundledDefaultError                                  | 4XX, 5XX                                                             | \*/\*                                                                |