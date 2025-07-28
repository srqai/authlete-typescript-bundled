# ServiceManagement
(*serviceManagement*)

## Overview

API endpoints for managing services, including creation, update, and deletion of services.

### Available Operations

* [serviceGetApi](#servicegetapi) - Get Service
* [serviceGetListApi](#servicegetlistapi) - List Services
* [serviceCreateApi](#servicecreateapi) - Create Service
* [serviceUpdateApi](#serviceupdateapi) - Update Service
* [serviceDeleteApi](#servicedeleteapi) - Delete Service ⚡
* [serviceConfigurationApi](#serviceconfigurationapi) - Get Service Configuration

## serviceGetApi

Get a service.

If the access token can only view or modify clients underneath this service, but does not
have access to view this service directly, a limited view of the service will be returned.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="service_get_api" method="get" path="/api/{serviceId}/service/get" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.serviceManagement.serviceGetApi({
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
import { serviceManagementServiceGetApi } from "authelete-bundled/funcs/serviceManagementServiceGetApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await serviceManagementServiceGetApi(autheleteBundled, {
    serviceId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serviceManagementServiceGetApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ServiceGetApiRequest](../../models/operations/servicegetapirequest.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ServiceGetApiResponse](../../models/operations/servicegetapiresponse.md)\>**

### Errors

| Error Type                              | Status Code                             | Content Type                            |
| --------------------------------------- | --------------------------------------- | --------------------------------------- |
| errors.ServiceGetApiBadRequestError     | 400                                     | application/json                        |
| errors.ServiceGetApiUnauthorizedError   | 401                                     | application/json                        |
| errors.ServiceGetApiForbiddenError      | 403                                     | application/json                        |
| errors.ServiceGetApiInternalServerError | 500                                     | application/json                        |
| errors.AutheleteBundledDefaultError     | 4XX, 5XX                                | \*/\*                                   |

## serviceGetListApi

Get a list of services.

If the access token can only view or modify clients underneath a service, but does not
have access to view that service directly, a limited view of the service will be returned.
Otherwise, all properties of the service are returned.

If the access token is an administrative token, this returns a list of all services on the Authlete instance.
Otherwise, all services that the access token can view, even in a limited fashion, are returned.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="service_get_list_api" method="get" path="/api/service/get/list" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.serviceManagement.serviceGetListApi();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { serviceManagementServiceGetListApi } from "authelete-bundled/funcs/serviceManagementServiceGetListApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await serviceManagementServiceGetListApi(autheleteBundled);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serviceManagementServiceGetListApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ServiceGetListApiRequest](../../models/operations/servicegetlistapirequest.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ServiceGetListApiResponse](../../models/operations/servicegetlistapiresponse.md)\>**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| errors.ServiceGetListApiBadRequestError     | 400                                         | application/json                            |
| errors.ServiceGetListApiUnauthorizedError   | 401                                         | application/json                            |
| errors.ServiceGetListApiForbiddenError      | 403                                         | application/json                            |
| errors.ServiceGetListApiInternalServerError | 500                                         | application/json                            |
| errors.AutheleteBundledDefaultError         | 4XX, 5XX                                    | \*/\*                                       |

## serviceCreateApi

Create a new service.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="service_create_api" method="post" path="/api/service/create" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.serviceManagement.serviceCreateApi({
    serviceName: "My service",
    issuer: "https://my-service.example.com",
    clientIdAliasEnabled: true,
    supportedGrantTypes: [
      "AUTHORIZATION_CODE",
      "REFRESH_TOKEN",
    ],
    supportedResponseTypes: [
      "CODE",
    ],
    authorizationEndpoint: "https://my-service.example.com/authz",
    pkceRequired: true,
    tokenEndpoint: "https://my-service.example.com/token",
    supportedTokenAuthMethods: [
      "CLIENT_SECRET_BASIC",
    ],
    revocationEndpoint: "https://my-service.example.com/revocation",
    supportedRevocationAuthMethods: [
      "CLIENT_SECRET_BASIC",
    ],
    introspectionEndpoint: "https://my-service.example.com/introspection",
    supportedIntrospectionAuthMethods: [
      "CLIENT_SECRET_BASIC",
    ],
    accessTokenType: "Bearer",
    accessTokenDuration: 3600,
    refreshTokenDuration: 3600,
    supportedScopes: [
      {
        name: "timeline.read",
        defaultEntry: false,
        description: "A permission to read your timeline.",
      },
      {
        name: "history.read",
        defaultEntry: false,
        description: "A permission to read your history.",
      },
    ],
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
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { serviceManagementServiceCreateApi } from "authelete-bundled/funcs/serviceManagementServiceCreateApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await serviceManagementServiceCreateApi(autheleteBundled, {
    serviceName: "My service",
    issuer: "https://my-service.example.com",
    clientIdAliasEnabled: true,
    supportedGrantTypes: [
      "AUTHORIZATION_CODE",
      "REFRESH_TOKEN",
    ],
    supportedResponseTypes: [
      "CODE",
    ],
    authorizationEndpoint: "https://my-service.example.com/authz",
    pkceRequired: true,
    tokenEndpoint: "https://my-service.example.com/token",
    supportedTokenAuthMethods: [
      "CLIENT_SECRET_BASIC",
    ],
    revocationEndpoint: "https://my-service.example.com/revocation",
    supportedRevocationAuthMethods: [
      "CLIENT_SECRET_BASIC",
    ],
    introspectionEndpoint: "https://my-service.example.com/introspection",
    supportedIntrospectionAuthMethods: [
      "CLIENT_SECRET_BASIC",
    ],
    accessTokenType: "Bearer",
    accessTokenDuration: 3600,
    refreshTokenDuration: 3600,
    supportedScopes: [
      {
        name: "timeline.read",
        defaultEntry: false,
        description: "A permission to read your timeline.",
      },
      {
        name: "history.read",
        defaultEntry: false,
        description: "A permission to read your history.",
      },
    ],
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
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serviceManagementServiceCreateApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ServiceCreateApiRequest](../../models/operations/servicecreateapirequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ServiceCreateApiResponse](../../models/operations/servicecreateapiresponse.md)\>**

### Errors

| Error Type                                 | Status Code                                | Content Type                               |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| errors.ServiceCreateApiBadRequestError     | 400                                        | application/json                           |
| errors.ServiceCreateApiUnauthorizedError   | 401                                        | application/json                           |
| errors.ServiceCreateApiForbiddenError      | 403                                        | application/json                           |
| errors.ServiceCreateApiInternalServerError | 500                                        | application/json                           |
| errors.AutheleteBundledDefaultError        | 4XX, 5XX                                   | \*/\*                                      |

## serviceUpdateApi

Update a service.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="service_update_api" method="post" path="/api/{serviceId}/service/update" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.serviceManagement.serviceUpdateApi({
    serviceId: "<id>",
    requestBody: {
      serviceName: "My updated service",
      issuer: "https://my-service.example.com",
      clientIdAliasEnabled: true,
      supportedGrantTypes: [
        "AUTHORIZATION_CODE",
        "REFRESH_TOKEN",
      ],
      supportedResponseTypes: [
        "CODE",
      ],
      errorDescriptionOmitted: false,
      errorUriOmitted: false,
      authorizationEndpoint: "https://my-service.example.com/authz",
      directAuthorizationEndpointEnabled: false,
      supportedDisplays: [
        "PAGE",
      ],
      pkceRequired: true,
      pkceS256Required: false,
      authorizationResponseDuration: 0,
      tokenEndpoint: "https://my-service.example.com/token",
      directTokenEndpointEnabled: false,
      supportedTokenAuthMethods: [
        "CLIENT_SECRET_BASIC",
      ],
      missingClientIdAllowed: false,
      revocationEndpoint: "https://my-service.example.com/revocation",
      directRevocationEndpointEnabled: false,
      supportedRevocationAuthMethods: [
        "CLIENT_SECRET_BASIC",
      ],
      introspectionEndpoint: "https://my-service.example.com/introspection",
      directIntrospectionEndpointEnabled: false,
      supportedIntrospectionAuthMethods: [
        "CLIENT_SECRET_BASIC",
      ],
      pushedAuthReqDuration: 0,
      parRequired: false,
      requestObjectRequired: false,
      traditionalRequestObjectProcessingApplied: false,
      mutualTlsValidatePkiCertChain: false,
      accessTokenType: "Bearer",
      tlsClientCertificateBoundAccessTokens: false,
      accessTokenDuration: 3600,
      singleAccessTokenPerSubject: false,
      refreshTokenDuration: 3600,
      refreshTokenDurationKept: false,
      refreshTokenDurationReset: false,
      refreshTokenKept: false,
      supportedScopes: [
        {
          name: "history.read",
          defaultEntry: false,
          description: "A permission to read your history.",
        },
        {
          name: "timeline.read",
          defaultEntry: false,
          description: "A permission to read your timeline.",
        },
      ],
      scopeRequired: false,
      idTokenDuration: 0,
      allowableClockSkew: 0,
      supportedClaimTypes: [
        "NORMAL",
      ],
      claimShortcutRestrictive: false,
      directJwksEndpointEnabled: false,
      directUserInfoEndpointEnabled: false,
      dynamicRegistrationSupported: false,
      backchannelAuthReqIdDuration: 0,
      backchannelPollingInterval: 0,
      backchannelUserCodeParameterSupported: false,
      backchannelBindingMessageRequiredInFapi: false,
      deviceFlowCodeDuration: 0,
      deviceFlowPollingInterval: 0,
      userCodeLength: 0,
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
      nbfOptional: false,
      issSuppressed: false,
      tokenExpirationLinked: false,
      frontChannelRequestObjectEncryptionRequired: false,
      requestObjectEncryptionAlgMatchRequired: false,
      requestObjectEncryptionEncMatchRequired: false,
      hsmEnabled: false,
      grantManagementActionRequired: false,
      unauthorizedOnClientConfigSupported: false,
      dcrScopeUsedAsRequestable: false,
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
import { serviceManagementServiceUpdateApi } from "authelete-bundled/funcs/serviceManagementServiceUpdateApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await serviceManagementServiceUpdateApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      serviceName: "My updated service",
      issuer: "https://my-service.example.com",
      clientIdAliasEnabled: true,
      supportedGrantTypes: [
        "AUTHORIZATION_CODE",
        "REFRESH_TOKEN",
      ],
      supportedResponseTypes: [
        "CODE",
      ],
      errorDescriptionOmitted: false,
      errorUriOmitted: false,
      authorizationEndpoint: "https://my-service.example.com/authz",
      directAuthorizationEndpointEnabled: false,
      supportedDisplays: [
        "PAGE",
      ],
      pkceRequired: true,
      pkceS256Required: false,
      authorizationResponseDuration: 0,
      tokenEndpoint: "https://my-service.example.com/token",
      directTokenEndpointEnabled: false,
      supportedTokenAuthMethods: [
        "CLIENT_SECRET_BASIC",
      ],
      missingClientIdAllowed: false,
      revocationEndpoint: "https://my-service.example.com/revocation",
      directRevocationEndpointEnabled: false,
      supportedRevocationAuthMethods: [
        "CLIENT_SECRET_BASIC",
      ],
      introspectionEndpoint: "https://my-service.example.com/introspection",
      directIntrospectionEndpointEnabled: false,
      supportedIntrospectionAuthMethods: [
        "CLIENT_SECRET_BASIC",
      ],
      pushedAuthReqDuration: 0,
      parRequired: false,
      requestObjectRequired: false,
      traditionalRequestObjectProcessingApplied: false,
      mutualTlsValidatePkiCertChain: false,
      accessTokenType: "Bearer",
      tlsClientCertificateBoundAccessTokens: false,
      accessTokenDuration: 3600,
      singleAccessTokenPerSubject: false,
      refreshTokenDuration: 3600,
      refreshTokenDurationKept: false,
      refreshTokenDurationReset: false,
      refreshTokenKept: false,
      supportedScopes: [
        {
          name: "history.read",
          defaultEntry: false,
          description: "A permission to read your history.",
        },
        {
          name: "timeline.read",
          defaultEntry: false,
          description: "A permission to read your timeline.",
        },
      ],
      scopeRequired: false,
      idTokenDuration: 0,
      allowableClockSkew: 0,
      supportedClaimTypes: [
        "NORMAL",
      ],
      claimShortcutRestrictive: false,
      directJwksEndpointEnabled: false,
      directUserInfoEndpointEnabled: false,
      dynamicRegistrationSupported: false,
      backchannelAuthReqIdDuration: 0,
      backchannelPollingInterval: 0,
      backchannelUserCodeParameterSupported: false,
      backchannelBindingMessageRequiredInFapi: false,
      deviceFlowCodeDuration: 0,
      deviceFlowPollingInterval: 0,
      userCodeLength: 0,
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
      nbfOptional: false,
      issSuppressed: false,
      tokenExpirationLinked: false,
      frontChannelRequestObjectEncryptionRequired: false,
      requestObjectEncryptionAlgMatchRequired: false,
      requestObjectEncryptionEncMatchRequired: false,
      hsmEnabled: false,
      grantManagementActionRequired: false,
      unauthorizedOnClientConfigSupported: false,
      dcrScopeUsedAsRequestable: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serviceManagementServiceUpdateApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ServiceUpdateApiRequest](../../models/operations/serviceupdateapirequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ServiceUpdateApiResponse](../../models/operations/serviceupdateapiresponse.md)\>**

### Errors

| Error Type                                 | Status Code                                | Content Type                               |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| errors.ServiceUpdateApiBadRequestError     | 400                                        | application/json                           |
| errors.ServiceUpdateApiUnauthorizedError   | 401                                        | application/json                           |
| errors.ServiceUpdateApiForbiddenError      | 403                                        | application/json                           |
| errors.ServiceUpdateApiInternalServerError | 500                                        | application/json                           |
| errors.AutheleteBundledDefaultError        | 4XX, 5XX                                   | \*/\*                                      |

## serviceDeleteApi

Delete a service.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="service_delete_api" method="delete" path="/api/{serviceId}/service/delete" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  await autheleteBundled.serviceManagement.serviceDeleteApi({
    serviceId: "<id>",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AutheleteBundledCore } from "authelete-bundled/core.js";
import { serviceManagementServiceDeleteApi } from "authelete-bundled/funcs/serviceManagementServiceDeleteApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await serviceManagementServiceDeleteApi(autheleteBundled, {
    serviceId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("serviceManagementServiceDeleteApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ServiceDeleteApiRequest](../../models/operations/servicedeleteapirequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<void\>**

### Errors

| Error Type                                 | Status Code                                | Content Type                               |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| errors.ServiceDeleteApiBadRequestError     | 400                                        | application/json                           |
| errors.ServiceDeleteApiUnauthorizedError   | 401                                        | application/json                           |
| errors.ServiceDeleteApiForbiddenError      | 403                                        | application/json                           |
| errors.ServiceDeleteApiInternalServerError | 500                                        | application/json                           |
| errors.AutheleteBundledDefaultError        | 4XX, 5XX                                   | \*/\*                                      |

## serviceConfigurationApi

This API gathers configuration information about a service.

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from within the implementation of the configuration endpoint of
the service where the service that supports OpenID Connect and [OpenID Connect Discovery 1.0](https://openid.net/specs/openid-connect-discovery-1_0.html)
must expose its configuration information in a JSON format. Details about the format are described
in "[3. OpenID Provider Metadata](https://openid.net/specs/openid-connect-discovery-1_0.html#ProviderMetadata)"
in OpenID Connect Discovery 1.0.

</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="service_configuration_api" method="get" path="/api/{serviceId}/service/configuration" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.serviceManagement.serviceConfigurationApi({
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
import { serviceManagementServiceConfigurationApi } from "authelete-bundled/funcs/serviceManagementServiceConfigurationApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await serviceManagementServiceConfigurationApi(autheleteBundled, {
    serviceId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("serviceManagementServiceConfigurationApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ServiceConfigurationApiRequest](../../models/operations/serviceconfigurationapirequest.md)                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.ServiceConfigurationApiResponse](../../models/operations/serviceconfigurationapiresponse.md)\>**

### Errors

| Error Type                                        | Status Code                                       | Content Type                                      |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| errors.ServiceConfigurationApiBadRequestError     | 400                                               | application/json                                  |
| errors.ServiceConfigurationApiUnauthorizedError   | 401                                               | application/json                                  |
| errors.ServiceConfigurationApiForbiddenError      | 403                                               | application/json                                  |
| errors.ServiceConfigurationApiInternalServerError | 500                                               | application/json                                  |
| errors.AutheleteBundledDefaultError               | 4XX, 5XX                                          | \*/\*                                             |