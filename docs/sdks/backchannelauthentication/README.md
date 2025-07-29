# BackchannelAuthentication
(*backchannelAuthentication*)

## Overview

### Available Operations

* [issue](#issue) - Issue Backchannel Authentication Response
* [issueForm](#issueform) - Issue Backchannel Authentication Response

## issue

This API prepares JSON that contains an `auth_req_id`. The JSON should be used as the response body
of the response which is returned to the client from the [backchannel authentication endpoint](https://openid.net/specs/openid-client-initiated-backchannel-authentication-core-1_0.html#auth_backchannel_endpoint)

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from within the implementation of the backchannel authentication
endpoint of the service in order to generate a successful response to the client application.

The description of the `/backchannel/authentication` API describes the timing when this API should
be called and the meaning of request parameters. See [AUTH_REQ_ID ISSUE] in `USER_IDENTIFICATION`.

The response from `/backchannel/authentication/issue` API has some parameters. Among them, it is
`action` parameter that the authorization server implementation should check first because it denotes
the next `action` that the authorization server implementation should take. According to the value
of `action`, the authorization server implementation must take the steps described below.

```java
@POST
@Consumes(MediaType.APPLICATION_FORM_URLENCODED)
public Response post(String parameters)
{
    // 'parameters' is the entity body of the backchannel authentication request.
    ......
}
```

The endpoint implementation does not have to parse the request parameters from the client application
because Authlete's `/backchannel/authentication` API does it.

The response from `/backchannel/authentication` API has various parameters. Among them, it is `action`
parameter that the authorization server implementation should check first because it denotes the
next action that the authorization server implementation should take. According to the value of
`action`, the service implementation must take the steps described below.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the request from the authorization
server implementation was wrong or that an error occurred in Authlete.
In either case, from the viewpoint of the client application, it is an error on the server side.
Therefore, the service implementation should generate a response to the client application with
HTTP status of "500 Internal Server Error" and `application/json`.

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

**INVALID_TICKET**

When the value of `action` is `INVALID_TICKET`, it means that the ticket included in the API call
was invalid. For example, it does not exist or has expired.

From a viewpoint of the client application, this is an error on the server side. Therefore, the
authorization server implementation should generate a response to the client application with
"500 Internal Server Error" and `application/json`.

You can build an error response in the same way as shown in the description for the case of `INTERNAL_SERVER_ERROR`.

**OK**

When the value of `action` is `OK`, it means that Authlete has succeeded in preparing JSON that
contains an `auth_req_id`. The JSON should be used as the response body of the response that is
returned to the client from the backchannel authentication endpoint. `responseContent` contains
the JSON.

The following illustrates the response which the authorization server implementation should generate
and return to the client application.

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="backchannel_authentication_issue_api" method="post" path="/api/{serviceId}/backchannel/authentication/issue" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.backchannelAuthentication.issue({
    serviceId: "<id>",
    requestBody: {
      ticket: "NFIHGx_btVrWmtAD093D-87JxvT4DAtuijEkLVHbS4Q",
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
import { backchannelAuthenticationIssue } from "authelete-bundled/funcs/backchannelAuthenticationIssue.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await backchannelAuthenticationIssue(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      ticket: "NFIHGx_btVrWmtAD093D-87JxvT4DAtuijEkLVHbS4Q",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("backchannelAuthenticationIssue failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.BackchannelAuthenticationIssueApiRequest](../../models/operations/backchannelauthenticationissueapirequest.md)                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.BackchannelAuthenticationIssueApiResponse](../../models/operations/backchannelauthenticationissueapiresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |

## issueForm

This API prepares JSON that contains an `auth_req_id`. The JSON should be used as the response body
of the response which is returned to the client from the [backchannel authentication endpoint](https://openid.net/specs/openid-client-initiated-backchannel-authentication-core-1_0.html#auth_backchannel_endpoint)

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from within the implementation of the backchannel authentication
endpoint of the service in order to generate a successful response to the client application.

The description of the `/backchannel/authentication` API describes the timing when this API should
be called and the meaning of request parameters. See [AUTH_REQ_ID ISSUE] in `USER_IDENTIFICATION`.

The response from `/backchannel/authentication/issue` API has some parameters. Among them, it is
`action` parameter that the authorization server implementation should check first because it denotes
the next `action` that the authorization server implementation should take. According to the value
of `action`, the authorization server implementation must take the steps described below.

```java
@POST
@Consumes(MediaType.APPLICATION_FORM_URLENCODED)
public Response post(String parameters)
{
    // 'parameters' is the entity body of the backchannel authentication request.
    ......
}
```

The endpoint implementation does not have to parse the request parameters from the client application
because Authlete's `/backchannel/authentication` API does it.

The response from `/backchannel/authentication` API has various parameters. Among them, it is `action`
parameter that the authorization server implementation should check first because it denotes the
next action that the authorization server implementation should take. According to the value of
`action`, the service implementation must take the steps described below.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the request from the authorization
server implementation was wrong or that an error occurred in Authlete.
In either case, from the viewpoint of the client application, it is an error on the server side.
Therefore, the service implementation should generate a response to the client application with
HTTP status of "500 Internal Server Error" and `application/json`.

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

**INVALID_TICKET**

When the value of `action` is `INVALID_TICKET`, it means that the ticket included in the API call
was invalid. For example, it does not exist or has expired.

From a viewpoint of the client application, this is an error on the server side. Therefore, the
authorization server implementation should generate a response to the client application with
"500 Internal Server Error" and `application/json`.

You can build an error response in the same way as shown in the description for the case of `INTERNAL_SERVER_ERROR`.

**OK**

When the value of `action` is `OK`, it means that Authlete has succeeded in preparing JSON that
contains an `auth_req_id`. The JSON should be used as the response body of the response that is
returned to the client from the backchannel authentication endpoint. `responseContent` contains
the JSON.

The following illustrates the response which the authorization server implementation should generate
and return to the client application.

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Cache-Control: no-store
Pragma: no-cache

{responseContent}
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="backchannel_authentication_issue_api_form" method="post" path="/api/{serviceId}/backchannel/authentication/issue" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.backchannelAuthentication.issueForm({
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
import { backchannelAuthenticationIssueForm } from "authelete-bundled/funcs/backchannelAuthenticationIssueForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await backchannelAuthenticationIssueForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("backchannelAuthenticationIssueForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.BackchannelAuthenticationIssueApiFormRequest](../../models/operations/backchannelauthenticationissueapiformrequest.md)                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.BackchannelAuthenticationIssueApiFormResponse](../../models/operations/backchannelauthenticationissueapiformresponse.md)\>**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| errors.BadRequestError              | 400                                 | application/json                    |
| errors.UnauthorizedError            | 401                                 | application/json                    |
| errors.ForbiddenError               | 403                                 | application/json                    |
| errors.InternalServerError          | 500                                 | application/json                    |
| errors.AutheleteBundledDefaultError | 4XX, 5XX                            | \*/\*                               |