# authelete-bundled

Developer-friendly & type-safe Typescript SDK specifically catered to leverage *authelete-bundled* API.

<div align="left">
    <a href="https://www.speakeasy.com/?utm_source=authelete-bundled&utm_campaign=typescript"><img src="https://custom-icon-badges.demolab.com/badge/-Built%20By%20Speakeasy-212015?style=for-the-badge&logoColor=FBE331&logo=speakeasy&labelColor=545454" /></a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" style="width: 100px; height: 28px;" />
    </a>
</div>


<br /><br />
> [!IMPORTANT]
> This SDK is not yet ready for production use. To complete setup please follow the steps outlined in your [workspace](https://app.speakeasy.com/org/vartana/qwerty). Delete this section before > publishing to a package manager.

<!-- Start Summary [summary] -->
## Summary

Authlete API Explorer: <div class="min-h-screen bg-gray-100 dark:bg-gray-900 text-gray-900 dark:text-gray-100 p-6">
  <div class="flex justify-end mb-4">
    <label for="theme-toggle" class="flex items-center cursor-pointer">
      <div class="relative">Dark mode:
        <input type="checkbox" id="theme-toggle" class="sr-only" onchange="toggleTheme()">
        <div class="block bg-gray-600 w-14 h-8 rounded-full"></div>
        <div class="dot absolute left-1 top-1 bg-white w-6 h-6 rounded-full transition"></div>
      </div>
    </label>
  </div>
  <header class="bg-green-500 dark:bg-green-700 p-4 rounded-lg text-white text-center">
    <p>
      Welcome to the <strong>Authlete API documentation</strong>. Authlete is an <strong>API-first service</strong>
      where every aspect of the platform is configurable via API. This explorer provides a convenient way to
      authenticate and interact with the API, allowing you to see Authlete in action quickly. 🚀
    </p>
    <p>
      At a high level, the Authlete API is grouped into two categories:
    </p>
    <ul class="list-disc list-inside">
      <li><strong>Management APIs</strong>: Enable you to manage services and clients. 🔧</li>
      <li><strong>Runtime APIs</strong>: Allow you to build your own Authorization Servers or Verifiable Credential (VC)
        issuers. 🔐</li>
    </ul>
    <p>All API endpoints are secured using access tokens issued by Authlete's Identity Provider (IdP). If you already
      have an Authlete account, simply use the <em>Get Token</em> option on the Authentication page to log in and obtain
      an access token for API usage. If you don't have an account yet, <a href="https://console.authlete.com/register">sign up
        here</a> to get started.</p>
  </header>
  <main>
    <section id="api-servers" class="mb-10">
      <h2 class="text-2xl font-semibold mb-4">🌐 API Servers</h2>
      <p>Authlete is a global service with clusters available in multiple regions across the world.</p>
      <p>Currently, our service is available in the following regions:</p>
      <div class="grid grid-cols-2 gap-4">
        <div class="p-4 bg-white dark:bg-gray-800 rounded-lg shadow">
          <p class="text-center font-semibold">🇺🇸 US</p>
        </div>
        <div class="p-4 bg-white dark:bg-gray-800 rounded-lg shadow">
          <p class="text-center font-semibold">🇯🇵 JP</p>
        </div>
        <div class="p-4 bg-white dark:bg-gray-800 rounded-lg shadow">
          <p class="text-center font-semibold">🇪🇺 EU</p>
        </div>
        <div class="p-4 bg-white dark:bg-gray-800 rounded-lg shadow">
          <p class="text-center font-semibold">🇧🇷 Brazil</p>
        </div>
      </div>
      <p>Our customers can host their data in the region that best meets their requirements.</p>
      <a href="#servers" class="block mt-4 text-green-500 dark:text-green-300 hover:underline text-center">Select your
        preferred server</a>
    </section>
    <section id="authentication" class="mb-10">
      <h2 class="text-2xl font-semibold mb-4">🔑 Authentication</h2>
      <p>The API Explorer requires an access token to call the API.</p>
      <p>You can create the access token from the <a href="https://console.authlete.com">Authlete Management Console</a> and set it in the HTTP Bearer section of Authentication page.</p>
      <p>Alternatively, if you have an Authlete account, the API Explorer can log you in with your Authlete account and
        automatically acquire the required access token.</p>
      <div class="theme-admonition theme-admonition-warning admonition_o5H7 alert alert--warning">
        <div class="admonitionContent_Knsx">
          <p>⚠️ <strong>Important Note:</strong> When the API Explorer acquires the token after login, the access tokens
            will have the same permissions as the user who logs in as part of this flow.</p>
        </div>
      </div>
      <a href="#auth" class="block mt-4 text-green-500 dark:text-green-300 hover:underline text-center">Setup your
        access token</a>
    </section>
    <section id="tutorials" class="mb-10">
      <h2 class="text-2xl font-semibold mb-4">🎓 Tutorials</h2>
      <p>If you have successfully tested the API from the API Console and want to take the next step of integrating the
        API into your application, or if you want to see a sample using Authlete APIs, follow the links below. These
        resources will help you understand key concepts and how to integrate Authlete API into your applications.</p>
      <div class="mt-4">
        <a href="https://www.authlete.com/developers/getting_started/"
          class="block text-green-500 dark:text-green-300 font-bold hover:underline mb-2">🚀 Getting Started with
          Authlete</a>
          </br>
        <a href="https://www.authlete.com/developers/tutorial/signup/"
          class="block text-green-500 dark:text-green-300 font-bold hover:underline">🔑 From Sign-Up to the First API
          Request</a>
      </div>
    </section>
    <section id="support" class="mb-10">
      <h2 class="text-2xl font-semibold mb-4">🛠 Contact Us</h2>
      <p>If you have any questions or need assistance, our team is here to help.</p>
      <a href="https://www.authlete.com/contact/"
        class="block mt-4 text-green-500 dark:text-green-300 font-bold hover:underline">Contact Page</a>
    </section>
  </main>
</div>
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [authelete-bundled](#authelete-bundled)
  * [SDK Installation](#sdk-installation)
  * [Requirements](#requirements)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Standalone functions](#standalone-functions)
  * [Retries](#retries)
  * [Error Handling](#error-handling)
  * [Server Selection](#server-selection)
  * [Custom HTTP Client](#custom-http-client)
  * [Debugging](#debugging)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

The SDK can be installed with either [npm](https://www.npmjs.com/), [pnpm](https://pnpm.io/), [bun](https://bun.sh/) or [yarn](https://classic.yarnpkg.com/en/) package managers.

### NPM

```bash
npm add authelete-bundled
```

### PNPM

```bash
pnpm add authelete-bundled
```

### Bun

```bash
bun add authelete-bundled
```

### Yarn

```bash
yarn add authelete-bundled zod

# Note that Yarn does not install peer dependencies automatically. You will need
# to install zod as shown above.
```

> [!NOTE]
> This package is published with CommonJS and ES Modules (ESM) support.
<!-- End SDK Installation [installation] -->

<!-- Start Requirements [requirements] -->
## Requirements

For supported JavaScript runtimes, please consult [RUNTIMES.md](RUNTIMES.md).
<!-- End Requirements [requirements] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.serviceManagement.get({
    serviceId: "<id>",
  });

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security schemes globally:

| Name       | Type   | Scheme       | Environment Variable        |
| ---------- | ------ | ------------ | --------------------------- |
| `authlete` | oauth2 | OAuth2 token | `AUTHELETEBUNDLED_AUTHLETE` |
| `bearer`   | http   | HTTP Bearer  | `AUTHELETEBUNDLED_BEARER`   |

You can set the security parameters through the `security` optional parameter when initializing the SDK client instance. The selected scheme will be used by default to authenticate with the API for all operations that support it. For example:
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.serviceManagement.get({
    serviceId: "<id>",
  });

  console.log(result);
}

run();

```
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>


### [authorization](docs/sdks/authorization/README.md)

* [process](docs/sdks/authorization/README.md#process) - Process Authorization Request
* [processForm](docs/sdks/authorization/README.md#processform) - Process Authorization Request

### [authorizationEndpoint](docs/sdks/authorizationendpoint/README.md)

* [failRequest](docs/sdks/authorizationendpoint/README.md#failrequest) - Fail Authorization Request
* [failRequestForm](docs/sdks/authorizationendpoint/README.md#failrequestform) - Fail Authorization Request
* [issue](docs/sdks/authorizationendpoint/README.md#issue) - Issue Authorization Response
* [issueForm](docs/sdks/authorizationendpoint/README.md#issueform) - Issue Authorization Response
* [getTicketInfo](docs/sdks/authorizationendpoint/README.md#getticketinfo) - Get Ticket Information
* [updateTicket](docs/sdks/authorizationendpoint/README.md#updateticket) - Update Ticket Information
* [updateTicketForm](docs/sdks/authorizationendpoint/README.md#updateticketform) - Update Ticket Information

### [backchannelAuthentication](docs/sdks/backchannelauthentication/README.md)

* [issue](docs/sdks/backchannelauthentication/README.md#issue) - Issue Backchannel Authentication Response
* [issueForm](docs/sdks/backchannelauthentication/README.md#issueform) - Issue Backchannel Authentication Response

### [ciba](docs/sdks/ciba/README.md)

* [processAuthentication](docs/sdks/ciba/README.md#processauthentication) - Process Backchannel Authentication Request
* [processAuthenticationForm](docs/sdks/ciba/README.md#processauthenticationform) - Process Backchannel Authentication Request
* [failAuthentication](docs/sdks/ciba/README.md#failauthentication) - Fail Backchannel Authentication Request
* [failAuthenticationForm](docs/sdks/ciba/README.md#failauthenticationform) - Fail Backchannel Authentication Request
* [completeAuthentication](docs/sdks/ciba/README.md#completeauthentication) - Complete Backchannel Authentication
* [completeAuthenticationForm](docs/sdks/ciba/README.md#completeauthenticationform) - Complete Backchannel Authentication

### [clientManagement](docs/sdks/clientmanagement/README.md)

* [deleteClient](docs/sdks/clientmanagement/README.md#deleteclient) - Delete Client ⚡
* [updateClientLock](docs/sdks/clientmanagement/README.md#updateclientlock) - Update Client Lock
* [updateSecret](docs/sdks/clientmanagement/README.md#updatesecret) - Update Client Secret
* [updateSecretForm](docs/sdks/clientmanagement/README.md#updatesecretform) - Update Client Secret
* [getAuthorizedApplications](docs/sdks/clientmanagement/README.md#getauthorizedapplications) - Get Authorized Applications
* [updateTokens](docs/sdks/clientmanagement/README.md#updatetokens) - Update Client Tokens
* [updateTokensForm](docs/sdks/clientmanagement/README.md#updatetokensform) - Update Client Tokens
* [deleteAuthorization](docs/sdks/clientmanagement/README.md#deleteauthorization) - Delete Client Tokens
* [getGrantedScopes](docs/sdks/clientmanagement/README.md#getgrantedscopes) - Get Granted Scopes
* [deleteGrantedScopes](docs/sdks/clientmanagement/README.md#deletegrantedscopes) - Delete Granted Scopes
* [getRequestableScopes](docs/sdks/clientmanagement/README.md#getrequestablescopes) - Get Requestable Scopes
* [updateRequestableScopes](docs/sdks/clientmanagement/README.md#updaterequestablescopes) - Update Requestable Scopes
* [deleteRequestableScopes](docs/sdks/clientmanagement/README.md#deleterequestablescopes) - Delete Requestable Scopes

### [clientRegistrations](docs/sdks/clientregistrations/README.md)

* [get](docs/sdks/clientregistrations/README.md#get) - Get Client

### [clients](docs/sdks/clients/README.md)

* [get](docs/sdks/clients/README.md#get) - Get Client
* [list](docs/sdks/clients/README.md#list) - List Clients
* [create](docs/sdks/clients/README.md#create) - Create Client
* [update](docs/sdks/clients/README.md#update) - Update Client
* [rotateSecret](docs/sdks/clients/README.md#rotatesecret) - Rotate Client Secret
* [updateRegistration](docs/sdks/clients/README.md#updateregistration) - Update Client
* [updateRegistrationForm](docs/sdks/clients/README.md#updateregistrationform) - Update Client

### [deviceFlow](docs/sdks/deviceflow/README.md)

* [authorize](docs/sdks/deviceflow/README.md#authorize) - Process Device Authorization Request
* [authorizeForm](docs/sdks/deviceflow/README.md#authorizeform) - Process Device Authorization Request
* [verify](docs/sdks/deviceflow/README.md#verify) - Process Device Verification Request
* [verifyForm](docs/sdks/deviceflow/README.md#verifyform) - Process Device Verification Request
* [completeAuthorization](docs/sdks/deviceflow/README.md#completeauthorization) - Complete Device Authorization
* [completeAuthorizationForm](docs/sdks/deviceflow/README.md#completeauthorizationform) - Complete Device Authorization

### [dynamicClientRegistration](docs/sdks/dynamicclientregistration/README.md)

* [register](docs/sdks/dynamicclientregistration/README.md#register) - Register Client
* [registerForm](docs/sdks/dynamicclientregistration/README.md#registerform) - Register Client
* [delete](docs/sdks/dynamicclientregistration/README.md#delete) - Delete Client
* [deleteForm](docs/sdks/dynamicclientregistration/README.md#deleteform) - Delete Client

### [federation](docs/sdks/federation/README.md)

* [processConfiguration](docs/sdks/federation/README.md#processconfiguration) - Process Entity Configuration Request
* [register](docs/sdks/federation/README.md#register) - Process Federation Registration Request
* [registerForm](docs/sdks/federation/README.md#registerform) - Process Federation Registration Request

### [grantManagement](docs/sdks/grantmanagement/README.md)

* [process](docs/sdks/grantmanagement/README.md#process) - Process Grant Management Request

### [hardwareSecurityKey](docs/sdks/hardwaresecuritykey/README.md)

* [create](docs/sdks/hardwaresecuritykey/README.md#create) - Create Security Key
* [createForm](docs/sdks/hardwaresecuritykey/README.md#createform) - Create Security Key
* [get](docs/sdks/hardwaresecuritykey/README.md#get) - Get Security Key

### [hardwareSecurityKeys](docs/sdks/hardwaresecuritykeys/README.md)

* [delete](docs/sdks/hardwaresecuritykeys/README.md#delete) - Delete Security Key
* [list](docs/sdks/hardwaresecuritykeys/README.md#list) - List Security Keys

### [introspection](docs/sdks/introspection/README.md)

* [process](docs/sdks/introspection/README.md#process) - Process Introspection Request
* [processForm](docs/sdks/introspection/README.md#processform) - Process Introspection Request

### [introspectionEndpoint](docs/sdks/introspectionendpoint/README.md)

* [processRequest](docs/sdks/introspectionendpoint/README.md#processrequest) - Process OAuth 2.0 Introspection Request
* [processRequestForm](docs/sdks/introspectionendpoint/README.md#processrequestform) - Process OAuth 2.0 Introspection Request

### [jose](docs/sdks/jose/README.md)

* [verify](docs/sdks/jose/README.md#verify) - Verify JOSE
* [verifyForm](docs/sdks/jose/README.md#verifyform) - Verify JOSE

### [jwks](docs/sdks/jwks/README.md)

* [get](docs/sdks/jwks/README.md#get) - Get JWK Set

### [pushedAuthorizationEndpoint](docs/sdks/pushedauthorizationendpoint/README.md)

* [processRequest](docs/sdks/pushedauthorizationendpoint/README.md#processrequest) - Process Pushed Authorization Request
* [processRequestForm](docs/sdks/pushedauthorizationendpoint/README.md#processrequestform) - Process Pushed Authorization Request

### [revocation](docs/sdks/revocation/README.md)

* [process](docs/sdks/revocation/README.md#process) - Process Revocation Request
* [processForm](docs/sdks/revocation/README.md#processform) - Process Revocation Request

### [serviceManagement](docs/sdks/servicemanagement/README.md)

* [get](docs/sdks/servicemanagement/README.md#get) - Get Service
* [list](docs/sdks/servicemanagement/README.md#list) - List Services
* [create](docs/sdks/servicemanagement/README.md#create) - Create Service
* [update](docs/sdks/servicemanagement/README.md#update) - Update Service
* [getConfiguration](docs/sdks/servicemanagement/README.md#getconfiguration) - Get Service Configuration

### [services](docs/sdks/services/README.md)

* [delete](docs/sdks/services/README.md#delete) - Delete Service ⚡

### [tokenEndpoint](docs/sdks/tokenendpoint/README.md)

* [process](docs/sdks/tokenendpoint/README.md#process) - Process Token Request
* [processForm](docs/sdks/tokenendpoint/README.md#processform) - Process Token Request
* [reissueIdToken](docs/sdks/tokenendpoint/README.md#reissueidtoken) - Reissue ID Token

### [tokenOperations](docs/sdks/tokenoperations/README.md)

* [updateToken](docs/sdks/tokenoperations/README.md#updatetoken) - Update Access Token
* [updateTokenForm](docs/sdks/tokenoperations/README.md#updatetokenform) - Update Access Token
* [delete](docs/sdks/tokenoperations/README.md#delete) - Delete Access Token
* [revokeToken](docs/sdks/tokenoperations/README.md#revoketoken) - Revoke Access Token
* [revokeTokenForm](docs/sdks/tokenoperations/README.md#revoketokenform) - Revoke Access Token

### [tokens](docs/sdks/tokens/README.md)

* [fail](docs/sdks/tokens/README.md#fail) - Fail Token Request
* [failForm](docs/sdks/tokens/README.md#failform) - Fail Token Request
* [issue](docs/sdks/tokens/README.md#issue) - Issue Token Response
* [issueForm](docs/sdks/tokens/README.md#issueform) - Issue Token Response
* [list](docs/sdks/tokens/README.md#list) - List Issued Tokens
* [create](docs/sdks/tokens/README.md#create) - Create Access Token
* [createForm](docs/sdks/tokens/README.md#createform) - Create Access Token

### [userinfo](docs/sdks/userinfo/README.md)

* [process](docs/sdks/userinfo/README.md#process) - Process UserInfo Request
* [processForm](docs/sdks/userinfo/README.md#processform) - Process UserInfo Request

### [userInfoEndpoint](docs/sdks/userinfoendpoint/README.md)

* [issue](docs/sdks/userinfoendpoint/README.md#issue) - Issue UserInfo Response
* [issueForm](docs/sdks/userinfoendpoint/README.md#issueform) - Issue UserInfo Response

### [utilityEndpoints](docs/sdks/utilityendpoints/README.md)

* [getInfo](docs/sdks/utilityendpoints/README.md#getinfo) - Get Server Metadata
* [echo](docs/sdks/utilityendpoints/README.md#echo) - Echo

### [vci](docs/sdks/vci/README.md)

* [metadata](docs/sdks/vci/README.md#metadata) - /api/{serviceId}/vci/metadata API
* [metadataForm](docs/sdks/vci/README.md#metadataform) - /api/{serviceId}/vci/metadata API
* [parseBatch](docs/sdks/vci/README.md#parsebatch) - /api/{serviceId}/vci/batch/parse API
* [parseBatchForm](docs/sdks/vci/README.md#parsebatchform) - /api/{serviceId}/vci/batch/parse API

### [verifiableCredentialIssuer](docs/sdks/verifiablecredentialissuer/README.md)

* [issueJwt](docs/sdks/verifiablecredentialissuer/README.md#issuejwt) - /api/{serviceId}/vci/jwtissuer API
* [issueJwtForm](docs/sdks/verifiablecredentialissuer/README.md#issuejwtform) - /api/{serviceId}/vci/jwtissuer API
* [jwks](docs/sdks/verifiablecredentialissuer/README.md#jwks) - /api/{serviceId}/vci/jwks API
* [jwksForm](docs/sdks/verifiablecredentialissuer/README.md#jwksform) - /api/{serviceId}/vci/jwks API
* [createOffer](docs/sdks/verifiablecredentialissuer/README.md#createoffer) - /api/{serviceId}/vci/offer/create API
* [createOfferForm](docs/sdks/verifiablecredentialissuer/README.md#createofferform) - /api/{serviceId}/vci/offer/create API
* [batchIssue](docs/sdks/verifiablecredentialissuer/README.md#batchissue) - /api/{serviceId}/vci/batch/issue API
* [deferredParse](docs/sdks/verifiablecredentialissuer/README.md#deferredparse) - /api/{serviceId}/vci/deferred/parse API
* [deferredParseForm](docs/sdks/verifiablecredentialissuer/README.md#deferredparseform) - /api/{serviceId}/vci/deferred/parse API
* [issueDeferred](docs/sdks/verifiablecredentialissuer/README.md#issuedeferred) - /api/{serviceId}/vci/deferred/issue API

### [verifiableCredentials](docs/sdks/verifiablecredentials/README.md)

* [offerInfo](docs/sdks/verifiablecredentials/README.md#offerinfo) - /api/{serviceId}/vci/offer/info API
* [offerInfoForm](docs/sdks/verifiablecredentials/README.md#offerinfoform) - /api/{serviceId}/vci/offer/info API
* [parse](docs/sdks/verifiablecredentials/README.md#parse) - /api/{serviceId}/vci/single/parse API
* [parseForm](docs/sdks/verifiablecredentials/README.md#parseform) - /api/{serviceId}/vci/single/parse API
* [issue](docs/sdks/verifiablecredentials/README.md#issue) - /api/{serviceId}/vci/single/issue API

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Standalone functions [standalone-funcs] -->
## Standalone functions

All the methods listed above are available as standalone functions. These
functions are ideal for use in applications running in the browser, serverless
runtimes or other environments where application bundle size is a primary
concern. When using a bundler to build your application, all unused
functionality will be either excluded from the final bundle or tree-shaken away.

To read more about standalone functions, check [FUNCTIONS.md](./FUNCTIONS.md).

<details>

<summary>Available standalone functions</summary>

- [`authorizationEndpointFailRequest`](docs/sdks/authorizationendpoint/README.md#failrequest) - Fail Authorization Request
- [`authorizationEndpointFailRequestForm`](docs/sdks/authorizationendpoint/README.md#failrequestform) - Fail Authorization Request
- [`authorizationEndpointGetTicketInfo`](docs/sdks/authorizationendpoint/README.md#getticketinfo) - Get Ticket Information
- [`authorizationEndpointIssue`](docs/sdks/authorizationendpoint/README.md#issue) - Issue Authorization Response
- [`authorizationEndpointIssueForm`](docs/sdks/authorizationendpoint/README.md#issueform) - Issue Authorization Response
- [`authorizationEndpointUpdateTicket`](docs/sdks/authorizationendpoint/README.md#updateticket) - Update Ticket Information
- [`authorizationEndpointUpdateTicketForm`](docs/sdks/authorizationendpoint/README.md#updateticketform) - Update Ticket Information
- [`authorizationProcess`](docs/sdks/authorization/README.md#process) - Process Authorization Request
- [`authorizationProcessForm`](docs/sdks/authorization/README.md#processform) - Process Authorization Request
- [`backchannelAuthenticationIssue`](docs/sdks/backchannelauthentication/README.md#issue) - Issue Backchannel Authentication Response
- [`backchannelAuthenticationIssueForm`](docs/sdks/backchannelauthentication/README.md#issueform) - Issue Backchannel Authentication Response
- [`cibaCompleteAuthentication`](docs/sdks/ciba/README.md#completeauthentication) - Complete Backchannel Authentication
- [`cibaCompleteAuthenticationForm`](docs/sdks/ciba/README.md#completeauthenticationform) - Complete Backchannel Authentication
- [`cibaFailAuthentication`](docs/sdks/ciba/README.md#failauthentication) - Fail Backchannel Authentication Request
- [`cibaFailAuthenticationForm`](docs/sdks/ciba/README.md#failauthenticationform) - Fail Backchannel Authentication Request
- [`cibaProcessAuthentication`](docs/sdks/ciba/README.md#processauthentication) - Process Backchannel Authentication Request
- [`cibaProcessAuthenticationForm`](docs/sdks/ciba/README.md#processauthenticationform) - Process Backchannel Authentication Request
- [`clientManagementDeleteAuthorization`](docs/sdks/clientmanagement/README.md#deleteauthorization) - Delete Client Tokens
- [`clientManagementDeleteClient`](docs/sdks/clientmanagement/README.md#deleteclient) - Delete Client ⚡
- [`clientManagementDeleteGrantedScopes`](docs/sdks/clientmanagement/README.md#deletegrantedscopes) - Delete Granted Scopes
- [`clientManagementDeleteRequestableScopes`](docs/sdks/clientmanagement/README.md#deleterequestablescopes) - Delete Requestable Scopes
- [`clientManagementGetAuthorizedApplications`](docs/sdks/clientmanagement/README.md#getauthorizedapplications) - Get Authorized Applications
- [`clientManagementGetGrantedScopes`](docs/sdks/clientmanagement/README.md#getgrantedscopes) - Get Granted Scopes
- [`clientManagementGetRequestableScopes`](docs/sdks/clientmanagement/README.md#getrequestablescopes) - Get Requestable Scopes
- [`clientManagementUpdateClientLock`](docs/sdks/clientmanagement/README.md#updateclientlock) - Update Client Lock
- [`clientManagementUpdateRequestableScopes`](docs/sdks/clientmanagement/README.md#updaterequestablescopes) - Update Requestable Scopes
- [`clientManagementUpdateSecret`](docs/sdks/clientmanagement/README.md#updatesecret) - Update Client Secret
- [`clientManagementUpdateSecretForm`](docs/sdks/clientmanagement/README.md#updatesecretform) - Update Client Secret
- [`clientManagementUpdateTokens`](docs/sdks/clientmanagement/README.md#updatetokens) - Update Client Tokens
- [`clientManagementUpdateTokensForm`](docs/sdks/clientmanagement/README.md#updatetokensform) - Update Client Tokens
- [`clientRegistrationsGet`](docs/sdks/clientregistrations/README.md#get) - Get Client
- [`clientsCreate`](docs/sdks/clients/README.md#create) - Create Client
- [`clientsGet`](docs/sdks/clients/README.md#get) - Get Client
- [`clientsList`](docs/sdks/clients/README.md#list) - List Clients
- [`clientsRotateSecret`](docs/sdks/clients/README.md#rotatesecret) - Rotate Client Secret
- [`clientsUpdate`](docs/sdks/clients/README.md#update) - Update Client
- [`clientsUpdateRegistration`](docs/sdks/clients/README.md#updateregistration) - Update Client
- [`clientsUpdateRegistrationForm`](docs/sdks/clients/README.md#updateregistrationform) - Update Client
- [`deviceFlowAuthorize`](docs/sdks/deviceflow/README.md#authorize) - Process Device Authorization Request
- [`deviceFlowAuthorizeForm`](docs/sdks/deviceflow/README.md#authorizeform) - Process Device Authorization Request
- [`deviceFlowCompleteAuthorization`](docs/sdks/deviceflow/README.md#completeauthorization) - Complete Device Authorization
- [`deviceFlowCompleteAuthorizationForm`](docs/sdks/deviceflow/README.md#completeauthorizationform) - Complete Device Authorization
- [`deviceFlowVerify`](docs/sdks/deviceflow/README.md#verify) - Process Device Verification Request
- [`deviceFlowVerifyForm`](docs/sdks/deviceflow/README.md#verifyform) - Process Device Verification Request
- [`dynamicClientRegistrationDelete`](docs/sdks/dynamicclientregistration/README.md#delete) - Delete Client
- [`dynamicClientRegistrationDeleteForm`](docs/sdks/dynamicclientregistration/README.md#deleteform) - Delete Client
- [`dynamicClientRegistrationRegister`](docs/sdks/dynamicclientregistration/README.md#register) - Register Client
- [`dynamicClientRegistrationRegisterForm`](docs/sdks/dynamicclientregistration/README.md#registerform) - Register Client
- [`federationProcessConfiguration`](docs/sdks/federation/README.md#processconfiguration) - Process Entity Configuration Request
- [`federationRegister`](docs/sdks/federation/README.md#register) - Process Federation Registration Request
- [`federationRegisterForm`](docs/sdks/federation/README.md#registerform) - Process Federation Registration Request
- [`grantManagementProcess`](docs/sdks/grantmanagement/README.md#process) - Process Grant Management Request
- [`hardwareSecurityKeyCreate`](docs/sdks/hardwaresecuritykey/README.md#create) - Create Security Key
- [`hardwareSecurityKeyCreateForm`](docs/sdks/hardwaresecuritykey/README.md#createform) - Create Security Key
- [`hardwareSecurityKeyGet`](docs/sdks/hardwaresecuritykey/README.md#get) - Get Security Key
- [`hardwareSecurityKeysDelete`](docs/sdks/hardwaresecuritykeys/README.md#delete) - Delete Security Key
- [`hardwareSecurityKeysList`](docs/sdks/hardwaresecuritykeys/README.md#list) - List Security Keys
- [`introspectionEndpointProcessRequest`](docs/sdks/introspectionendpoint/README.md#processrequest) - Process OAuth 2.0 Introspection Request
- [`introspectionEndpointProcessRequestForm`](docs/sdks/introspectionendpoint/README.md#processrequestform) - Process OAuth 2.0 Introspection Request
- [`introspectionProcess`](docs/sdks/introspection/README.md#process) - Process Introspection Request
- [`introspectionProcessForm`](docs/sdks/introspection/README.md#processform) - Process Introspection Request
- [`joseVerify`](docs/sdks/jose/README.md#verify) - Verify JOSE
- [`joseVerifyForm`](docs/sdks/jose/README.md#verifyform) - Verify JOSE
- [`jwksGet`](docs/sdks/jwks/README.md#get) - Get JWK Set
- [`pushedAuthorizationEndpointProcessRequest`](docs/sdks/pushedauthorizationendpoint/README.md#processrequest) - Process Pushed Authorization Request
- [`pushedAuthorizationEndpointProcessRequestForm`](docs/sdks/pushedauthorizationendpoint/README.md#processrequestform) - Process Pushed Authorization Request
- [`revocationProcess`](docs/sdks/revocation/README.md#process) - Process Revocation Request
- [`revocationProcessForm`](docs/sdks/revocation/README.md#processform) - Process Revocation Request
- [`serviceManagementCreate`](docs/sdks/servicemanagement/README.md#create) - Create Service
- [`serviceManagementGet`](docs/sdks/servicemanagement/README.md#get) - Get Service
- [`serviceManagementGetConfiguration`](docs/sdks/servicemanagement/README.md#getconfiguration) - Get Service Configuration
- [`serviceManagementList`](docs/sdks/servicemanagement/README.md#list) - List Services
- [`serviceManagementUpdate`](docs/sdks/servicemanagement/README.md#update) - Update Service
- [`servicesDelete`](docs/sdks/services/README.md#delete) - Delete Service ⚡
- [`tokenEndpointProcess`](docs/sdks/tokenendpoint/README.md#process) - Process Token Request
- [`tokenEndpointProcessForm`](docs/sdks/tokenendpoint/README.md#processform) - Process Token Request
- [`tokenEndpointReissueIdToken`](docs/sdks/tokenendpoint/README.md#reissueidtoken) - Reissue ID Token
- [`tokenOperationsDelete`](docs/sdks/tokenoperations/README.md#delete) - Delete Access Token
- [`tokenOperationsRevokeToken`](docs/sdks/tokenoperations/README.md#revoketoken) - Revoke Access Token
- [`tokenOperationsRevokeTokenForm`](docs/sdks/tokenoperations/README.md#revoketokenform) - Revoke Access Token
- [`tokenOperationsUpdateToken`](docs/sdks/tokenoperations/README.md#updatetoken) - Update Access Token
- [`tokenOperationsUpdateTokenForm`](docs/sdks/tokenoperations/README.md#updatetokenform) - Update Access Token
- [`tokensCreate`](docs/sdks/tokens/README.md#create) - Create Access Token
- [`tokensCreateForm`](docs/sdks/tokens/README.md#createform) - Create Access Token
- [`tokensFail`](docs/sdks/tokens/README.md#fail) - Fail Token Request
- [`tokensFailForm`](docs/sdks/tokens/README.md#failform) - Fail Token Request
- [`tokensIssue`](docs/sdks/tokens/README.md#issue) - Issue Token Response
- [`tokensIssueForm`](docs/sdks/tokens/README.md#issueform) - Issue Token Response
- [`tokensList`](docs/sdks/tokens/README.md#list) - List Issued Tokens
- [`userInfoEndpointIssue`](docs/sdks/userinfoendpoint/README.md#issue) - Issue UserInfo Response
- [`userInfoEndpointIssueForm`](docs/sdks/userinfoendpoint/README.md#issueform) - Issue UserInfo Response
- [`userinfoProcess`](docs/sdks/userinfo/README.md#process) - Process UserInfo Request
- [`userinfoProcessForm`](docs/sdks/userinfo/README.md#processform) - Process UserInfo Request
- [`utilityEndpointsEcho`](docs/sdks/utilityendpoints/README.md#echo) - Echo
- [`utilityEndpointsGetInfo`](docs/sdks/utilityendpoints/README.md#getinfo) - Get Server Metadata
- [`vciMetadata`](docs/sdks/vci/README.md#metadata) - /api/{serviceId}/vci/metadata API
- [`vciMetadataForm`](docs/sdks/vci/README.md#metadataform) - /api/{serviceId}/vci/metadata API
- [`vciParseBatch`](docs/sdks/vci/README.md#parsebatch) - /api/{serviceId}/vci/batch/parse API
- [`vciParseBatchForm`](docs/sdks/vci/README.md#parsebatchform) - /api/{serviceId}/vci/batch/parse API
- [`verifiableCredentialIssuerBatchIssue`](docs/sdks/verifiablecredentialissuer/README.md#batchissue) - /api/{serviceId}/vci/batch/issue API
- [`verifiableCredentialIssuerCreateOffer`](docs/sdks/verifiablecredentialissuer/README.md#createoffer) - /api/{serviceId}/vci/offer/create API
- [`verifiableCredentialIssuerCreateOfferForm`](docs/sdks/verifiablecredentialissuer/README.md#createofferform) - /api/{serviceId}/vci/offer/create API
- [`verifiableCredentialIssuerDeferredParse`](docs/sdks/verifiablecredentialissuer/README.md#deferredparse) - /api/{serviceId}/vci/deferred/parse API
- [`verifiableCredentialIssuerDeferredParseForm`](docs/sdks/verifiablecredentialissuer/README.md#deferredparseform) - /api/{serviceId}/vci/deferred/parse API
- [`verifiableCredentialIssuerIssueDeferred`](docs/sdks/verifiablecredentialissuer/README.md#issuedeferred) - /api/{serviceId}/vci/deferred/issue API
- [`verifiableCredentialIssuerIssueJwt`](docs/sdks/verifiablecredentialissuer/README.md#issuejwt) - /api/{serviceId}/vci/jwtissuer API
- [`verifiableCredentialIssuerIssueJwtForm`](docs/sdks/verifiablecredentialissuer/README.md#issuejwtform) - /api/{serviceId}/vci/jwtissuer API
- [`verifiableCredentialIssuerJwks`](docs/sdks/verifiablecredentialissuer/README.md#jwks) - /api/{serviceId}/vci/jwks API
- [`verifiableCredentialIssuerJwksForm`](docs/sdks/verifiablecredentialissuer/README.md#jwksform) - /api/{serviceId}/vci/jwks API
- [`verifiableCredentialsIssue`](docs/sdks/verifiablecredentials/README.md#issue) - /api/{serviceId}/vci/single/issue API
- [`verifiableCredentialsOfferInfo`](docs/sdks/verifiablecredentials/README.md#offerinfo) - /api/{serviceId}/vci/offer/info API
- [`verifiableCredentialsOfferInfoForm`](docs/sdks/verifiablecredentials/README.md#offerinfoform) - /api/{serviceId}/vci/offer/info API
- [`verifiableCredentialsParse`](docs/sdks/verifiablecredentials/README.md#parse) - /api/{serviceId}/vci/single/parse API
- [`verifiableCredentialsParseForm`](docs/sdks/verifiablecredentials/README.md#parseform) - /api/{serviceId}/vci/single/parse API

</details>
<!-- End Standalone functions [standalone-funcs] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries.  If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API.  However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a retryConfig object to the call:
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.serviceManagement.get({
    serviceId: "<id>",
  }, {
    retries: {
      strategy: "backoff",
      backoff: {
        initialInterval: 1,
        maxInterval: 50,
        exponent: 1.1,
        maxElapsedTime: 100,
      },
      retryConnectionErrors: false,
    },
  });

  console.log(result);
}

run();

```

If you'd like to override the default retry strategy for all operations that support retries, you can provide a retryConfig at SDK initialization:
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  retryConfig: {
    strategy: "backoff",
    backoff: {
      initialInterval: 1,
      maxInterval: 50,
      exponent: 1.1,
      maxElapsedTime: 100,
    },
    retryConnectionErrors: false,
  },
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.serviceManagement.get({
    serviceId: "<id>",
  });

  console.log(result);
}

run();

```
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

[`AutheleteBundledError`](./src/models/errors/autheletebundlederror.ts) is the base class for all HTTP error responses. It has the following properties:

| Property            | Type       | Description                                                                             |
| ------------------- | ---------- | --------------------------------------------------------------------------------------- |
| `error.message`     | `string`   | Error message                                                                           |
| `error.statusCode`  | `number`   | HTTP response status code eg `404`                                                      |
| `error.headers`     | `Headers`  | HTTP response headers                                                                   |
| `error.body`        | `string`   | HTTP body. Can be empty string if no body is returned.                                  |
| `error.rawResponse` | `Response` | Raw HTTP response                                                                       |
| `error.data$`       |            | Optional. Some errors may contain structured data. [See Error Classes](#error-classes). |

### Example
```typescript
import { AutheleteBundled } from "authelete-bundled";
import * as errors from "authelete-bundled/models/errors";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  try {
    const result = await autheleteBundled.serviceManagement.get({
      serviceId: "<id>",
    });

    console.log(result);
  } catch (error) {
    // The base class for HTTP error responses
    if (error instanceof errors.AutheleteBundledError) {
      console.log(error.message);
      console.log(error.statusCode);
      console.log(error.body);
      console.log(error.headers);

      // Depending on the method different errors may be thrown
      if (error instanceof errors.BadRequestError) {
        console.log(error.data$.resultCode); // string
        console.log(error.data$.resultMessage); // string
      }
    }
  }
}

run();

```

### Error Classes
**Primary errors:**
* [`AutheleteBundledError`](./src/models/errors/autheletebundlederror.ts): The base class for HTTP error responses.
  * [`BadRequestError`](./src/models/errors/badrequesterror.ts): . Status code `400`. *
  * [`UnauthorizedError`](./src/models/errors/unauthorizederror.ts): . Status code `401`. *
  * [`ForbiddenError`](./src/models/errors/forbiddenerror.ts): . Status code `403`. *
  * [`InternalServerError`](./src/models/errors/internalservererror.ts): . Status code `500`. *

<details><summary>Less common errors (6)</summary>

<br />

**Network errors:**
* [`ConnectionError`](./src/models/errors/httpclienterrors.ts): HTTP client was unable to make a request to a server.
* [`RequestTimeoutError`](./src/models/errors/httpclienterrors.ts): HTTP request timed out due to an AbortSignal signal.
* [`RequestAbortedError`](./src/models/errors/httpclienterrors.ts): HTTP request was aborted by the client.
* [`InvalidRequestError`](./src/models/errors/httpclienterrors.ts): Any input used to create a request is invalid.
* [`UnexpectedClientError`](./src/models/errors/httpclienterrors.ts): Unrecognised or unexpected error.


**Inherit from [`AutheleteBundledError`](./src/models/errors/autheletebundlederror.ts)**:
* [`ResponseValidationError`](./src/models/errors/responsevalidationerror.ts): Type mismatch between the data returned from the server and the structure expected by the SDK. See `error.rawValue` for the raw value and `error.pretty()` for a nicely formatted multi-line string.

</details>

\* Check [the method documentation](#available-resources-and-operations) to see if the error is applicable.
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Select Server by Index

You can override the default server globally by passing a server index to the `serverIdx: number` optional parameter when initializing the SDK client instance. The selected server will then be used as the default on the operations that use it. This table lists the indexes associated with the available servers:

| #   | Server                    | Description         |
| --- | ------------------------- | ------------------- |
| 0   | `https://us.authlete.com` | 🇺🇸 US Cluster     |
| 1   | `https://jp.authlete.com` | 🇯🇵 Japan Cluster  |
| 2   | `https://eu.authlete.com` | 🇪🇺 Europe Cluster |
| 3   | `https://br.authlete.com` | 🇧🇷 Brazil Cluster |

#### Example

```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  serverIdx: 3,
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.serviceManagement.get({
    serviceId: "<id>",
  });

  console.log(result);
}

run();

```

### Override Server URL Per-Client

The default server can also be overridden globally by passing a URL to the `serverURL: string` optional parameter when initializing the SDK client instance. For example:
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  serverURL: "https://br.authlete.com",
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.serviceManagement.get({
    serviceId: "<id>",
  });

  console.log(result);
}

run();

```

### Override Server URL Per-Operation

The server URL can also be overridden on a per-operation basis, provided a server list was specified for the operation. For example:
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.serviceManagement.get({
    serviceId: "<id>",
  }, {
    serverURL: "https://br.authlete.com",
  });

  console.log(result);
}

run();

```
<!-- End Server Selection [server] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The TypeScript SDK makes API calls using an `HTTPClient` that wraps the native
[Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API). This
client is a thin wrapper around `fetch` and provides the ability to attach hooks
around the request lifecycle that can be used to modify the request or handle
errors and response.

The `HTTPClient` constructor takes an optional `fetcher` argument that can be
used to integrate a third-party HTTP client or when writing tests to mock out
the HTTP client and feed in fixtures.

The following example shows how to use the `"beforeRequest"` hook to to add a
custom header and a timeout to requests and how to use the `"requestError"` hook
to log errors:

```typescript
import { AutheleteBundled } from "authelete-bundled";
import { HTTPClient } from "authelete-bundled/lib/http";

const httpClient = new HTTPClient({
  // fetcher takes a function that has the same signature as native `fetch`.
  fetcher: (request) => {
    return fetch(request);
  }
});

httpClient.addHook("beforeRequest", (request) => {
  const nextRequest = new Request(request, {
    signal: request.signal || AbortSignal.timeout(5000)
  });

  nextRequest.headers.set("x-custom-header", "custom value");

  return nextRequest;
});

httpClient.addHook("requestError", (error, request) => {
  console.group("Request Error");
  console.log("Reason:", `${error}`);
  console.log("Endpoint:", `${request.method} ${request.url}`);
  console.groupEnd();
});

const sdk = new AutheleteBundled({ httpClient });
```
<!-- End Custom HTTP Client [http-client] -->

<!-- Start Debugging [debug] -->
## Debugging

You can setup your SDK to emit debug logs for SDK requests and responses.

You can pass a logger that matches `console`'s interface as an SDK option.

> [!WARNING]
> Beware that debug logging will reveal secrets, like API tokens in headers, in log messages printed to a console or files. It's recommended to use this feature only during local development and not in production.

```typescript
import { AutheleteBundled } from "authelete-bundled";

const sdk = new AutheleteBundled({ debugLogger: console });
```

You can also enable a default debug logger by setting an environment variable `AUTHELETEBUNDLED_DEBUG` to true.
<!-- End Debugging [debug] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### SDK Created by [Speakeasy](https://www.speakeasy.com/?utm_source=authelete-bundled&utm_campaign=typescript)
