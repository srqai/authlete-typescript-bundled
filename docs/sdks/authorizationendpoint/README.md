# AuthorizationEndpoint
(*authorizationEndpoint*)

## Overview

### Available Operations

* [failRequest](#failrequest) - Fail Authorization Request
* [failRequestForm](#failrequestform) - Fail Authorization Request
* [issue](#issue) - Issue Authorization Response
* [issueForm](#issueform) - Issue Authorization Response
* [getTicketInfo](#getticketinfo) - Get Ticket Information
* [updateTicket](#updateticket) - Update Ticket Information
* [updateTicketForm](#updateticketform) - Update Ticket Information

## failRequest

This API generates a content of an error authorization response that the authorization server implementation
returns to the client application.

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from within the implementation of the authorization endpoint of the service
in order to generate an error response to the client application.

The description of the `/auth/authorization` API describes the timing when this API should be called.

The response from `/auth/authorization/fail` API has some parameters.
Among them, it is `action` parameter that the authorization server implementation should check first because
it denotes the next action that the authorization server implementation should take.
According to the value of `action`, the authorization server implementation must take the steps described below.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the request from the authorization
server implementation was wrong or that an error occurred in Authlete.

In either case, from the viewpoint of the client application, it is an error on the server side.
Therefore, the service implementation should generate a response to the client application with
HTTP status of "500 Internal Server Error". Authlete recommends `application/json` as the content type.

The value of `responseContent` is a JSON string which describes the error, so it can be used
as the entity body of the response.

The following illustrates the response which the service implementation should generate and return
to the client application.

```
HTTP/1.1 500 Internal Server Error
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client application since
"500 Internal Server Error" is not required by OAuth 2.0.

**BAD_REQUEST**

When the value of `action` is `BAD_REQUEST`, it means that the ticket is no longer valid (deleted
or expired) and that the reason of the invalidity was probably due to the end-user's too-delayed
response to the authorization UI.

A response with HTTP status of "400 Bad Request" should be returned to the client application and
Authlete recommends `application/json` as the content type.

The value of `responseContent` is a JSON string which describes the error, so it can be used
as the entity body of the response.

The following illustrates the response which the service implementation should generate and return
to the client application.

```
HTTP/1.1 400 Bad Request
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client application since
"400 Bad Request" is not required by OAuth 2.0.

**LOCATION**

When the value of `action` is `LOCATION`, it means that the response to the client application must
be "302 Found" with Location header.

The parameter responseContent contains a redirect URI with (1) an authorization code, an ID token
and/or an access token (on success) or (2) an error code (on failure), so it can be used as the
value of `Location` header.

The following illustrates the response which the service implementation must generate and return
to the client application.

```
HTTP/1.1 302 Found
Location: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**FORM**

When the value of `action` is `FORM`, it means that the response to the client application must be 200 OK
with an HTML which triggers redirection by JavaScript.
This happens when the authorization request from the client application contained `response_mode=form_post`.

The value of `responseContent` is an HTML which can be used as the entity body of the response.

The following illustrates the response which the service implementation must generate and return
to the client application.

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_authorization_fail_api" method="post" path="/api/{serviceId}/auth/authorization/fail" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.authorizationEndpoint.failRequest({
    serviceId: "<id>",
    requestBody: {
      ticket: "qA7wGybwArICpbUSutrf5Xc9-i1fHE0ySOHxR1eBoBQ",
      reason: "NOT_AUTHENTICATED",
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
import { authorizationEndpointFailRequest } from "authelete-bundled/funcs/authorizationEndpointFailRequest.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await authorizationEndpointFailRequest(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      ticket: "qA7wGybwArICpbUSutrf5Xc9-i1fHE0ySOHxR1eBoBQ",
      reason: "NOT_AUTHENTICATED",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("authorizationEndpointFailRequest failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthAuthorizationFailApiRequest](../../models/operations/authauthorizationfailapirequest.md)                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthAuthorizationFailApiResponse](../../models/operations/authauthorizationfailapiresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## failRequestForm

This API generates a content of an error authorization response that the authorization server implementation
returns to the client application.

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from within the implementation of the authorization endpoint of the service
in order to generate an error response to the client application.

The description of the `/auth/authorization` API describes the timing when this API should be called.

The response from `/auth/authorization/fail` API has some parameters.
Among them, it is `action` parameter that the authorization server implementation should check first because
it denotes the next action that the authorization server implementation should take.
According to the value of `action`, the authorization server implementation must take the steps described below.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the request from the authorization
server implementation was wrong or that an error occurred in Authlete.

In either case, from the viewpoint of the client application, it is an error on the server side.
Therefore, the service implementation should generate a response to the client application with
HTTP status of "500 Internal Server Error". Authlete recommends `application/json` as the content type.

The value of `responseContent` is a JSON string which describes the error, so it can be used
as the entity body of the response.

The following illustrates the response which the service implementation should generate and return
to the client application.

```
HTTP/1.1 500 Internal Server Error
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client application since
"500 Internal Server Error" is not required by OAuth 2.0.

**BAD_REQUEST**

When the value of `action` is `BAD_REQUEST`, it means that the ticket is no longer valid (deleted
or expired) and that the reason of the invalidity was probably due to the end-user's too-delayed
response to the authorization UI.

A response with HTTP status of "400 Bad Request" should be returned to the client application and
Authlete recommends `application/json` as the content type.

The value of `responseContent` is a JSON string which describes the error, so it can be used
as the entity body of the response.

The following illustrates the response which the service implementation should generate and return
to the client application.

```
HTTP/1.1 400 Bad Request
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client application since
"400 Bad Request" is not required by OAuth 2.0.

**LOCATION**

When the value of `action` is `LOCATION`, it means that the response to the client application must
be "302 Found" with Location header.

The parameter responseContent contains a redirect URI with (1) an authorization code, an ID token
and/or an access token (on success) or (2) an error code (on failure), so it can be used as the
value of `Location` header.

The following illustrates the response which the service implementation must generate and return
to the client application.

```
HTTP/1.1 302 Found
Location: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**FORM**

When the value of `action` is `FORM`, it means that the response to the client application must be 200 OK
with an HTML which triggers redirection by JavaScript.
This happens when the authorization request from the client application contained `response_mode=form_post`.

The value of `responseContent` is an HTML which can be used as the entity body of the response.

The following illustrates the response which the service implementation must generate and return
to the client application.

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_authorization_fail_api_form" method="post" path="/api/{serviceId}/auth/authorization/fail" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.authorizationEndpoint.failRequestForm({
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
import { authorizationEndpointFailRequestForm } from "authelete-bundled/funcs/authorizationEndpointFailRequestForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await authorizationEndpointFailRequestForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("authorizationEndpointFailRequestForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthAuthorizationFailApiFormRequest](../../models/operations/authauthorizationfailapiformrequest.md)                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthAuthorizationFailApiFormResponse](../../models/operations/authauthorizationfailapiformresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## issue

This API parses request parameters of an authorization request and returns necessary data for the
authorization server implementation to process the authorization request further.

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from within the implementation of the authorization endpoint of
the service in order to generate a successful response to the client application.

The description of the `/auth/authorization` API describes the timing when this API should be called
and the meaning of request parameters. See [ISSUE] in `NO_INTERACTION`.

The response from `/auth/authorization/issue` API has some parameters.
Among them, it is `action` parameter that the authorization server implementation should check first
because it denotes the next action that the authorization server implementation should take.
According to the value of `action`, the authorization server implementation must take the steps
described below.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the request from the authorization
server implementation was wrong or that an error occurred in Authlete.
In either case, from the viewpoint of the client application, it is an error on the server side.
Therefore, the service implementation should generate a response to the client application with
HTTP status of "500 Internal Server Error".

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the service implementation should generate and return
to the client application.

```
HTTP/1.1 500 Internal Server Error
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client application since
"500 Internal Server Error" is not required by OAuth 2.0.

**BAD_REQUEST**

When the value of "action" is `BAD_REQUEST`, it means that the ticket is no longer valid (deleted
or expired) and that the reason of the invalidity was probably due to the end-user's too-delayed
response to the authorization UI.

The HTTP status of the response returned to the client application should be "400 Bad Request"
and the content type should be `application/json` although OAuth 2.0 specification does not mention
the format of the error response.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the service implementation should generate and return
to the client application.

```
HTTP/1.1 400 Bad Request
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client application since
"400 Bad Request" is not required by OAuth 2.0.

**LOCATION**

When the value of `action` is `LOCATION`, it means that the response to the client application
should be "302 Found" with `Location` header.

The value of `responseContent` is a redirect URI which contains (1) an authorization code, an ID
token and/or an access token (on success) or (2) an error code (on failure), so it can be used as
the value of `Location` header.

The following illustrates the response which the service implementation must generate and return
to the client application.

```
HTTP/1.1 302 Found
Location: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**FORM**

When the value of `action` is `FORM`, it means that the response to the client application should
be "200 OK" with an HTML which triggers redirection by JavaScript. This happens when the authorization
request from the client contains `response_mode=form_post` request parameter.

The value of `responseContent` is an HTML which satisfies the requirements of `response_mode=form_post`,
so it can be used as the entity body of the response.

The following illustrates the response which the service implementation should generate and return
to the client application.

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_authorization_issue_api" method="post" path="/api/{serviceId}/auth/authorization/issue" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.authorizationEndpoint.issue({
    serviceId: "<id>",
    requestBody: {
      ticket: "FFgB9gwb_WXh6g1u-UQ8ZI-d_k4B-o-cm7RkVzI8Vnc",
      subject: "john",
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
import { authorizationEndpointIssue } from "authelete-bundled/funcs/authorizationEndpointIssue.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await authorizationEndpointIssue(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      ticket: "FFgB9gwb_WXh6g1u-UQ8ZI-d_k4B-o-cm7RkVzI8Vnc",
      subject: "john",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("authorizationEndpointIssue failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthAuthorizationIssueApiRequest](../../models/operations/authauthorizationissueapirequest.md)                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthAuthorizationIssueApiResponse](../../models/operations/authauthorizationissueapiresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## issueForm

This API parses request parameters of an authorization request and returns necessary data for the
authorization server implementation to process the authorization request further.

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from within the implementation of the authorization endpoint of
the service in order to generate a successful response to the client application.

The description of the `/auth/authorization` API describes the timing when this API should be called
and the meaning of request parameters. See [ISSUE] in `NO_INTERACTION`.

The response from `/auth/authorization/issue` API has some parameters.
Among them, it is `action` parameter that the authorization server implementation should check first
because it denotes the next action that the authorization server implementation should take.
According to the value of `action`, the authorization server implementation must take the steps
described below.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the request from the authorization
server implementation was wrong or that an error occurred in Authlete.
In either case, from the viewpoint of the client application, it is an error on the server side.
Therefore, the service implementation should generate a response to the client application with
HTTP status of "500 Internal Server Error".

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the service implementation should generate and return
to the client application.

```
HTTP/1.1 500 Internal Server Error
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client application since
"500 Internal Server Error" is not required by OAuth 2.0.

**BAD_REQUEST**

When the value of "action" is `BAD_REQUEST`, it means that the ticket is no longer valid (deleted
or expired) and that the reason of the invalidity was probably due to the end-user's too-delayed
response to the authorization UI.

The HTTP status of the response returned to the client application should be "400 Bad Request"
and the content type should be `application/json` although OAuth 2.0 specification does not mention
the format of the error response.

The value of `responseContent` is a JSON string which describes the error, so it can be used as
the entity body of the response.

The following illustrates the response which the service implementation should generate and return
to the client application.

```
HTTP/1.1 400 Bad Request
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```

The endpoint implementation may return another different response to the client application since
"400 Bad Request" is not required by OAuth 2.0.

**LOCATION**

When the value of `action` is `LOCATION`, it means that the response to the client application
should be "302 Found" with `Location` header.

The value of `responseContent` is a redirect URI which contains (1) an authorization code, an ID
token and/or an access token (on success) or (2) an error code (on failure), so it can be used as
the value of `Location` header.

The following illustrates the response which the service implementation must generate and return
to the client application.

```
HTTP/1.1 302 Found
Location: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**FORM**

When the value of `action` is `FORM`, it means that the response to the client application should
be "200 OK" with an HTML which triggers redirection by JavaScript. This happens when the authorization
request from the client contains `response_mode=form_post` request parameter.

The value of `responseContent` is an HTML which satisfies the requirements of `response_mode=form_post`,
so it can be used as the entity body of the response.

The following illustrates the response which the service implementation should generate and return
to the client application.

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_authorization_issue_api_form" method="post" path="/api/{serviceId}/auth/authorization/issue" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.authorizationEndpoint.issueForm({
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
import { authorizationEndpointIssueForm } from "authelete-bundled/funcs/authorizationEndpointIssueForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await authorizationEndpointIssueForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("authorizationEndpointIssueForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthAuthorizationIssueApiFormRequest](../../models/operations/authauthorizationissueapiformrequest.md)                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthAuthorizationIssueApiFormResponse](../../models/operations/authauthorizationissueapiformresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## getTicketInfo

Get Ticket Information

### Example Usage

<!-- UsageSnippet language="typescript" operationID="get_/api/{serviceId}/auth/authorization/ticket/info" method="get" path="/api/{serviceId}/auth/authorization/ticket/info" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.authorizationEndpoint.getTicketInfo({
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
import { authorizationEndpointGetTicketInfo } from "authelete-bundled/funcs/authorizationEndpointGetTicketInfo.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await authorizationEndpointGetTicketInfo(autheleteBundled, {
    serviceId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("authorizationEndpointGetTicketInfo failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetApiServiceIdAuthAuthorizationTicketInfoRequest](../../models/operations/getapiserviceidauthauthorizationticketinforequest.md)                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.GetApiServiceIdAuthAuthorizationTicketInfoResponse](../../models/operations/getapiserviceidauthauthorizationticketinforesponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## updateTicket

Update Ticket Information

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/api/{serviceId}/auth/authorization/ticket/update" method="post" path="/api/{serviceId}/auth/authorization/ticket/update" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.authorizationEndpoint.updateTicket({
    serviceId: "<id>",
    requestBody: {
      ticket: "<value>",
      info: "<value>",
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
import { authorizationEndpointUpdateTicket } from "authelete-bundled/funcs/authorizationEndpointUpdateTicket.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await authorizationEndpointUpdateTicket(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      ticket: "<value>",
      info: "<value>",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("authorizationEndpointUpdateTicket failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostApiServiceIdAuthAuthorizationTicketUpdateRequest](../../models/operations/postapiserviceidauthauthorizationticketupdaterequest.md)                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.PostApiServiceIdAuthAuthorizationTicketUpdateResponse](../../models/operations/postapiserviceidauthauthorizationticketupdateresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## updateTicketForm

Update Ticket Information

### Example Usage

<!-- UsageSnippet language="typescript" operationID="post_/api/{serviceId}/auth/authorization/ticket/update_form" method="post" path="/api/{serviceId}/auth/authorization/ticket/update" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.authorizationEndpoint.updateTicketForm({
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
import { authorizationEndpointUpdateTicketForm } from "authelete-bundled/funcs/authorizationEndpointUpdateTicketForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await authorizationEndpointUpdateTicketForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("authorizationEndpointUpdateTicketForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PostApiServiceIdAuthAuthorizationTicketUpdateFormRequest](../../models/operations/postapiserviceidauthauthorizationticketupdateformrequest.md)                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.PostApiServiceIdAuthAuthorizationTicketUpdateFormResponse](../../models/operations/postapiserviceidauthauthorizationticketupdateformresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |