# VerifiableCredentialIssuer
(*verifiableCredentialIssuer*)

## Overview

API endpoints for implementing and running a Verifiable Credential Issuer (VCI).

### Available Operations

* [vciMetadataApi](#vcimetadataapi) - /api/{serviceId}/vci/metadata API
* [vciMetadataApiForm](#vcimetadataapiform) - /api/{serviceId}/vci/metadata API
* [vciJwtissuerApi](#vcijwtissuerapi) - /api/{serviceId}/vci/jwtissuer API
* [vciJwtissuerApiForm](#vcijwtissuerapiform) - /api/{serviceId}/vci/jwtissuer API
* [vciJwksApi](#vcijwksapi) - /api/{serviceId}/vci/jwks API
* [vciJwksApiForm](#vcijwksapiform) - /api/{serviceId}/vci/jwks API
* [vciOfferCreateApi](#vcioffercreateapi) - /api/{serviceId}/vci/offer/create API
* [vciOfferCreateApiForm](#vcioffercreateapiform) - /api/{serviceId}/vci/offer/create API
* [vciOfferInfoApi](#vciofferinfoapi) - /api/{serviceId}/vci/offer/info API
* [vciOfferInfoApiForm](#vciofferinfoapiform) - /api/{serviceId}/vci/offer/info API
* [vciSingleParseApi](#vcisingleparseapi) - /api/{serviceId}/vci/single/parse API
* [vciSingleParseApiForm](#vcisingleparseapiform) - /api/{serviceId}/vci/single/parse API
* [vciSingleIssueApi](#vcisingleissueapi) - /api/{serviceId}/vci/single/issue API
* [vciBatchParseApi](#vcibatchparseapi) - /api/{serviceId}/vci/batch/parse API
* [vciBatchParseApiForm](#vcibatchparseapiform) - /api/{serviceId}/vci/batch/parse API
* [vciBatchIssueApi](#vcibatchissueapi) - /api/{serviceId}/vci/batch/issue API
* [vciDeferredParseApi](#vcideferredparseapi) - /api/{serviceId}/vci/deferred/parse API
* [vciDeferredParseApiForm](#vcideferredparseapiform) - /api/{serviceId}/vci/deferred/parse API
* [vciDeferredIssueApi](#vcideferredissueapi) - /api/{serviceId}/vci/deferred/issue API

## vciMetadataApi

/api/{serviceId}/vci/metadata API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_metadata_api" method="post" path="/api/{serviceId}/vci/metadata" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciMetadataApi({
    serviceId: "<id>",
    requestBody: {
      pretty: true,
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
import { verifiableCredentialIssuerVciMetadataApi } from "authelete-bundled/funcs/verifiableCredentialIssuerVciMetadataApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciMetadataApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      pretty: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciMetadataApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciMetadataApiRequest](../../models/operations/vcimetadataapirequest.md)                                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciMetadataApiResponse](../../models/operations/vcimetadataapiresponse.md)\>**

### Errors

| Error Type                               | Status Code                              | Content Type                             |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| errors.VciMetadataApiBadRequestError     | 400                                      | application/json                         |
| errors.VciMetadataApiUnauthorizedError   | 401                                      | application/json                         |
| errors.VciMetadataApiForbiddenError      | 403                                      | application/json                         |
| errors.VciMetadataApiInternalServerError | 500                                      | application/json                         |
| errors.AutheleteBundledDefaultError      | 4XX, 5XX                                 | \*/\*                                    |

## vciMetadataApiForm

/api/{serviceId}/vci/metadata API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_metadata_api_form" method="post" path="/api/{serviceId}/vci/metadata" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciMetadataApiForm({
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
import { verifiableCredentialIssuerVciMetadataApiForm } from "authelete-bundled/funcs/verifiableCredentialIssuerVciMetadataApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciMetadataApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciMetadataApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciMetadataApiFormRequest](../../models/operations/vcimetadataapiformrequest.md)                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciMetadataApiFormResponse](../../models/operations/vcimetadataapiformresponse.md)\>**

### Errors

| Error Type                                   | Status Code                                  | Content Type                                 |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| errors.VciMetadataApiFormBadRequestError     | 400                                          | application/json                             |
| errors.VciMetadataApiFormUnauthorizedError   | 401                                          | application/json                             |
| errors.VciMetadataApiFormForbiddenError      | 403                                          | application/json                             |
| errors.VciMetadataApiFormInternalServerError | 500                                          | application/json                             |
| errors.AutheleteBundledDefaultError          | 4XX, 5XX                                     | \*/\*                                        |

## vciJwtissuerApi

/api/{serviceId}/vci/jwtissuer API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_jwtissuer_api" method="post" path="/api/{serviceId}/vci/jwtissuer" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciJwtissuerApi({
    serviceId: "<id>",
    requestBody: {
      pretty: true,
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
import { verifiableCredentialIssuerVciJwtissuerApi } from "authelete-bundled/funcs/verifiableCredentialIssuerVciJwtissuerApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciJwtissuerApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      pretty: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciJwtissuerApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciJwtissuerApiRequest](../../models/operations/vcijwtissuerapirequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciJwtissuerApiResponse](../../models/operations/vcijwtissuerapiresponse.md)\>**

### Errors

| Error Type                                | Status Code                               | Content Type                              |
| ----------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| errors.VciJwtissuerApiBadRequestError     | 400                                       | application/json                          |
| errors.VciJwtissuerApiUnauthorizedError   | 401                                       | application/json                          |
| errors.VciJwtissuerApiForbiddenError      | 403                                       | application/json                          |
| errors.VciJwtissuerApiInternalServerError | 500                                       | application/json                          |
| errors.AutheleteBundledDefaultError       | 4XX, 5XX                                  | \*/\*                                     |

## vciJwtissuerApiForm

/api/{serviceId}/vci/jwtissuer API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_jwtissuer_api_form" method="post" path="/api/{serviceId}/vci/jwtissuer" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciJwtissuerApiForm({
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
import { verifiableCredentialIssuerVciJwtissuerApiForm } from "authelete-bundled/funcs/verifiableCredentialIssuerVciJwtissuerApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciJwtissuerApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciJwtissuerApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciJwtissuerApiFormRequest](../../models/operations/vcijwtissuerapiformrequest.md)                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciJwtissuerApiFormResponse](../../models/operations/vcijwtissuerapiformresponse.md)\>**

### Errors

| Error Type                                    | Status Code                                   | Content Type                                  |
| --------------------------------------------- | --------------------------------------------- | --------------------------------------------- |
| errors.VciJwtissuerApiFormBadRequestError     | 400                                           | application/json                              |
| errors.VciJwtissuerApiFormUnauthorizedError   | 401                                           | application/json                              |
| errors.VciJwtissuerApiFormForbiddenError      | 403                                           | application/json                              |
| errors.VciJwtissuerApiFormInternalServerError | 500                                           | application/json                              |
| errors.AutheleteBundledDefaultError           | 4XX, 5XX                                      | \*/\*                                         |

## vciJwksApi

/api/{serviceId}/vci/jwks API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_jwks_api" method="post" path="/api/{serviceId}/vci/jwks" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciJwksApi({
    serviceId: "<id>",
    requestBody: {
      pretty: false,
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
import { verifiableCredentialIssuerVciJwksApi } from "authelete-bundled/funcs/verifiableCredentialIssuerVciJwksApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciJwksApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      pretty: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciJwksApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciJwksApiRequest](../../models/operations/vcijwksapirequest.md)                                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciJwksApiResponse](../../models/operations/vcijwksapiresponse.md)\>**

### Errors

| Error Type                           | Status Code                          | Content Type                         |
| ------------------------------------ | ------------------------------------ | ------------------------------------ |
| errors.VciJwksApiBadRequestError     | 400                                  | application/json                     |
| errors.VciJwksApiUnauthorizedError   | 401                                  | application/json                     |
| errors.VciJwksApiForbiddenError      | 403                                  | application/json                     |
| errors.VciJwksApiInternalServerError | 500                                  | application/json                     |
| errors.AutheleteBundledDefaultError  | 4XX, 5XX                             | \*/\*                                |

## vciJwksApiForm

/api/{serviceId}/vci/jwks API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_jwks_api_form" method="post" path="/api/{serviceId}/vci/jwks" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciJwksApiForm({
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
import { verifiableCredentialIssuerVciJwksApiForm } from "authelete-bundled/funcs/verifiableCredentialIssuerVciJwksApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciJwksApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciJwksApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciJwksApiFormRequest](../../models/operations/vcijwksapiformrequest.md)                                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciJwksApiFormResponse](../../models/operations/vcijwksapiformresponse.md)\>**

### Errors

| Error Type                               | Status Code                              | Content Type                             |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| errors.VciJwksApiFormBadRequestError     | 400                                      | application/json                         |
| errors.VciJwksApiFormUnauthorizedError   | 401                                      | application/json                         |
| errors.VciJwksApiFormForbiddenError      | 403                                      | application/json                         |
| errors.VciJwksApiFormInternalServerError | 500                                      | application/json                         |
| errors.AutheleteBundledDefaultError      | 4XX, 5XX                                 | \*/\*                                    |

## vciOfferCreateApi

/api/{serviceId}/vci/offer/create API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_offer_create_api" method="post" path="/api/{serviceId}/vci/offer/create" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciOfferCreateApi({
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
import { verifiableCredentialIssuerVciOfferCreateApi } from "authelete-bundled/funcs/verifiableCredentialIssuerVciOfferCreateApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciOfferCreateApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {},
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciOfferCreateApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciOfferCreateApiRequest](../../models/operations/vcioffercreateapirequest.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciOfferCreateApiResponse](../../models/operations/vcioffercreateapiresponse.md)\>**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| errors.VciOfferCreateApiBadRequestError     | 400                                         | application/json                            |
| errors.VciOfferCreateApiUnauthorizedError   | 401                                         | application/json                            |
| errors.VciOfferCreateApiForbiddenError      | 403                                         | application/json                            |
| errors.VciOfferCreateApiInternalServerError | 500                                         | application/json                            |
| errors.AutheleteBundledDefaultError         | 4XX, 5XX                                    | \*/\*                                       |

## vciOfferCreateApiForm

/api/{serviceId}/vci/offer/create API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_offer_create_api_form" method="post" path="/api/{serviceId}/vci/offer/create" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciOfferCreateApiForm({
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
import { verifiableCredentialIssuerVciOfferCreateApiForm } from "authelete-bundled/funcs/verifiableCredentialIssuerVciOfferCreateApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciOfferCreateApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciOfferCreateApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciOfferCreateApiFormRequest](../../models/operations/vcioffercreateapiformrequest.md)                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciOfferCreateApiFormResponse](../../models/operations/vcioffercreateapiformresponse.md)\>**

### Errors

| Error Type                                      | Status Code                                     | Content Type                                    |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| errors.VciOfferCreateApiFormBadRequestError     | 400                                             | application/json                                |
| errors.VciOfferCreateApiFormUnauthorizedError   | 401                                             | application/json                                |
| errors.VciOfferCreateApiFormForbiddenError      | 403                                             | application/json                                |
| errors.VciOfferCreateApiFormInternalServerError | 500                                             | application/json                                |
| errors.AutheleteBundledDefaultError             | 4XX, 5XX                                        | \*/\*                                           |

## vciOfferInfoApi

/api/{serviceId}/vci/offer/info API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_offer_info_api" method="post" path="/api/{serviceId}/vci/offer/info" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciOfferInfoApi({
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
import { verifiableCredentialIssuerVciOfferInfoApi } from "authelete-bundled/funcs/verifiableCredentialIssuerVciOfferInfoApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciOfferInfoApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {},
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciOfferInfoApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciOfferInfoApiRequest](../../models/operations/vciofferinfoapirequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciOfferInfoApiResponse](../../models/operations/vciofferinfoapiresponse.md)\>**

### Errors

| Error Type                                | Status Code                               | Content Type                              |
| ----------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| errors.VciOfferInfoApiBadRequestError     | 400                                       | application/json                          |
| errors.VciOfferInfoApiUnauthorizedError   | 401                                       | application/json                          |
| errors.VciOfferInfoApiForbiddenError      | 403                                       | application/json                          |
| errors.VciOfferInfoApiInternalServerError | 500                                       | application/json                          |
| errors.AutheleteBundledDefaultError       | 4XX, 5XX                                  | \*/\*                                     |

## vciOfferInfoApiForm

/api/{serviceId}/vci/offer/info API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_offer_info_api_form" method="post" path="/api/{serviceId}/vci/offer/info" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciOfferInfoApiForm({
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
import { verifiableCredentialIssuerVciOfferInfoApiForm } from "authelete-bundled/funcs/verifiableCredentialIssuerVciOfferInfoApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciOfferInfoApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciOfferInfoApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciOfferInfoApiFormRequest](../../models/operations/vciofferinfoapiformrequest.md)                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciOfferInfoApiFormResponse](../../models/operations/vciofferinfoapiformresponse.md)\>**

### Errors

| Error Type                                    | Status Code                                   | Content Type                                  |
| --------------------------------------------- | --------------------------------------------- | --------------------------------------------- |
| errors.VciOfferInfoApiFormBadRequestError     | 400                                           | application/json                              |
| errors.VciOfferInfoApiFormUnauthorizedError   | 401                                           | application/json                              |
| errors.VciOfferInfoApiFormForbiddenError      | 403                                           | application/json                              |
| errors.VciOfferInfoApiFormInternalServerError | 500                                           | application/json                              |
| errors.AutheleteBundledDefaultError           | 4XX, 5XX                                      | \*/\*                                         |

## vciSingleParseApi

/api/{serviceId}/vci/single/parse API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_single_parse_api" method="post" path="/api/{serviceId}/vci/single/parse" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciSingleParseApi({
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
import { verifiableCredentialIssuerVciSingleParseApi } from "authelete-bundled/funcs/verifiableCredentialIssuerVciSingleParseApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciSingleParseApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {},
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciSingleParseApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciSingleParseApiRequest](../../models/operations/vcisingleparseapirequest.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciSingleParseApiResponse](../../models/operations/vcisingleparseapiresponse.md)\>**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| errors.VciSingleParseApiBadRequestError     | 400                                         | application/json                            |
| errors.VciSingleParseApiUnauthorizedError   | 401                                         | application/json                            |
| errors.VciSingleParseApiForbiddenError      | 403                                         | application/json                            |
| errors.VciSingleParseApiInternalServerError | 500                                         | application/json                            |
| errors.AutheleteBundledDefaultError         | 4XX, 5XX                                    | \*/\*                                       |

## vciSingleParseApiForm

/api/{serviceId}/vci/single/parse API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_single_parse_api_form" method="post" path="/api/{serviceId}/vci/single/parse" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciSingleParseApiForm({
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
import { verifiableCredentialIssuerVciSingleParseApiForm } from "authelete-bundled/funcs/verifiableCredentialIssuerVciSingleParseApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciSingleParseApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciSingleParseApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciSingleParseApiFormRequest](../../models/operations/vcisingleparseapiformrequest.md)                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciSingleParseApiFormResponse](../../models/operations/vcisingleparseapiformresponse.md)\>**

### Errors

| Error Type                                      | Status Code                                     | Content Type                                    |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| errors.VciSingleParseApiFormBadRequestError     | 400                                             | application/json                                |
| errors.VciSingleParseApiFormUnauthorizedError   | 401                                             | application/json                                |
| errors.VciSingleParseApiFormForbiddenError      | 403                                             | application/json                                |
| errors.VciSingleParseApiFormInternalServerError | 500                                             | application/json                                |
| errors.AutheleteBundledDefaultError             | 4XX, 5XX                                        | \*/\*                                           |

## vciSingleIssueApi

/api/{serviceId}/vci/single/issue API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_single_issue_api" method="post" path="/api/{serviceId}/vci/single/issue" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciSingleIssueApi({
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
import { verifiableCredentialIssuerVciSingleIssueApi } from "authelete-bundled/funcs/verifiableCredentialIssuerVciSingleIssueApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciSingleIssueApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {},
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciSingleIssueApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciSingleIssueApiRequest](../../models/operations/vcisingleissueapirequest.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciSingleIssueApiResponse](../../models/operations/vcisingleissueapiresponse.md)\>**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| errors.VciSingleIssueApiBadRequestError     | 400                                         | application/json                            |
| errors.VciSingleIssueApiUnauthorizedError   | 401                                         | application/json                            |
| errors.VciSingleIssueApiForbiddenError      | 403                                         | application/json                            |
| errors.VciSingleIssueApiInternalServerError | 500                                         | application/json                            |
| errors.AutheleteBundledDefaultError         | 4XX, 5XX                                    | \*/\*                                       |

## vciBatchParseApi

/api/{serviceId}/vci/batch/parse API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_batch_parse_api" method="post" path="/api/{serviceId}/vci/batch/parse" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciBatchParseApi({
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
import { verifiableCredentialIssuerVciBatchParseApi } from "authelete-bundled/funcs/verifiableCredentialIssuerVciBatchParseApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciBatchParseApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {},
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciBatchParseApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciBatchParseApiRequest](../../models/operations/vcibatchparseapirequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciBatchParseApiResponse](../../models/operations/vcibatchparseapiresponse.md)\>**

### Errors

| Error Type                                 | Status Code                                | Content Type                               |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| errors.VciBatchParseApiBadRequestError     | 400                                        | application/json                           |
| errors.VciBatchParseApiUnauthorizedError   | 401                                        | application/json                           |
| errors.VciBatchParseApiForbiddenError      | 403                                        | application/json                           |
| errors.VciBatchParseApiInternalServerError | 500                                        | application/json                           |
| errors.AutheleteBundledDefaultError        | 4XX, 5XX                                   | \*/\*                                      |

## vciBatchParseApiForm

/api/{serviceId}/vci/batch/parse API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_batch_parse_api_form" method="post" path="/api/{serviceId}/vci/batch/parse" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciBatchParseApiForm({
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
import { verifiableCredentialIssuerVciBatchParseApiForm } from "authelete-bundled/funcs/verifiableCredentialIssuerVciBatchParseApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciBatchParseApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciBatchParseApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciBatchParseApiFormRequest](../../models/operations/vcibatchparseapiformrequest.md)                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciBatchParseApiFormResponse](../../models/operations/vcibatchparseapiformresponse.md)\>**

### Errors

| Error Type                                     | Status Code                                    | Content Type                                   |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| errors.VciBatchParseApiFormBadRequestError     | 400                                            | application/json                               |
| errors.VciBatchParseApiFormUnauthorizedError   | 401                                            | application/json                               |
| errors.VciBatchParseApiFormForbiddenError      | 403                                            | application/json                               |
| errors.VciBatchParseApiFormInternalServerError | 500                                            | application/json                               |
| errors.AutheleteBundledDefaultError            | 4XX, 5XX                                       | \*/\*                                          |

## vciBatchIssueApi

/api/{serviceId}/vci/batch/issue API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_batch_issue_api" method="post" path="/api/{serviceId}/vci/batch/issue" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciBatchIssueApi({
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
import { verifiableCredentialIssuerVciBatchIssueApi } from "authelete-bundled/funcs/verifiableCredentialIssuerVciBatchIssueApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciBatchIssueApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {},
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciBatchIssueApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciBatchIssueApiRequest](../../models/operations/vcibatchissueapirequest.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciBatchIssueApiResponse](../../models/operations/vcibatchissueapiresponse.md)\>**

### Errors

| Error Type                                 | Status Code                                | Content Type                               |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| errors.VciBatchIssueApiBadRequestError     | 400                                        | application/json                           |
| errors.VciBatchIssueApiUnauthorizedError   | 401                                        | application/json                           |
| errors.VciBatchIssueApiForbiddenError      | 403                                        | application/json                           |
| errors.VciBatchIssueApiInternalServerError | 500                                        | application/json                           |
| errors.AutheleteBundledDefaultError        | 4XX, 5XX                                   | \*/\*                                      |

## vciDeferredParseApi

/api/{serviceId}/vci/deferred/parse API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_deferred_parse_api" method="post" path="/api/{serviceId}/vci/deferred/parse" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciDeferredParseApi({
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
import { verifiableCredentialIssuerVciDeferredParseApi } from "authelete-bundled/funcs/verifiableCredentialIssuerVciDeferredParseApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciDeferredParseApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {},
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciDeferredParseApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciDeferredParseApiRequest](../../models/operations/vcideferredparseapirequest.md)                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciDeferredParseApiResponse](../../models/operations/vcideferredparseapiresponse.md)\>**

### Errors

| Error Type                                    | Status Code                                   | Content Type                                  |
| --------------------------------------------- | --------------------------------------------- | --------------------------------------------- |
| errors.VciDeferredParseApiBadRequestError     | 400                                           | application/json                              |
| errors.VciDeferredParseApiUnauthorizedError   | 401                                           | application/json                              |
| errors.VciDeferredParseApiForbiddenError      | 403                                           | application/json                              |
| errors.VciDeferredParseApiInternalServerError | 500                                           | application/json                              |
| errors.AutheleteBundledDefaultError           | 4XX, 5XX                                      | \*/\*                                         |

## vciDeferredParseApiForm

/api/{serviceId}/vci/deferred/parse API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_deferred_parse_api_form" method="post" path="/api/{serviceId}/vci/deferred/parse" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciDeferredParseApiForm({
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
import { verifiableCredentialIssuerVciDeferredParseApiForm } from "authelete-bundled/funcs/verifiableCredentialIssuerVciDeferredParseApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciDeferredParseApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciDeferredParseApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciDeferredParseApiFormRequest](../../models/operations/vcideferredparseapiformrequest.md)                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciDeferredParseApiFormResponse](../../models/operations/vcideferredparseapiformresponse.md)\>**

### Errors

| Error Type                                        | Status Code                                       | Content Type                                      |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| errors.VciDeferredParseApiFormBadRequestError     | 400                                               | application/json                                  |
| errors.VciDeferredParseApiFormUnauthorizedError   | 401                                               | application/json                                  |
| errors.VciDeferredParseApiFormForbiddenError      | 403                                               | application/json                                  |
| errors.VciDeferredParseApiFormInternalServerError | 500                                               | application/json                                  |
| errors.AutheleteBundledDefaultError               | 4XX, 5XX                                          | \*/\*                                             |

## vciDeferredIssueApi

/api/{serviceId}/vci/deferred/issue API

### Example Usage

<!-- UsageSnippet language="typescript" operationID="vci_deferred_issue_api" method="post" path="/api/{serviceId}/vci/deferred/issue" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.verifiableCredentialIssuer.vciDeferredIssueApi({
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
import { verifiableCredentialIssuerVciDeferredIssueApi } from "authelete-bundled/funcs/verifiableCredentialIssuerVciDeferredIssueApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await verifiableCredentialIssuerVciDeferredIssueApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {},
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("verifiableCredentialIssuerVciDeferredIssueApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VciDeferredIssueApiRequest](../../models/operations/vcideferredissueapirequest.md)                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.VciDeferredIssueApiResponse](../../models/operations/vcideferredissueapiresponse.md)\>**

### Errors

| Error Type                                    | Status Code                                   | Content Type                                  |
| --------------------------------------------- | --------------------------------------------- | --------------------------------------------- |
| errors.VciDeferredIssueApiBadRequestError     | 400                                           | application/json                              |
| errors.VciDeferredIssueApiUnauthorizedError   | 401                                           | application/json                              |
| errors.VciDeferredIssueApiForbiddenError      | 403                                           | application/json                              |
| errors.VciDeferredIssueApiInternalServerError | 500                                           | application/json                              |
| errors.AutheleteBundledDefaultError           | 4XX, 5XX                                      | \*/\*                                         |