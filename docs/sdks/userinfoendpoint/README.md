# UserInfoEndpoint
(*userInfoEndpoint*)

## Overview

API endpoints for implementing OpenID Connect UserInfo Endpoint.

### Available Operations

* [authUserinfoApi](#authuserinfoapi) - Process UserInfo Request
* [authUserinfoApiForm](#authuserinfoapiform) - Process UserInfo Request
* [authUserinfoIssueApi](#authuserinfoissueapi) - Issue UserInfo Response
* [authUserinfoIssueApiForm](#authuserinfoissueapiform) - Issue UserInfo Response

## authUserinfoApi

This API gathers information about a user.

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from within the implementation of the [userinfo endpoint](https://openid.net/specs/openid-connect-core-1_0.html#UserInfo)
of the authorization server in order to get information about the user that is associated with
an access token.

The response from `/auth/userinfo` API has various parameters. Among them, it is `action` parameter
that the authorization server implementation should check first because it denotes the next action
that the authorization server implementation should take. According to the value of `action`, the
service implementation must take the steps described below.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the request from the authorization
server implementation was wrong or that an error occurred in Authlete. In either case, from the
viewpoint of the client application, it is an error on the server side. Therefore, the service
implementation should generate a response to the client application with HTTP status of "500 Internal
Server Error".

The value of `responseContent` is a string which describes the error in the format of [RFC 6750](https://datatracker.ietf.org/doc/html/rfc6750)
(OAuth 2.0 Bearer Token Usage) so the userinfo endpoint implementation can use the value of `responseContent`
as the value of`WWW-Authenticate` header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 500 Internal Server Error
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**BAD_REQUEST**

When the value of `action` is `BAD_REQUEST`, it means that the request from the client application
does not contain an access token (= the request from the authorization server implementation to
Authlete does not contain `token` parameter).

The value of `responseContent` is a string which describes the error in the format
of [RFC 6750](https://datatracker.ietf.org/doc/html/rfc6750) (OAuth 2.0 Bearer Token Usage) so the
userinfo endpoint implementation can use the value of `responseContent` as the value of`WWW-Authenticate`
header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 400 Bad Request
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**UNAUTHORIZED**

When the value of `action` is `UNAUTHORIZED`, it means that the access token does not exist, has
expired, or is not associated with any subject (= any user account).

The value of `responseContent` is a string which describes the error in the format of [RFC
6750](https://datatracker.ietf.org/doc/html/rfc6750) (OAuth 2.0 Bearer Token Usage) so the userinfo
endpoint implementation can use the value of `responseContent` as the value of`WWW-Authenticate`
header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 401 Unauthorized
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**FORBIDDEN**

When the value of `action` is `FORBIDDEN`, it means that the access token does not include the
`openid` scope.

The value of `responseContent` is a string which describes the error in the format of [RFC 6750](https://datatracker.ietf.org/doc/html/rfc6750)
(OAuth 2.0 Bearer Token Usage) so the userinfo endpoint implementation can use the value of `responseContent`
as the value of`WWW-Authenticate` header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 403 Forbidden
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**OK**

When the value of `action` is `OK`, it means that the access token which the client application
presented is valid. To be concrete, it means that the access token exists, has not expired, includes
the openid scope, and is associated with a subject (= a user account).

What the userinfo endpoint implementation should do next is to collect information about the subject
(user) from your database. The value of the `subject` is contained in the subject parameter in the
response from this API and the names of data, i.e., the claims names are contained in the claims
parameter in the response. For example, if the `subject` parameter is `joe123` and the claims
parameter is `[ "given_name", "email" ]`, you need to extract information about joe123's given name
and email from your database.

Then, call Authlete's `/auth/userinfo/issue` API with the collected information and the access token
in order to make Authlete generate an ID token.

If an error occurred during the above steps, generate an error response to the client. The response
should comply with [RFC 6750](https://datatracker.ietf.org/doc/html/rfc6750). For example, if the
subject associated with the access token does not exist in your database any longer, you may feel
like generating a response like below.

```
HTTP/1.1 400 Bad Request
WWW-Authenticate: Bearer error="invalid_token",
 error_description="The subject associated with the access token does not exist."
Cache-Control: no-store
Pragma: no-cache
```

Also, an error might occur on database access. If you treat the error as an internal server error,
then the response would be like the following.

```
HTTP/1.1 500 Internal Server Error
WWW-Authenticate: Bearer error="server_error",
 error_description="Failed to extract information about the subject from the database."
Cache-Control: no-store
Pragma: no-cache
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_userinfo_api" method="post" path="/api/{serviceId}/auth/userinfo" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.userInfoEndpoint.authUserinfoApi({
    serviceId: "<id>",
    requestBody: {
      token: "Ntm9MDb8WXQAevqrBkd84KTTHbYHVQrTjgUZCOWqEUI",
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
import { userInfoEndpointAuthUserinfoApi } from "authelete-bundled/funcs/userInfoEndpointAuthUserinfoApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await userInfoEndpointAuthUserinfoApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      token: "Ntm9MDb8WXQAevqrBkd84KTTHbYHVQrTjgUZCOWqEUI",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("userInfoEndpointAuthUserinfoApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthUserinfoApiRequest](../../models/operations/authuserinfoapirequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthUserinfoApiResponse](../../models/operations/authuserinfoapiresponse.md)\>**

### Errors

| Error Type                                | Status Code                               | Content Type                              |
| ----------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| errors.AuthUserinfoApiBadRequestError     | 400                                       | application/json                          |
| errors.AuthUserinfoApiUnauthorizedError   | 401                                       | application/json                          |
| errors.AuthUserinfoApiForbiddenError      | 403                                       | application/json                          |
| errors.AuthUserinfoApiInternalServerError | 500                                       | application/json                          |
| errors.AutheleteBundledDefaultError       | 4XX, 5XX                                  | \*/\*                                     |

## authUserinfoApiForm

This API gathers information about a user.

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from within the implementation of the [userinfo endpoint](https://openid.net/specs/openid-connect-core-1_0.html#UserInfo)
of the authorization server in order to get information about the user that is associated with
an access token.

The response from `/auth/userinfo` API has various parameters. Among them, it is `action` parameter
that the authorization server implementation should check first because it denotes the next action
that the authorization server implementation should take. According to the value of `action`, the
service implementation must take the steps described below.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the request from the authorization
server implementation was wrong or that an error occurred in Authlete. In either case, from the
viewpoint of the client application, it is an error on the server side. Therefore, the service
implementation should generate a response to the client application with HTTP status of "500 Internal
Server Error".

The value of `responseContent` is a string which describes the error in the format of [RFC 6750](https://datatracker.ietf.org/doc/html/rfc6750)
(OAuth 2.0 Bearer Token Usage) so the userinfo endpoint implementation can use the value of `responseContent`
as the value of`WWW-Authenticate` header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 500 Internal Server Error
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**BAD_REQUEST**

When the value of `action` is `BAD_REQUEST`, it means that the request from the client application
does not contain an access token (= the request from the authorization server implementation to
Authlete does not contain `token` parameter).

The value of `responseContent` is a string which describes the error in the format
of [RFC 6750](https://datatracker.ietf.org/doc/html/rfc6750) (OAuth 2.0 Bearer Token Usage) so the
userinfo endpoint implementation can use the value of `responseContent` as the value of`WWW-Authenticate`
header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 400 Bad Request
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**UNAUTHORIZED**

When the value of `action` is `UNAUTHORIZED`, it means that the access token does not exist, has
expired, or is not associated with any subject (= any user account).

The value of `responseContent` is a string which describes the error in the format of [RFC
6750](https://datatracker.ietf.org/doc/html/rfc6750) (OAuth 2.0 Bearer Token Usage) so the userinfo
endpoint implementation can use the value of `responseContent` as the value of`WWW-Authenticate`
header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 401 Unauthorized
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**FORBIDDEN**

When the value of `action` is `FORBIDDEN`, it means that the access token does not include the
`openid` scope.

The value of `responseContent` is a string which describes the error in the format of [RFC 6750](https://datatracker.ietf.org/doc/html/rfc6750)
(OAuth 2.0 Bearer Token Usage) so the userinfo endpoint implementation can use the value of `responseContent`
as the value of`WWW-Authenticate` header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 403 Forbidden
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**OK**

When the value of `action` is `OK`, it means that the access token which the client application
presented is valid. To be concrete, it means that the access token exists, has not expired, includes
the openid scope, and is associated with a subject (= a user account).

What the userinfo endpoint implementation should do next is to collect information about the subject
(user) from your database. The value of the `subject` is contained in the subject parameter in the
response from this API and the names of data, i.e., the claims names are contained in the claims
parameter in the response. For example, if the `subject` parameter is `joe123` and the claims
parameter is `[ "given_name", "email" ]`, you need to extract information about joe123's given name
and email from your database.

Then, call Authlete's `/auth/userinfo/issue` API with the collected information and the access token
in order to make Authlete generate an ID token.

If an error occurred during the above steps, generate an error response to the client. The response
should comply with [RFC 6750](https://datatracker.ietf.org/doc/html/rfc6750). For example, if the
subject associated with the access token does not exist in your database any longer, you may feel
like generating a response like below.

```
HTTP/1.1 400 Bad Request
WWW-Authenticate: Bearer error="invalid_token",
 error_description="The subject associated with the access token does not exist."
Cache-Control: no-store
Pragma: no-cache
```

Also, an error might occur on database access. If you treat the error as an internal server error,
then the response would be like the following.

```
HTTP/1.1 500 Internal Server Error
WWW-Authenticate: Bearer error="server_error",
 error_description="Failed to extract information about the subject from the database."
Cache-Control: no-store
Pragma: no-cache
```
</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_userinfo_api_form" method="post" path="/api/{serviceId}/auth/userinfo" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.userInfoEndpoint.authUserinfoApiForm({
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
import { userInfoEndpointAuthUserinfoApiForm } from "authelete-bundled/funcs/userInfoEndpointAuthUserinfoApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await userInfoEndpointAuthUserinfoApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: false,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("userInfoEndpointAuthUserinfoApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthUserinfoApiFormRequest](../../models/operations/authuserinfoapiformrequest.md)                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthUserinfoApiFormResponse](../../models/operations/authuserinfoapiformresponse.md)\>**

### Errors

| Error Type                                    | Status Code                                   | Content Type                                  |
| --------------------------------------------- | --------------------------------------------- | --------------------------------------------- |
| errors.AuthUserinfoApiFormBadRequestError     | 400                                           | application/json                              |
| errors.AuthUserinfoApiFormUnauthorizedError   | 401                                           | application/json                              |
| errors.AuthUserinfoApiFormForbiddenError      | 403                                           | application/json                              |
| errors.AuthUserinfoApiFormInternalServerError | 500                                           | application/json                              |
| errors.AutheleteBundledDefaultError           | 4XX, 5XX                                      | \*/\*                                         |

## authUserinfoIssueApi

This API generates an ID token.

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from within the implementation of the [userinfo endpoint](https://openid.net/specs/openid-connect-core-1_0.html#UserInfo)
of the authorization server in order to generate an ID token. Before calling this API, a valid
response from `/auth/userinfo` API must be obtained. Then, call this API with the access token
contained in the response and the claims values of the user (subject) associated with the access
token. See **OK** written in the description of `/auth/userinfo` API for details.

The response from `/auth/userinfo/issue` API has various parameters. Among them, it is `action`
parameter that the authorization server implementation should check first because it denotes the
next action that the authorization server implementation should take. According to the value of
`action`, the service implementation must take the steps described below.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the request from the authorization
server implementation was wrong or that an error occurred in Authlete. In either case, from the
viewpoint of the client application, it is an error on the server side. Therefore, the service
implementation should generate a response to the client application with HTTP status of "500 Internal
Server Error".

The parameter `responseContent` returns a string which describes the error in the format of [RFC
6750](https://datatracker.ietf.org/doc/html/rfc6750) (OAuth 2.0 Bearer Token Usage) so the userinfo
endpoint implementation can use the value of `responseContent` as the value of`WWW-Authenticate`
header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 500 Internal Server Error
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**BAD_REQUEST**

When the value of `action` is `BAD_REQUEST`, it means that the request from the client application
does not contain an access token (= the request from the authorization server implementation to
Authlete does not contain `token` parameter).

The parameter `responseContent` returns a string which describes the error in the format of [RFC
6750](https://datatracker.ietf.org/doc/html/rfc6750) (OAuth 2.0 Bearer Token Usage) so the userinfo
endpoint implementation can use the value of `responseContent` as the value of`WWW-Authenticate`
header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 400 Bad Request
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**UNAUTHORIZED**

When the value of `action` is `UNAUTHORIZED`, it means that the access token does not exist, has
expired, or is not associated with any subject (= any user account).

The parameter `responseContent` returns a string which describes the error in the format of [RFC
6750](https://datatracker.ietf.org/doc/html/rfc6750) (OAuth 2.0 Bearer Token Usage) so the userinfo
endpoint implementation can use the value of `responseContent` as the value of`WWW-Authenticate`
header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 401 Unauthorized
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**FORBIDDEN**

When the value of `action` is `FORBIDDEN`, it means that the access token does not include the
`openid` scope.

The parameter `responseContent` returns a string which describes the error in the format of [RFC
6750](https://datatracker.ietf.org/doc/html/rfc6750) (OAuth 2.0 Bearer Token Usage) so the userinfo
endpoint implementation can use the value of `responseContent` as the value of`WWW-Authenticate`
header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 403 Forbidden
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**JSON**

When the value of `action` is `JSON`, it means that the access token which the client application
presented is valid and an ID token was successfully generated in the format of JSON.

The userinfo endpoint implementation is expected to generate a response to the client application.
The content type of the response must be `application/json` and the response body must be an ID
token in JSON format.

The value of `responseContent` is the ID token in JSON format when `action` is `JSON`, so
a response to the client can be built like below.

```
HTTP/1.1 200 OK
Cache-Control: no-store
Pragma: no-cache
Content-Type: application/json;charset=UTF-8

{responseContent}
```

**JWT**

When the value of `action` is `JWT`, it means that the access token which the client application
presented is valid and an ID token was successfully generated in the format of JWT (JSON Web Token)
([RFC 7519](https://datatracker.ietf.org/doc/html/rfc7519)).

The userinfo endpoint implementation is expected to generate a response to the client application.
The content type of the response must be `application/jwt` and the response body must be an ID
token in JWT format.

The value of `responseContent` is the ID token in JSON format when `action` is `JWT`, so a response
to the client can be built like below.

```
HTTP/1.1 200 OK
Cache-Control: no-store
Pragma: no-cache
Content-Type: application/jwt

{responseContent}
```

</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_userinfo_issue_api" method="post" path="/api/{serviceId}/auth/userinfo/issue" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.userInfoEndpoint.authUserinfoIssueApi({
    serviceId: "<id>",
    requestBody: {
      token: "Ntm9MDb8WXQAevqrBkd84KTTHbYHVQrTjgUZCOWqEUI",
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
import { userInfoEndpointAuthUserinfoIssueApi } from "authelete-bundled/funcs/userInfoEndpointAuthUserinfoIssueApi.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await userInfoEndpointAuthUserinfoIssueApi(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      token: "Ntm9MDb8WXQAevqrBkd84KTTHbYHVQrTjgUZCOWqEUI",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("userInfoEndpointAuthUserinfoIssueApi failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthUserinfoIssueApiRequest](../../models/operations/authuserinfoissueapirequest.md)                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthUserinfoIssueApiResponse](../../models/operations/authuserinfoissueapiresponse.md)\>**

### Errors

| Error Type                                     | Status Code                                    | Content Type                                   |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| errors.AuthUserinfoIssueApiBadRequestError     | 400                                            | application/json                               |
| errors.AuthUserinfoIssueApiUnauthorizedError   | 401                                            | application/json                               |
| errors.AuthUserinfoIssueApiForbiddenError      | 403                                            | application/json                               |
| errors.AuthUserinfoIssueApiInternalServerError | 500                                            | application/json                               |
| errors.AutheleteBundledDefaultError            | 4XX, 5XX                                       | \*/\*                                          |

## authUserinfoIssueApiForm

This API generates an ID token.

<br>
<details>
<summary>Description</summary>

This API is supposed to be called from within the implementation of the [userinfo endpoint](https://openid.net/specs/openid-connect-core-1_0.html#UserInfo)
of the authorization server in order to generate an ID token. Before calling this API, a valid
response from `/auth/userinfo` API must be obtained. Then, call this API with the access token
contained in the response and the claims values of the user (subject) associated with the access
token. See **OK** written in the description of `/auth/userinfo` API for details.

The response from `/auth/userinfo/issue` API has various parameters. Among them, it is `action`
parameter that the authorization server implementation should check first because it denotes the
next action that the authorization server implementation should take. According to the value of
`action`, the service implementation must take the steps described below.

**INTERNAL_SERVER_ERROR**

When the value of `action` is `INTERNAL_SERVER_ERROR`, it means that the request from the authorization
server implementation was wrong or that an error occurred in Authlete. In either case, from the
viewpoint of the client application, it is an error on the server side. Therefore, the service
implementation should generate a response to the client application with HTTP status of "500 Internal
Server Error".

The parameter `responseContent` returns a string which describes the error in the format of [RFC
6750](https://datatracker.ietf.org/doc/html/rfc6750) (OAuth 2.0 Bearer Token Usage) so the userinfo
endpoint implementation can use the value of `responseContent` as the value of`WWW-Authenticate`
header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 500 Internal Server Error
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**BAD_REQUEST**

When the value of `action` is `BAD_REQUEST`, it means that the request from the client application
does not contain an access token (= the request from the authorization server implementation to
Authlete does not contain `token` parameter).

The parameter `responseContent` returns a string which describes the error in the format of [RFC
6750](https://datatracker.ietf.org/doc/html/rfc6750) (OAuth 2.0 Bearer Token Usage) so the userinfo
endpoint implementation can use the value of `responseContent` as the value of`WWW-Authenticate`
header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 400 Bad Request
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**UNAUTHORIZED**

When the value of `action` is `UNAUTHORIZED`, it means that the access token does not exist, has
expired, or is not associated with any subject (= any user account).

The parameter `responseContent` returns a string which describes the error in the format of [RFC
6750](https://datatracker.ietf.org/doc/html/rfc6750) (OAuth 2.0 Bearer Token Usage) so the userinfo
endpoint implementation can use the value of `responseContent` as the value of`WWW-Authenticate`
header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 401 Unauthorized
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**FORBIDDEN**

When the value of `action` is `FORBIDDEN`, it means that the access token does not include the
`openid` scope.

The parameter `responseContent` returns a string which describes the error in the format of [RFC
6750](https://datatracker.ietf.org/doc/html/rfc6750) (OAuth 2.0 Bearer Token Usage) so the userinfo
endpoint implementation can use the value of `responseContent` as the value of`WWW-Authenticate`
header.

The following is an example response which complies with RFC 6750. Note that OpenID Connect Core
1.0 requires that an error response from userinfo endpoint comply with RFC 6750. See [5.3.3. UserInfo
Response](https://openid.net/specs/openid-connect-core-1_0.html#UserInfoError) for details.

```
HTTP/1.1 403 Forbidden
WWW-Authenticate: {responseContent}
Cache-Control: no-store
Pragma: no-cache
```

**JSON**

When the value of `action` is `JSON`, it means that the access token which the client application
presented is valid and an ID token was successfully generated in the format of JSON.

The userinfo endpoint implementation is expected to generate a response to the client application.
The content type of the response must be `application/json` and the response body must be an ID
token in JSON format.

The value of `responseContent` is the ID token in JSON format when `action` is `JSON`, so
a response to the client can be built like below.

```
HTTP/1.1 200 OK
Cache-Control: no-store
Pragma: no-cache
Content-Type: application/json;charset=UTF-8

{responseContent}
```

**JWT**

When the value of `action` is `JWT`, it means that the access token which the client application
presented is valid and an ID token was successfully generated in the format of JWT (JSON Web Token)
([RFC 7519](https://datatracker.ietf.org/doc/html/rfc7519)).

The userinfo endpoint implementation is expected to generate a response to the client application.
The content type of the response must be `application/jwt` and the response body must be an ID
token in JWT format.

The value of `responseContent` is the ID token in JSON format when `action` is `JWT`, so a response
to the client can be built like below.

```
HTTP/1.1 200 OK
Cache-Control: no-store
Pragma: no-cache
Content-Type: application/jwt

{responseContent}
```

</details>


### Example Usage

<!-- UsageSnippet language="typescript" operationID="auth_userinfo_issue_api_form" method="post" path="/api/{serviceId}/auth/userinfo/issue" -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.userInfoEndpoint.authUserinfoIssueApiForm({
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
import { userInfoEndpointAuthUserinfoIssueApiForm } from "authelete-bundled/funcs/userInfoEndpointAuthUserinfoIssueApiForm.js";

// Use `AutheleteBundledCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const autheleteBundled = new AutheleteBundledCore({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const res = await userInfoEndpointAuthUserinfoIssueApiForm(autheleteBundled, {
    serviceId: "<id>",
    requestBody: {
      clientLocked: true,
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("userInfoEndpointAuthUserinfoIssueApiForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AuthUserinfoIssueApiFormRequest](../../models/operations/authuserinfoissueapiformrequest.md)                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |
| `options.serverURL`                                                                                                                                                            | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | An optional server URL to use.                                                                                                                                                 |

### Response

**Promise\<[operations.AuthUserinfoIssueApiFormResponse](../../models/operations/authuserinfoissueapiformresponse.md)\>**

### Errors

| Error Type                                         | Status Code                                        | Content Type                                       |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| errors.AuthUserinfoIssueApiFormBadRequestError     | 400                                                | application/json                                   |
| errors.AuthUserinfoIssueApiFormUnauthorizedError   | 401                                                | application/json                                   |
| errors.AuthUserinfoIssueApiFormForbiddenError      | 403                                                | application/json                                   |
| errors.AuthUserinfoIssueApiFormInternalServerError | 500                                                | application/json                                   |
| errors.AutheleteBundledDefaultError                | 4XX, 5XX                                           | \*/\*                                              |