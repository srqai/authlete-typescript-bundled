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

> [!TIP]
> To finish publishing your SDK to npm and others you must [run your first generation action](https://www.speakeasy.com/docs/github-setup#step-by-step-guide).


The SDK can be installed with either [npm](https://www.npmjs.com/), [pnpm](https://pnpm.io/), [bun](https://bun.sh/) or [yarn](https://classic.yarnpkg.com/en/) package managers.

### NPM

```bash
npm add https://github.com/srqai/authlete-typescript-bundled
```

### PNPM

```bash
pnpm add https://github.com/srqai/authlete-typescript-bundled
```

### Bun

```bash
bun add https://github.com/srqai/authlete-typescript-bundled
```

### Yarn

```bash
yarn add https://github.com/srqai/authlete-typescript-bundled zod

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
  const result = await autheleteBundled.serviceManagement.serviceGetApi({
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
  const result = await autheleteBundled.serviceManagement.serviceGetApi({
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


### [authorizationEndpoint](docs/sdks/authorizationendpoint/README.md)

* [authAuthorizationApi](docs/sdks/authorizationendpoint/README.md#authauthorizationapi) - Process Authorization Request
* [authAuthorizationApiForm](docs/sdks/authorizationendpoint/README.md#authauthorizationapiform) - Process Authorization Request
* [authAuthorizationFailApi](docs/sdks/authorizationendpoint/README.md#authauthorizationfailapi) - Fail Authorization Request
* [authAuthorizationFailApiForm](docs/sdks/authorizationendpoint/README.md#authauthorizationfailapiform) - Fail Authorization Request
* [authAuthorizationIssueApi](docs/sdks/authorizationendpoint/README.md#authauthorizationissueapi) - Issue Authorization Response
* [authAuthorizationIssueApiForm](docs/sdks/authorizationendpoint/README.md#authauthorizationissueapiform) - Issue Authorization Response
* [getApiServiceIdAuthAuthorizationTicketInfo](docs/sdks/authorizationendpoint/README.md#getapiserviceidauthauthorizationticketinfo) - Get Ticket Information
* [postApiServiceIdAuthAuthorizationTicketUpdate](docs/sdks/authorizationendpoint/README.md#postapiserviceidauthauthorizationticketupdate) - Update Ticket Information
* [postApiServiceIdAuthAuthorizationTicketUpdateForm](docs/sdks/authorizationendpoint/README.md#postapiserviceidauthauthorizationticketupdateform) - Update Ticket Information

### [ciba](docs/sdks/ciba/README.md)

* [backchannelAuthenticationApi](docs/sdks/ciba/README.md#backchannelauthenticationapi) - Process Backchannel Authentication Request
* [backchannelAuthenticationApiForm](docs/sdks/ciba/README.md#backchannelauthenticationapiform) - Process Backchannel Authentication Request
* [backchannelAuthenticationIssueApi](docs/sdks/ciba/README.md#backchannelauthenticationissueapi) - Issue Backchannel Authentication Response
* [backchannelAuthenticationIssueApiForm](docs/sdks/ciba/README.md#backchannelauthenticationissueapiform) - Issue Backchannel Authentication Response
* [backchannelAuthenticationFailApi](docs/sdks/ciba/README.md#backchannelauthenticationfailapi) - Fail Backchannel Authentication Request
* [backchannelAuthenticationFailApiForm](docs/sdks/ciba/README.md#backchannelauthenticationfailapiform) - Fail Backchannel Authentication Request
* [backchannelAuthenticationCompleteApi](docs/sdks/ciba/README.md#backchannelauthenticationcompleteapi) - Complete Backchannel Authentication
* [backchannelAuthenticationCompleteApiForm](docs/sdks/ciba/README.md#backchannelauthenticationcompleteapiform) - Complete Backchannel Authentication

### [clientManagement](docs/sdks/clientmanagement/README.md)

* [clientGetApi](docs/sdks/clientmanagement/README.md#clientgetapi) - Get Client
* [clientGetListApi](docs/sdks/clientmanagement/README.md#clientgetlistapi) - List Clients
* [clientCreateApi](docs/sdks/clientmanagement/README.md#clientcreateapi) - Create Client
* [clientUpdateApi](docs/sdks/clientmanagement/README.md#clientupdateapi) - Update Client
* [clientDeleteApi](docs/sdks/clientmanagement/README.md#clientdeleteapi) - Delete Client ⚡
* [clientFlagUpdateApi](docs/sdks/clientmanagement/README.md#clientflagupdateapi) - Update Client Lock
* [clientSecretRefreshApi](docs/sdks/clientmanagement/README.md#clientsecretrefreshapi) - Rotate Client Secret
* [clientSecretUpdateApi](docs/sdks/clientmanagement/README.md#clientsecretupdateapi) - Update Client Secret
* [clientSecretUpdateApiForm](docs/sdks/clientmanagement/README.md#clientsecretupdateapiform) - Update Client Secret
* [clientAuthorizationGetListApi](docs/sdks/clientmanagement/README.md#clientauthorizationgetlistapi) - Get Authorized Applications
* [clientAuthorizationUpdateApi](docs/sdks/clientmanagement/README.md#clientauthorizationupdateapi) - Update Client Tokens
* [clientAuthorizationUpdateApiForm](docs/sdks/clientmanagement/README.md#clientauthorizationupdateapiform) - Update Client Tokens
* [clientAuthorizationDeleteApi](docs/sdks/clientmanagement/README.md#clientauthorizationdeleteapi) - Delete Client Tokens
* [clientGrantedScopesGetApi](docs/sdks/clientmanagement/README.md#clientgrantedscopesgetapi) - Get Granted Scopes
* [clientGrantedScopesDeleteApi](docs/sdks/clientmanagement/README.md#clientgrantedscopesdeleteapi) - Delete Granted Scopes
* [clientExtensionRequestablesScopesGetApi](docs/sdks/clientmanagement/README.md#clientextensionrequestablesscopesgetapi) - Get Requestable Scopes
* [clientExtensionRequestablesScopesUpdateApi](docs/sdks/clientmanagement/README.md#clientextensionrequestablesscopesupdateapi) - Update Requestable Scopes
* [clientExtensionRequestablesScopesDeleteApi](docs/sdks/clientmanagement/README.md#clientextensionrequestablesscopesdeleteapi) - Delete Requestable Scopes

### [deviceFlow](docs/sdks/deviceflow/README.md)

* [deviceAuthorizationApi](docs/sdks/deviceflow/README.md#deviceauthorizationapi) - Process Device Authorization Request
* [deviceAuthorizationApiForm](docs/sdks/deviceflow/README.md#deviceauthorizationapiform) - Process Device Authorization Request
* [deviceVerificationApi](docs/sdks/deviceflow/README.md#deviceverificationapi) - Process Device Verification Request
* [deviceVerificationApiForm](docs/sdks/deviceflow/README.md#deviceverificationapiform) - Process Device Verification Request
* [deviceCompleteApi](docs/sdks/deviceflow/README.md#devicecompleteapi) - Complete Device Authorization
* [deviceCompleteApiForm](docs/sdks/deviceflow/README.md#devicecompleteapiform) - Complete Device Authorization

### [dynamicClientRegistration](docs/sdks/dynamicclientregistration/README.md)

* [clientRegistrationApi](docs/sdks/dynamicclientregistration/README.md#clientregistrationapi) - Register Client
* [clientRegistrationApiForm](docs/sdks/dynamicclientregistration/README.md#clientregistrationapiform) - Register Client
* [clientRegistrationGetApi](docs/sdks/dynamicclientregistration/README.md#clientregistrationgetapi) - Get Client
* [clientRegistrationUpdateApi](docs/sdks/dynamicclientregistration/README.md#clientregistrationupdateapi) - Update Client
* [clientRegistrationUpdateApiForm](docs/sdks/dynamicclientregistration/README.md#clientregistrationupdateapiform) - Update Client
* [clientRegistrationDeleteApi](docs/sdks/dynamicclientregistration/README.md#clientregistrationdeleteapi) - Delete Client
* [clientRegistrationDeleteApiForm](docs/sdks/dynamicclientregistration/README.md#clientregistrationdeleteapiform) - Delete Client

### [federationEndpoint](docs/sdks/federationendpoint/README.md)

* [federationConfigurationApi](docs/sdks/federationendpoint/README.md#federationconfigurationapi) - Process Entity Configuration Request
* [federationRegistrationApi](docs/sdks/federationendpoint/README.md#federationregistrationapi) - Process Federation Registration Request
* [federationRegistrationApiForm](docs/sdks/federationendpoint/README.md#federationregistrationapiform) - Process Federation Registration Request

### [grantManagementEndpoint](docs/sdks/grantmanagementendpoint/README.md)

* [grantMApi](docs/sdks/grantmanagementendpoint/README.md#grantmapi) - Process Grant Management Request

### [hardwareSecurityKey](docs/sdks/hardwaresecuritykey/README.md)

* [hskCreateApi](docs/sdks/hardwaresecuritykey/README.md#hskcreateapi) - Create Security Key
* [hskCreateApiForm](docs/sdks/hardwaresecuritykey/README.md#hskcreateapiform) - Create Security Key
* [hskDeleteApi](docs/sdks/hardwaresecuritykey/README.md#hskdeleteapi) - Delete Security Key
* [hskGetApi](docs/sdks/hardwaresecuritykey/README.md#hskgetapi) - Get Security Key
* [hskGetListApi](docs/sdks/hardwaresecuritykey/README.md#hskgetlistapi) - List Security Keys

### [introspectionEndpoint](docs/sdks/introspectionendpoint/README.md)

* [authIntrospectionApi](docs/sdks/introspectionendpoint/README.md#authintrospectionapi) - Process Introspection Request
* [authIntrospectionApiForm](docs/sdks/introspectionendpoint/README.md#authintrospectionapiform) - Process Introspection Request
* [authIntrospectionStandardApi](docs/sdks/introspectionendpoint/README.md#authintrospectionstandardapi) - Process OAuth 2.0 Introspection Request
* [authIntrospectionStandardApiForm](docs/sdks/introspectionendpoint/README.md#authintrospectionstandardapiform) - Process OAuth 2.0 Introspection Request

### [joseObject](docs/sdks/joseobject/README.md)

* [joseVerifyApi](docs/sdks/joseobject/README.md#joseverifyapi) - Verify JOSE
* [joseVerifyApiForm](docs/sdks/joseobject/README.md#joseverifyapiform) - Verify JOSE

### [jwkSetEndpoint](docs/sdks/jwksetendpoint/README.md)

* [serviceJwksGetApi](docs/sdks/jwksetendpoint/README.md#servicejwksgetapi) - Get JWK Set

### [pushedAuthorizationEndpoint](docs/sdks/pushedauthorizationendpoint/README.md)

* [pushedAuthReqApi](docs/sdks/pushedauthorizationendpoint/README.md#pushedauthreqapi) - Process Pushed Authorization Request
* [pushedAuthReqApiForm](docs/sdks/pushedauthorizationendpoint/README.md#pushedauthreqapiform) - Process Pushed Authorization Request

### [revocationEndpoint](docs/sdks/revocationendpoint/README.md)

* [authRevocationApi](docs/sdks/revocationendpoint/README.md#authrevocationapi) - Process Revocation Request
* [authRevocationApiForm](docs/sdks/revocationendpoint/README.md#authrevocationapiform) - Process Revocation Request

### [serviceManagement](docs/sdks/servicemanagement/README.md)

* [serviceGetApi](docs/sdks/servicemanagement/README.md#servicegetapi) - Get Service
* [serviceGetListApi](docs/sdks/servicemanagement/README.md#servicegetlistapi) - List Services
* [serviceCreateApi](docs/sdks/servicemanagement/README.md#servicecreateapi) - Create Service
* [serviceUpdateApi](docs/sdks/servicemanagement/README.md#serviceupdateapi) - Update Service
* [serviceDeleteApi](docs/sdks/servicemanagement/README.md#servicedeleteapi) - Delete Service ⚡
* [serviceConfigurationApi](docs/sdks/servicemanagement/README.md#serviceconfigurationapi) - Get Service Configuration

### [tokenEndpoint](docs/sdks/tokenendpoint/README.md)

* [authTokenApi](docs/sdks/tokenendpoint/README.md#authtokenapi) - Process Token Request
* [authTokenApiForm](docs/sdks/tokenendpoint/README.md#authtokenapiform) - Process Token Request
* [authTokenFailApi](docs/sdks/tokenendpoint/README.md#authtokenfailapi) - Fail Token Request
* [authTokenFailApiForm](docs/sdks/tokenendpoint/README.md#authtokenfailapiform) - Fail Token Request
* [authTokenIssueApi](docs/sdks/tokenendpoint/README.md#authtokenissueapi) - Issue Token Response
* [authTokenIssueApiForm](docs/sdks/tokenendpoint/README.md#authtokenissueapiform) - Issue Token Response
* [idtokenReissueApi](docs/sdks/tokenendpoint/README.md#idtokenreissueapi) - Reissue ID Token

### [tokenOperations](docs/sdks/tokenoperations/README.md)

* [authTokenGetListApi](docs/sdks/tokenoperations/README.md#authtokengetlistapi) - List Issued Tokens
* [authTokenCreateApi](docs/sdks/tokenoperations/README.md#authtokencreateapi) - Create Access Token
* [authTokenCreateApiForm](docs/sdks/tokenoperations/README.md#authtokencreateapiform) - Create Access Token
* [authTokenUpdateApi](docs/sdks/tokenoperations/README.md#authtokenupdateapi) - Update Access Token
* [authTokenUpdateApiForm](docs/sdks/tokenoperations/README.md#authtokenupdateapiform) - Update Access Token
* [authTokenDeleteApi](docs/sdks/tokenoperations/README.md#authtokendeleteapi) - Delete Access Token
* [authTokenRevokeApi](docs/sdks/tokenoperations/README.md#authtokenrevokeapi) - Revoke Access Token
* [authTokenRevokeApiForm](docs/sdks/tokenoperations/README.md#authtokenrevokeapiform) - Revoke Access Token

### [userInfoEndpoint](docs/sdks/userinfoendpoint/README.md)

* [authUserinfoApi](docs/sdks/userinfoendpoint/README.md#authuserinfoapi) - Process UserInfo Request
* [authUserinfoApiForm](docs/sdks/userinfoendpoint/README.md#authuserinfoapiform) - Process UserInfo Request
* [authUserinfoIssueApi](docs/sdks/userinfoendpoint/README.md#authuserinfoissueapi) - Issue UserInfo Response
* [authUserinfoIssueApiForm](docs/sdks/userinfoendpoint/README.md#authuserinfoissueapiform) - Issue UserInfo Response

### [utilityEndpoints](docs/sdks/utilityendpoints/README.md)

* [infoApi](docs/sdks/utilityendpoints/README.md#infoapi) - Get Server Metadata
* [miscEchoApi](docs/sdks/utilityendpoints/README.md#miscechoapi) - Echo

### [verifiableCredentialIssuer](docs/sdks/verifiablecredentialissuer/README.md)

* [vciMetadataApi](docs/sdks/verifiablecredentialissuer/README.md#vcimetadataapi) - /api/{serviceId}/vci/metadata API
* [vciMetadataApiForm](docs/sdks/verifiablecredentialissuer/README.md#vcimetadataapiform) - /api/{serviceId}/vci/metadata API
* [vciJwtissuerApi](docs/sdks/verifiablecredentialissuer/README.md#vcijwtissuerapi) - /api/{serviceId}/vci/jwtissuer API
* [vciJwtissuerApiForm](docs/sdks/verifiablecredentialissuer/README.md#vcijwtissuerapiform) - /api/{serviceId}/vci/jwtissuer API
* [vciJwksApi](docs/sdks/verifiablecredentialissuer/README.md#vcijwksapi) - /api/{serviceId}/vci/jwks API
* [vciJwksApiForm](docs/sdks/verifiablecredentialissuer/README.md#vcijwksapiform) - /api/{serviceId}/vci/jwks API
* [vciOfferCreateApi](docs/sdks/verifiablecredentialissuer/README.md#vcioffercreateapi) - /api/{serviceId}/vci/offer/create API
* [vciOfferCreateApiForm](docs/sdks/verifiablecredentialissuer/README.md#vcioffercreateapiform) - /api/{serviceId}/vci/offer/create API
* [vciOfferInfoApi](docs/sdks/verifiablecredentialissuer/README.md#vciofferinfoapi) - /api/{serviceId}/vci/offer/info API
* [vciOfferInfoApiForm](docs/sdks/verifiablecredentialissuer/README.md#vciofferinfoapiform) - /api/{serviceId}/vci/offer/info API
* [vciSingleParseApi](docs/sdks/verifiablecredentialissuer/README.md#vcisingleparseapi) - /api/{serviceId}/vci/single/parse API
* [vciSingleParseApiForm](docs/sdks/verifiablecredentialissuer/README.md#vcisingleparseapiform) - /api/{serviceId}/vci/single/parse API
* [vciSingleIssueApi](docs/sdks/verifiablecredentialissuer/README.md#vcisingleissueapi) - /api/{serviceId}/vci/single/issue API
* [vciBatchParseApi](docs/sdks/verifiablecredentialissuer/README.md#vcibatchparseapi) - /api/{serviceId}/vci/batch/parse API
* [vciBatchParseApiForm](docs/sdks/verifiablecredentialissuer/README.md#vcibatchparseapiform) - /api/{serviceId}/vci/batch/parse API
* [vciBatchIssueApi](docs/sdks/verifiablecredentialissuer/README.md#vcibatchissueapi) - /api/{serviceId}/vci/batch/issue API
* [vciDeferredParseApi](docs/sdks/verifiablecredentialissuer/README.md#vcideferredparseapi) - /api/{serviceId}/vci/deferred/parse API
* [vciDeferredParseApiForm](docs/sdks/verifiablecredentialissuer/README.md#vcideferredparseapiform) - /api/{serviceId}/vci/deferred/parse API
* [vciDeferredIssueApi](docs/sdks/verifiablecredentialissuer/README.md#vcideferredissueapi) - /api/{serviceId}/vci/deferred/issue API

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

- [`authorizationEndpointAuthAuthorizationApi`](docs/sdks/authorizationendpoint/README.md#authauthorizationapi) - Process Authorization Request
- [`authorizationEndpointAuthAuthorizationApiForm`](docs/sdks/authorizationendpoint/README.md#authauthorizationapiform) - Process Authorization Request
- [`authorizationEndpointAuthAuthorizationFailApi`](docs/sdks/authorizationendpoint/README.md#authauthorizationfailapi) - Fail Authorization Request
- [`authorizationEndpointAuthAuthorizationFailApiForm`](docs/sdks/authorizationendpoint/README.md#authauthorizationfailapiform) - Fail Authorization Request
- [`authorizationEndpointAuthAuthorizationIssueApi`](docs/sdks/authorizationendpoint/README.md#authauthorizationissueapi) - Issue Authorization Response
- [`authorizationEndpointAuthAuthorizationIssueApiForm`](docs/sdks/authorizationendpoint/README.md#authauthorizationissueapiform) - Issue Authorization Response
- [`authorizationEndpointGetApiServiceIdAuthAuthorizationTicketInfo`](docs/sdks/authorizationendpoint/README.md#getapiserviceidauthauthorizationticketinfo) - Get Ticket Information
- [`authorizationEndpointPostApiServiceIdAuthAuthorizationTicketUpdate`](docs/sdks/authorizationendpoint/README.md#postapiserviceidauthauthorizationticketupdate) - Update Ticket Information
- [`authorizationEndpointPostApiServiceIdAuthAuthorizationTicketUpdateForm`](docs/sdks/authorizationendpoint/README.md#postapiserviceidauthauthorizationticketupdateform) - Update Ticket Information
- [`cibaBackchannelAuthenticationApi`](docs/sdks/ciba/README.md#backchannelauthenticationapi) - Process Backchannel Authentication Request
- [`cibaBackchannelAuthenticationApiForm`](docs/sdks/ciba/README.md#backchannelauthenticationapiform) - Process Backchannel Authentication Request
- [`cibaBackchannelAuthenticationCompleteApi`](docs/sdks/ciba/README.md#backchannelauthenticationcompleteapi) - Complete Backchannel Authentication
- [`cibaBackchannelAuthenticationCompleteApiForm`](docs/sdks/ciba/README.md#backchannelauthenticationcompleteapiform) - Complete Backchannel Authentication
- [`cibaBackchannelAuthenticationFailApi`](docs/sdks/ciba/README.md#backchannelauthenticationfailapi) - Fail Backchannel Authentication Request
- [`cibaBackchannelAuthenticationFailApiForm`](docs/sdks/ciba/README.md#backchannelauthenticationfailapiform) - Fail Backchannel Authentication Request
- [`cibaBackchannelAuthenticationIssueApi`](docs/sdks/ciba/README.md#backchannelauthenticationissueapi) - Issue Backchannel Authentication Response
- [`cibaBackchannelAuthenticationIssueApiForm`](docs/sdks/ciba/README.md#backchannelauthenticationissueapiform) - Issue Backchannel Authentication Response
- [`clientManagementClientAuthorizationDeleteApi`](docs/sdks/clientmanagement/README.md#clientauthorizationdeleteapi) - Delete Client Tokens
- [`clientManagementClientAuthorizationGetListApi`](docs/sdks/clientmanagement/README.md#clientauthorizationgetlistapi) - Get Authorized Applications
- [`clientManagementClientAuthorizationUpdateApi`](docs/sdks/clientmanagement/README.md#clientauthorizationupdateapi) - Update Client Tokens
- [`clientManagementClientAuthorizationUpdateApiForm`](docs/sdks/clientmanagement/README.md#clientauthorizationupdateapiform) - Update Client Tokens
- [`clientManagementClientCreateApi`](docs/sdks/clientmanagement/README.md#clientcreateapi) - Create Client
- [`clientManagementClientDeleteApi`](docs/sdks/clientmanagement/README.md#clientdeleteapi) - Delete Client ⚡
- [`clientManagementClientExtensionRequestablesScopesDeleteApi`](docs/sdks/clientmanagement/README.md#clientextensionrequestablesscopesdeleteapi) - Delete Requestable Scopes
- [`clientManagementClientExtensionRequestablesScopesGetApi`](docs/sdks/clientmanagement/README.md#clientextensionrequestablesscopesgetapi) - Get Requestable Scopes
- [`clientManagementClientExtensionRequestablesScopesUpdateApi`](docs/sdks/clientmanagement/README.md#clientextensionrequestablesscopesupdateapi) - Update Requestable Scopes
- [`clientManagementClientFlagUpdateApi`](docs/sdks/clientmanagement/README.md#clientflagupdateapi) - Update Client Lock
- [`clientManagementClientGetApi`](docs/sdks/clientmanagement/README.md#clientgetapi) - Get Client
- [`clientManagementClientGetListApi`](docs/sdks/clientmanagement/README.md#clientgetlistapi) - List Clients
- [`clientManagementClientGrantedScopesDeleteApi`](docs/sdks/clientmanagement/README.md#clientgrantedscopesdeleteapi) - Delete Granted Scopes
- [`clientManagementClientGrantedScopesGetApi`](docs/sdks/clientmanagement/README.md#clientgrantedscopesgetapi) - Get Granted Scopes
- [`clientManagementClientSecretRefreshApi`](docs/sdks/clientmanagement/README.md#clientsecretrefreshapi) - Rotate Client Secret
- [`clientManagementClientSecretUpdateApi`](docs/sdks/clientmanagement/README.md#clientsecretupdateapi) - Update Client Secret
- [`clientManagementClientSecretUpdateApiForm`](docs/sdks/clientmanagement/README.md#clientsecretupdateapiform) - Update Client Secret
- [`clientManagementClientUpdateApi`](docs/sdks/clientmanagement/README.md#clientupdateapi) - Update Client
- [`deviceFlowDeviceAuthorizationApi`](docs/sdks/deviceflow/README.md#deviceauthorizationapi) - Process Device Authorization Request
- [`deviceFlowDeviceAuthorizationApiForm`](docs/sdks/deviceflow/README.md#deviceauthorizationapiform) - Process Device Authorization Request
- [`deviceFlowDeviceCompleteApi`](docs/sdks/deviceflow/README.md#devicecompleteapi) - Complete Device Authorization
- [`deviceFlowDeviceCompleteApiForm`](docs/sdks/deviceflow/README.md#devicecompleteapiform) - Complete Device Authorization
- [`deviceFlowDeviceVerificationApi`](docs/sdks/deviceflow/README.md#deviceverificationapi) - Process Device Verification Request
- [`deviceFlowDeviceVerificationApiForm`](docs/sdks/deviceflow/README.md#deviceverificationapiform) - Process Device Verification Request
- [`dynamicClientRegistrationClientRegistrationApi`](docs/sdks/dynamicclientregistration/README.md#clientregistrationapi) - Register Client
- [`dynamicClientRegistrationClientRegistrationApiForm`](docs/sdks/dynamicclientregistration/README.md#clientregistrationapiform) - Register Client
- [`dynamicClientRegistrationClientRegistrationDeleteApi`](docs/sdks/dynamicclientregistration/README.md#clientregistrationdeleteapi) - Delete Client
- [`dynamicClientRegistrationClientRegistrationDeleteApiForm`](docs/sdks/dynamicclientregistration/README.md#clientregistrationdeleteapiform) - Delete Client
- [`dynamicClientRegistrationClientRegistrationGetApi`](docs/sdks/dynamicclientregistration/README.md#clientregistrationgetapi) - Get Client
- [`dynamicClientRegistrationClientRegistrationUpdateApi`](docs/sdks/dynamicclientregistration/README.md#clientregistrationupdateapi) - Update Client
- [`dynamicClientRegistrationClientRegistrationUpdateApiForm`](docs/sdks/dynamicclientregistration/README.md#clientregistrationupdateapiform) - Update Client
- [`federationEndpointFederationConfigurationApi`](docs/sdks/federationendpoint/README.md#federationconfigurationapi) - Process Entity Configuration Request
- [`federationEndpointFederationRegistrationApi`](docs/sdks/federationendpoint/README.md#federationregistrationapi) - Process Federation Registration Request
- [`federationEndpointFederationRegistrationApiForm`](docs/sdks/federationendpoint/README.md#federationregistrationapiform) - Process Federation Registration Request
- [`grantManagementEndpointGrantMApi`](docs/sdks/grantmanagementendpoint/README.md#grantmapi) - Process Grant Management Request
- [`hardwareSecurityKeyHskCreateApi`](docs/sdks/hardwaresecuritykey/README.md#hskcreateapi) - Create Security Key
- [`hardwareSecurityKeyHskCreateApiForm`](docs/sdks/hardwaresecuritykey/README.md#hskcreateapiform) - Create Security Key
- [`hardwareSecurityKeyHskDeleteApi`](docs/sdks/hardwaresecuritykey/README.md#hskdeleteapi) - Delete Security Key
- [`hardwareSecurityKeyHskGetApi`](docs/sdks/hardwaresecuritykey/README.md#hskgetapi) - Get Security Key
- [`hardwareSecurityKeyHskGetListApi`](docs/sdks/hardwaresecuritykey/README.md#hskgetlistapi) - List Security Keys
- [`introspectionEndpointAuthIntrospectionApi`](docs/sdks/introspectionendpoint/README.md#authintrospectionapi) - Process Introspection Request
- [`introspectionEndpointAuthIntrospectionApiForm`](docs/sdks/introspectionendpoint/README.md#authintrospectionapiform) - Process Introspection Request
- [`introspectionEndpointAuthIntrospectionStandardApi`](docs/sdks/introspectionendpoint/README.md#authintrospectionstandardapi) - Process OAuth 2.0 Introspection Request
- [`introspectionEndpointAuthIntrospectionStandardApiForm`](docs/sdks/introspectionendpoint/README.md#authintrospectionstandardapiform) - Process OAuth 2.0 Introspection Request
- [`joseObjectJoseVerifyApi`](docs/sdks/joseobject/README.md#joseverifyapi) - Verify JOSE
- [`joseObjectJoseVerifyApiForm`](docs/sdks/joseobject/README.md#joseverifyapiform) - Verify JOSE
- [`jwkSetEndpointServiceJwksGetApi`](docs/sdks/jwksetendpoint/README.md#servicejwksgetapi) - Get JWK Set
- [`pushedAuthorizationEndpointPushedAuthReqApi`](docs/sdks/pushedauthorizationendpoint/README.md#pushedauthreqapi) - Process Pushed Authorization Request
- [`pushedAuthorizationEndpointPushedAuthReqApiForm`](docs/sdks/pushedauthorizationendpoint/README.md#pushedauthreqapiform) - Process Pushed Authorization Request
- [`revocationEndpointAuthRevocationApi`](docs/sdks/revocationendpoint/README.md#authrevocationapi) - Process Revocation Request
- [`revocationEndpointAuthRevocationApiForm`](docs/sdks/revocationendpoint/README.md#authrevocationapiform) - Process Revocation Request
- [`serviceManagementServiceConfigurationApi`](docs/sdks/servicemanagement/README.md#serviceconfigurationapi) - Get Service Configuration
- [`serviceManagementServiceCreateApi`](docs/sdks/servicemanagement/README.md#servicecreateapi) - Create Service
- [`serviceManagementServiceDeleteApi`](docs/sdks/servicemanagement/README.md#servicedeleteapi) - Delete Service ⚡
- [`serviceManagementServiceGetApi`](docs/sdks/servicemanagement/README.md#servicegetapi) - Get Service
- [`serviceManagementServiceGetListApi`](docs/sdks/servicemanagement/README.md#servicegetlistapi) - List Services
- [`serviceManagementServiceUpdateApi`](docs/sdks/servicemanagement/README.md#serviceupdateapi) - Update Service
- [`tokenEndpointAuthTokenApi`](docs/sdks/tokenendpoint/README.md#authtokenapi) - Process Token Request
- [`tokenEndpointAuthTokenApiForm`](docs/sdks/tokenendpoint/README.md#authtokenapiform) - Process Token Request
- [`tokenEndpointAuthTokenFailApi`](docs/sdks/tokenendpoint/README.md#authtokenfailapi) - Fail Token Request
- [`tokenEndpointAuthTokenFailApiForm`](docs/sdks/tokenendpoint/README.md#authtokenfailapiform) - Fail Token Request
- [`tokenEndpointAuthTokenIssueApi`](docs/sdks/tokenendpoint/README.md#authtokenissueapi) - Issue Token Response
- [`tokenEndpointAuthTokenIssueApiForm`](docs/sdks/tokenendpoint/README.md#authtokenissueapiform) - Issue Token Response
- [`tokenEndpointIdtokenReissueApi`](docs/sdks/tokenendpoint/README.md#idtokenreissueapi) - Reissue ID Token
- [`tokenOperationsAuthTokenCreateApi`](docs/sdks/tokenoperations/README.md#authtokencreateapi) - Create Access Token
- [`tokenOperationsAuthTokenCreateApiForm`](docs/sdks/tokenoperations/README.md#authtokencreateapiform) - Create Access Token
- [`tokenOperationsAuthTokenDeleteApi`](docs/sdks/tokenoperations/README.md#authtokendeleteapi) - Delete Access Token
- [`tokenOperationsAuthTokenGetListApi`](docs/sdks/tokenoperations/README.md#authtokengetlistapi) - List Issued Tokens
- [`tokenOperationsAuthTokenRevokeApi`](docs/sdks/tokenoperations/README.md#authtokenrevokeapi) - Revoke Access Token
- [`tokenOperationsAuthTokenRevokeApiForm`](docs/sdks/tokenoperations/README.md#authtokenrevokeapiform) - Revoke Access Token
- [`tokenOperationsAuthTokenUpdateApi`](docs/sdks/tokenoperations/README.md#authtokenupdateapi) - Update Access Token
- [`tokenOperationsAuthTokenUpdateApiForm`](docs/sdks/tokenoperations/README.md#authtokenupdateapiform) - Update Access Token
- [`userInfoEndpointAuthUserinfoApi`](docs/sdks/userinfoendpoint/README.md#authuserinfoapi) - Process UserInfo Request
- [`userInfoEndpointAuthUserinfoApiForm`](docs/sdks/userinfoendpoint/README.md#authuserinfoapiform) - Process UserInfo Request
- [`userInfoEndpointAuthUserinfoIssueApi`](docs/sdks/userinfoendpoint/README.md#authuserinfoissueapi) - Issue UserInfo Response
- [`userInfoEndpointAuthUserinfoIssueApiForm`](docs/sdks/userinfoendpoint/README.md#authuserinfoissueapiform) - Issue UserInfo Response
- [`utilityEndpointsInfoApi`](docs/sdks/utilityendpoints/README.md#infoapi) - Get Server Metadata
- [`utilityEndpointsMiscEchoApi`](docs/sdks/utilityendpoints/README.md#miscechoapi) - Echo
- [`verifiableCredentialIssuerVciBatchIssueApi`](docs/sdks/verifiablecredentialissuer/README.md#vcibatchissueapi) - /api/{serviceId}/vci/batch/issue API
- [`verifiableCredentialIssuerVciBatchParseApi`](docs/sdks/verifiablecredentialissuer/README.md#vcibatchparseapi) - /api/{serviceId}/vci/batch/parse API
- [`verifiableCredentialIssuerVciBatchParseApiForm`](docs/sdks/verifiablecredentialissuer/README.md#vcibatchparseapiform) - /api/{serviceId}/vci/batch/parse API
- [`verifiableCredentialIssuerVciDeferredIssueApi`](docs/sdks/verifiablecredentialissuer/README.md#vcideferredissueapi) - /api/{serviceId}/vci/deferred/issue API
- [`verifiableCredentialIssuerVciDeferredParseApi`](docs/sdks/verifiablecredentialissuer/README.md#vcideferredparseapi) - /api/{serviceId}/vci/deferred/parse API
- [`verifiableCredentialIssuerVciDeferredParseApiForm`](docs/sdks/verifiablecredentialissuer/README.md#vcideferredparseapiform) - /api/{serviceId}/vci/deferred/parse API
- [`verifiableCredentialIssuerVciJwksApi`](docs/sdks/verifiablecredentialissuer/README.md#vcijwksapi) - /api/{serviceId}/vci/jwks API
- [`verifiableCredentialIssuerVciJwksApiForm`](docs/sdks/verifiablecredentialissuer/README.md#vcijwksapiform) - /api/{serviceId}/vci/jwks API
- [`verifiableCredentialIssuerVciJwtissuerApi`](docs/sdks/verifiablecredentialissuer/README.md#vcijwtissuerapi) - /api/{serviceId}/vci/jwtissuer API
- [`verifiableCredentialIssuerVciJwtissuerApiForm`](docs/sdks/verifiablecredentialissuer/README.md#vcijwtissuerapiform) - /api/{serviceId}/vci/jwtissuer API
- [`verifiableCredentialIssuerVciMetadataApi`](docs/sdks/verifiablecredentialissuer/README.md#vcimetadataapi) - /api/{serviceId}/vci/metadata API
- [`verifiableCredentialIssuerVciMetadataApiForm`](docs/sdks/verifiablecredentialissuer/README.md#vcimetadataapiform) - /api/{serviceId}/vci/metadata API
- [`verifiableCredentialIssuerVciOfferCreateApi`](docs/sdks/verifiablecredentialissuer/README.md#vcioffercreateapi) - /api/{serviceId}/vci/offer/create API
- [`verifiableCredentialIssuerVciOfferCreateApiForm`](docs/sdks/verifiablecredentialissuer/README.md#vcioffercreateapiform) - /api/{serviceId}/vci/offer/create API
- [`verifiableCredentialIssuerVciOfferInfoApi`](docs/sdks/verifiablecredentialissuer/README.md#vciofferinfoapi) - /api/{serviceId}/vci/offer/info API
- [`verifiableCredentialIssuerVciOfferInfoApiForm`](docs/sdks/verifiablecredentialissuer/README.md#vciofferinfoapiform) - /api/{serviceId}/vci/offer/info API
- [`verifiableCredentialIssuerVciSingleIssueApi`](docs/sdks/verifiablecredentialissuer/README.md#vcisingleissueapi) - /api/{serviceId}/vci/single/issue API
- [`verifiableCredentialIssuerVciSingleParseApi`](docs/sdks/verifiablecredentialissuer/README.md#vcisingleparseapi) - /api/{serviceId}/vci/single/parse API
- [`verifiableCredentialIssuerVciSingleParseApiForm`](docs/sdks/verifiablecredentialissuer/README.md#vcisingleparseapiform) - /api/{serviceId}/vci/single/parse API

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
  const result = await autheleteBundled.serviceManagement.serviceGetApi({
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
  const result = await autheleteBundled.serviceManagement.serviceGetApi({
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
    const result = await autheleteBundled.serviceManagement.serviceGetApi({
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
      if (error instanceof errors.ServiceGetApiBadRequestError) {
        console.log(error.data$.resultCode); // string
        console.log(error.data$.resultMessage); // string
      }
    }
  }
}

run();

```

### Error Classes
**Primary error:**
* [`AutheleteBundledError`](./src/models/errors/autheletebundlederror.ts): The base class for HTTP error responses.

<details><summary>Less common errors (458)</summary>

<br />

**Network errors:**
* [`ConnectionError`](./src/models/errors/httpclienterrors.ts): HTTP client was unable to make a request to a server.
* [`RequestTimeoutError`](./src/models/errors/httpclienterrors.ts): HTTP request timed out due to an AbortSignal signal.
* [`RequestAbortedError`](./src/models/errors/httpclienterrors.ts): HTTP request was aborted by the client.
* [`InvalidRequestError`](./src/models/errors/httpclienterrors.ts): Any input used to create a request is invalid.
* [`UnexpectedClientError`](./src/models/errors/httpclienterrors.ts): Unrecognised or unexpected error.


**Inherit from [`AutheleteBundledError`](./src/models/errors/autheletebundlederror.ts)**:
* [`ServiceGetApiBadRequestError`](./src/models/errors/servicegetapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ServiceGetListApiBadRequestError`](./src/models/errors/servicegetlistapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ServiceCreateApiBadRequestError`](./src/models/errors/servicecreateapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ServiceUpdateApiBadRequestError`](./src/models/errors/serviceupdateapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ServiceDeleteApiBadRequestError`](./src/models/errors/servicedeleteapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ServiceConfigurationApiBadRequestError`](./src/models/errors/serviceconfigurationapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientGetApiBadRequestError`](./src/models/errors/clientgetapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientGetListApiBadRequestError`](./src/models/errors/clientgetlistapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientCreateApiBadRequestError`](./src/models/errors/clientcreateapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientUpdateApiBadRequestError`](./src/models/errors/clientupdateapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientDeleteApiBadRequestError`](./src/models/errors/clientdeleteapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientFlagUpdateApiBadRequestError`](./src/models/errors/clientflagupdateapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientSecretRefreshApiBadRequestError`](./src/models/errors/clientsecretrefreshapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientSecretUpdateApiBadRequestError`](./src/models/errors/clientsecretupdateapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientSecretUpdateApiFormBadRequestError`](./src/models/errors/clientsecretupdateapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationGetListApiBadRequestError`](./src/models/errors/clientauthorizationgetlistapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationUpdateApiBadRequestError`](./src/models/errors/clientauthorizationupdateapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationUpdateApiFormBadRequestError`](./src/models/errors/clientauthorizationupdateapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationDeleteApiBadRequestError`](./src/models/errors/clientauthorizationdeleteapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientGrantedScopesGetApiBadRequestError`](./src/models/errors/clientgrantedscopesgetapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientGrantedScopesDeleteApiBadRequestError`](./src/models/errors/clientgrantedscopesdeleteapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientExtensionRequestablesScopesGetApiBadRequestError`](./src/models/errors/clientextensionrequestablesscopesgetapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientExtensionRequestablesScopesUpdateApiBadRequestError`](./src/models/errors/clientextensionrequestablesscopesupdateapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientExtensionRequestablesScopesDeleteApiBadRequestError`](./src/models/errors/clientextensionrequestablesscopesdeleteapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationApiBadRequestError`](./src/models/errors/authauthorizationapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationApiFormBadRequestError`](./src/models/errors/authauthorizationapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationFailApiBadRequestError`](./src/models/errors/authauthorizationfailapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationFailApiFormBadRequestError`](./src/models/errors/authauthorizationfailapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationIssueApiBadRequestError`](./src/models/errors/authauthorizationissueapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationIssueApiFormBadRequestError`](./src/models/errors/authauthorizationissueapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`GetApiServiceIdAuthAuthorizationTicketInfoBadRequestError`](./src/models/errors/getapiserviceidauthauthorizationticketinfobadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`PostApiServiceIdAuthAuthorizationTicketUpdateBadRequestError`](./src/models/errors/postapiserviceidauthauthorizationticketupdatebadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`PostApiServiceIdAuthAuthorizationTicketUpdateFormBadRequestError`](./src/models/errors/postapiserviceidauthauthorizationticketupdateformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`PushedAuthReqApiBadRequestError`](./src/models/errors/pushedauthreqapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`PushedAuthReqApiFormBadRequestError`](./src/models/errors/pushedauthreqapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthTokenApiBadRequestError`](./src/models/errors/authtokenapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthTokenApiFormBadRequestError`](./src/models/errors/authtokenapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthTokenFailApiBadRequestError`](./src/models/errors/authtokenfailapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthTokenFailApiFormBadRequestError`](./src/models/errors/authtokenfailapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthTokenIssueApiBadRequestError`](./src/models/errors/authtokenissueapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthTokenIssueApiFormBadRequestError`](./src/models/errors/authtokenissueapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`IdtokenReissueApiBadRequestError`](./src/models/errors/idtokenreissueapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionApiBadRequestError`](./src/models/errors/authintrospectionapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionApiFormBadRequestError`](./src/models/errors/authintrospectionapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionStandardApiBadRequestError`](./src/models/errors/authintrospectionstandardapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionStandardApiFormBadRequestError`](./src/models/errors/authintrospectionstandardapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthRevocationApiBadRequestError`](./src/models/errors/authrevocationapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthRevocationApiFormBadRequestError`](./src/models/errors/authrevocationapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoApiBadRequestError`](./src/models/errors/authuserinfoapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoApiFormBadRequestError`](./src/models/errors/authuserinfoapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoIssueApiBadRequestError`](./src/models/errors/authuserinfoissueapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoIssueApiFormBadRequestError`](./src/models/errors/authuserinfoissueapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`GrantMApiBadRequestError`](./src/models/errors/grantmapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ServiceJwksGetApiBadRequestError`](./src/models/errors/servicejwksgetapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationApiBadRequestError`](./src/models/errors/clientregistrationapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationApiFormBadRequestError`](./src/models/errors/clientregistrationapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationGetApiBadRequestError`](./src/models/errors/clientregistrationgetapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationUpdateApiBadRequestError`](./src/models/errors/clientregistrationupdateapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationUpdateApiFormBadRequestError`](./src/models/errors/clientregistrationupdateapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationDeleteApiBadRequestError`](./src/models/errors/clientregistrationdeleteapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationDeleteApiFormBadRequestError`](./src/models/errors/clientregistrationdeleteapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationApiBadRequestError`](./src/models/errors/backchannelauthenticationapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationApiFormBadRequestError`](./src/models/errors/backchannelauthenticationapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationIssueApiBadRequestError`](./src/models/errors/backchannelauthenticationissueapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationIssueApiFormBadRequestError`](./src/models/errors/backchannelauthenticationissueapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationFailApiBadRequestError`](./src/models/errors/backchannelauthenticationfailapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationFailApiFormBadRequestError`](./src/models/errors/backchannelauthenticationfailapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationCompleteApiBadRequestError`](./src/models/errors/backchannelauthenticationcompleteapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationCompleteApiFormBadRequestError`](./src/models/errors/backchannelauthenticationcompleteapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`DeviceAuthorizationApiBadRequestError`](./src/models/errors/deviceauthorizationapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`DeviceAuthorizationApiFormBadRequestError`](./src/models/errors/deviceauthorizationapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`DeviceVerificationApiBadRequestError`](./src/models/errors/deviceverificationapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`DeviceVerificationApiFormBadRequestError`](./src/models/errors/deviceverificationapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`DeviceCompleteApiBadRequestError`](./src/models/errors/devicecompleteapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`DeviceCompleteApiFormBadRequestError`](./src/models/errors/devicecompleteapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthTokenGetListApiBadRequestError`](./src/models/errors/authtokengetlistapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthTokenCreateApiBadRequestError`](./src/models/errors/authtokencreateapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthTokenCreateApiFormBadRequestError`](./src/models/errors/authtokencreateapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthTokenUpdateApiBadRequestError`](./src/models/errors/authtokenupdateapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthTokenUpdateApiFormBadRequestError`](./src/models/errors/authtokenupdateapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthTokenDeleteApiBadRequestError`](./src/models/errors/authtokendeleteapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthTokenRevokeApiBadRequestError`](./src/models/errors/authtokenrevokeapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`AuthTokenRevokeApiFormBadRequestError`](./src/models/errors/authtokenrevokeapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`JoseVerifyApiBadRequestError`](./src/models/errors/joseverifyapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`JoseVerifyApiFormBadRequestError`](./src/models/errors/joseverifyapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`FederationConfigurationApiBadRequestError`](./src/models/errors/federationconfigurationapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`FederationRegistrationApiBadRequestError`](./src/models/errors/federationregistrationapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`FederationRegistrationApiFormBadRequestError`](./src/models/errors/federationregistrationapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`InfoApiBadRequestError`](./src/models/errors/infoapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`HskCreateApiBadRequestError`](./src/models/errors/hskcreateapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`HskCreateApiFormBadRequestError`](./src/models/errors/hskcreateapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`HskDeleteApiBadRequestError`](./src/models/errors/hskdeleteapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`HskGetApiBadRequestError`](./src/models/errors/hskgetapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`HskGetListApiBadRequestError`](./src/models/errors/hskgetlistapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciMetadataApiBadRequestError`](./src/models/errors/vcimetadataapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciMetadataApiFormBadRequestError`](./src/models/errors/vcimetadataapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciJwtissuerApiBadRequestError`](./src/models/errors/vcijwtissuerapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciJwtissuerApiFormBadRequestError`](./src/models/errors/vcijwtissuerapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciJwksApiBadRequestError`](./src/models/errors/vcijwksapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciJwksApiFormBadRequestError`](./src/models/errors/vcijwksapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciOfferCreateApiBadRequestError`](./src/models/errors/vcioffercreateapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciOfferCreateApiFormBadRequestError`](./src/models/errors/vcioffercreateapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciOfferInfoApiBadRequestError`](./src/models/errors/vciofferinfoapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciOfferInfoApiFormBadRequestError`](./src/models/errors/vciofferinfoapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciSingleParseApiBadRequestError`](./src/models/errors/vcisingleparseapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciSingleParseApiFormBadRequestError`](./src/models/errors/vcisingleparseapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciSingleIssueApiBadRequestError`](./src/models/errors/vcisingleissueapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciBatchParseApiBadRequestError`](./src/models/errors/vcibatchparseapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciBatchParseApiFormBadRequestError`](./src/models/errors/vcibatchparseapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciBatchIssueApiBadRequestError`](./src/models/errors/vcibatchissueapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciDeferredParseApiBadRequestError`](./src/models/errors/vcideferredparseapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciDeferredParseApiFormBadRequestError`](./src/models/errors/vcideferredparseapiformbadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`VciDeferredIssueApiBadRequestError`](./src/models/errors/vcideferredissueapibadrequesterror.ts): . Status code `400`. Applicable to 1 of 114 methods.*
* [`ServiceGetApiUnauthorizedError`](./src/models/errors/servicegetapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ServiceGetListApiUnauthorizedError`](./src/models/errors/servicegetlistapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ServiceCreateApiUnauthorizedError`](./src/models/errors/servicecreateapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ServiceUpdateApiUnauthorizedError`](./src/models/errors/serviceupdateapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ServiceDeleteApiUnauthorizedError`](./src/models/errors/servicedeleteapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ServiceConfigurationApiUnauthorizedError`](./src/models/errors/serviceconfigurationapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientGetApiUnauthorizedError`](./src/models/errors/clientgetapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientGetListApiUnauthorizedError`](./src/models/errors/clientgetlistapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientCreateApiUnauthorizedError`](./src/models/errors/clientcreateapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientUpdateApiUnauthorizedError`](./src/models/errors/clientupdateapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientDeleteApiUnauthorizedError`](./src/models/errors/clientdeleteapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientFlagUpdateApiUnauthorizedError`](./src/models/errors/clientflagupdateapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientSecretRefreshApiUnauthorizedError`](./src/models/errors/clientsecretrefreshapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientSecretUpdateApiUnauthorizedError`](./src/models/errors/clientsecretupdateapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientSecretUpdateApiFormUnauthorizedError`](./src/models/errors/clientsecretupdateapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationGetListApiUnauthorizedError`](./src/models/errors/clientauthorizationgetlistapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationUpdateApiUnauthorizedError`](./src/models/errors/clientauthorizationupdateapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationUpdateApiFormUnauthorizedError`](./src/models/errors/clientauthorizationupdateapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationDeleteApiUnauthorizedError`](./src/models/errors/clientauthorizationdeleteapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientGrantedScopesGetApiUnauthorizedError`](./src/models/errors/clientgrantedscopesgetapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientGrantedScopesDeleteApiUnauthorizedError`](./src/models/errors/clientgrantedscopesdeleteapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientExtensionRequestablesScopesGetApiUnauthorizedError`](./src/models/errors/clientextensionrequestablesscopesgetapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientExtensionRequestablesScopesUpdateApiUnauthorizedError`](./src/models/errors/clientextensionrequestablesscopesupdateapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientExtensionRequestablesScopesDeleteApiUnauthorizedError`](./src/models/errors/clientextensionrequestablesscopesdeleteapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationApiUnauthorizedError`](./src/models/errors/authauthorizationapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationApiFormUnauthorizedError`](./src/models/errors/authauthorizationapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationFailApiUnauthorizedError`](./src/models/errors/authauthorizationfailapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationFailApiFormUnauthorizedError`](./src/models/errors/authauthorizationfailapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationIssueApiUnauthorizedError`](./src/models/errors/authauthorizationissueapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationIssueApiFormUnauthorizedError`](./src/models/errors/authauthorizationissueapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`GetApiServiceIdAuthAuthorizationTicketInfoUnauthorizedError`](./src/models/errors/getapiserviceidauthauthorizationticketinfounauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`PostApiServiceIdAuthAuthorizationTicketUpdateUnauthorizedError`](./src/models/errors/postapiserviceidauthauthorizationticketupdateunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`PostApiServiceIdAuthAuthorizationTicketUpdateFormUnauthorizedError`](./src/models/errors/postapiserviceidauthauthorizationticketupdateformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`PushedAuthReqApiUnauthorizedError`](./src/models/errors/pushedauthreqapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`PushedAuthReqApiFormUnauthorizedError`](./src/models/errors/pushedauthreqapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthTokenApiUnauthorizedError`](./src/models/errors/authtokenapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthTokenApiFormUnauthorizedError`](./src/models/errors/authtokenapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthTokenFailApiUnauthorizedError`](./src/models/errors/authtokenfailapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthTokenFailApiFormUnauthorizedError`](./src/models/errors/authtokenfailapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthTokenIssueApiUnauthorizedError`](./src/models/errors/authtokenissueapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthTokenIssueApiFormUnauthorizedError`](./src/models/errors/authtokenissueapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`IdtokenReissueApiUnauthorizedError`](./src/models/errors/idtokenreissueapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionApiUnauthorizedError`](./src/models/errors/authintrospectionapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionApiFormUnauthorizedError`](./src/models/errors/authintrospectionapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionStandardApiUnauthorizedError`](./src/models/errors/authintrospectionstandardapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionStandardApiFormUnauthorizedError`](./src/models/errors/authintrospectionstandardapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthRevocationApiUnauthorizedError`](./src/models/errors/authrevocationapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthRevocationApiFormUnauthorizedError`](./src/models/errors/authrevocationapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoApiUnauthorizedError`](./src/models/errors/authuserinfoapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoApiFormUnauthorizedError`](./src/models/errors/authuserinfoapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoIssueApiUnauthorizedError`](./src/models/errors/authuserinfoissueapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoIssueApiFormUnauthorizedError`](./src/models/errors/authuserinfoissueapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`GrantMApiUnauthorizedError`](./src/models/errors/grantmapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ServiceJwksGetApiUnauthorizedError`](./src/models/errors/servicejwksgetapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationApiUnauthorizedError`](./src/models/errors/clientregistrationapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationApiFormUnauthorizedError`](./src/models/errors/clientregistrationapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationGetApiUnauthorizedError`](./src/models/errors/clientregistrationgetapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationUpdateApiUnauthorizedError`](./src/models/errors/clientregistrationupdateapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationUpdateApiFormUnauthorizedError`](./src/models/errors/clientregistrationupdateapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationDeleteApiUnauthorizedError`](./src/models/errors/clientregistrationdeleteapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationDeleteApiFormUnauthorizedError`](./src/models/errors/clientregistrationdeleteapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationApiUnauthorizedError`](./src/models/errors/backchannelauthenticationapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationApiFormUnauthorizedError`](./src/models/errors/backchannelauthenticationapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationIssueApiUnauthorizedError`](./src/models/errors/backchannelauthenticationissueapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationIssueApiFormUnauthorizedError`](./src/models/errors/backchannelauthenticationissueapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationFailApiUnauthorizedError`](./src/models/errors/backchannelauthenticationfailapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationFailApiFormUnauthorizedError`](./src/models/errors/backchannelauthenticationfailapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationCompleteApiUnauthorizedError`](./src/models/errors/backchannelauthenticationcompleteapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationCompleteApiFormUnauthorizedError`](./src/models/errors/backchannelauthenticationcompleteapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`DeviceAuthorizationApiUnauthorizedError`](./src/models/errors/deviceauthorizationapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`DeviceAuthorizationApiFormUnauthorizedError`](./src/models/errors/deviceauthorizationapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`DeviceVerificationApiUnauthorizedError`](./src/models/errors/deviceverificationapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`DeviceVerificationApiFormUnauthorizedError`](./src/models/errors/deviceverificationapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`DeviceCompleteApiUnauthorizedError`](./src/models/errors/devicecompleteapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`DeviceCompleteApiFormUnauthorizedError`](./src/models/errors/devicecompleteapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthTokenGetListApiUnauthorizedError`](./src/models/errors/authtokengetlistapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthTokenCreateApiUnauthorizedError`](./src/models/errors/authtokencreateapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthTokenCreateApiFormUnauthorizedError`](./src/models/errors/authtokencreateapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthTokenUpdateApiUnauthorizedError`](./src/models/errors/authtokenupdateapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthTokenUpdateApiFormUnauthorizedError`](./src/models/errors/authtokenupdateapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthTokenDeleteApiUnauthorizedError`](./src/models/errors/authtokendeleteapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthTokenRevokeApiUnauthorizedError`](./src/models/errors/authtokenrevokeapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`AuthTokenRevokeApiFormUnauthorizedError`](./src/models/errors/authtokenrevokeapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`JoseVerifyApiUnauthorizedError`](./src/models/errors/joseverifyapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`JoseVerifyApiFormUnauthorizedError`](./src/models/errors/joseverifyapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`FederationConfigurationApiUnauthorizedError`](./src/models/errors/federationconfigurationapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`FederationRegistrationApiUnauthorizedError`](./src/models/errors/federationregistrationapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`FederationRegistrationApiFormUnauthorizedError`](./src/models/errors/federationregistrationapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`InfoApiUnauthorizedError`](./src/models/errors/infoapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`HskCreateApiUnauthorizedError`](./src/models/errors/hskcreateapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`HskCreateApiFormUnauthorizedError`](./src/models/errors/hskcreateapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`HskDeleteApiUnauthorizedError`](./src/models/errors/hskdeleteapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`HskGetApiUnauthorizedError`](./src/models/errors/hskgetapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`HskGetListApiUnauthorizedError`](./src/models/errors/hskgetlistapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciMetadataApiUnauthorizedError`](./src/models/errors/vcimetadataapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciMetadataApiFormUnauthorizedError`](./src/models/errors/vcimetadataapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciJwtissuerApiUnauthorizedError`](./src/models/errors/vcijwtissuerapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciJwtissuerApiFormUnauthorizedError`](./src/models/errors/vcijwtissuerapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciJwksApiUnauthorizedError`](./src/models/errors/vcijwksapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciJwksApiFormUnauthorizedError`](./src/models/errors/vcijwksapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciOfferCreateApiUnauthorizedError`](./src/models/errors/vcioffercreateapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciOfferCreateApiFormUnauthorizedError`](./src/models/errors/vcioffercreateapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciOfferInfoApiUnauthorizedError`](./src/models/errors/vciofferinfoapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciOfferInfoApiFormUnauthorizedError`](./src/models/errors/vciofferinfoapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciSingleParseApiUnauthorizedError`](./src/models/errors/vcisingleparseapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciSingleParseApiFormUnauthorizedError`](./src/models/errors/vcisingleparseapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciSingleIssueApiUnauthorizedError`](./src/models/errors/vcisingleissueapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciBatchParseApiUnauthorizedError`](./src/models/errors/vcibatchparseapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciBatchParseApiFormUnauthorizedError`](./src/models/errors/vcibatchparseapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciBatchIssueApiUnauthorizedError`](./src/models/errors/vcibatchissueapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciDeferredParseApiUnauthorizedError`](./src/models/errors/vcideferredparseapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciDeferredParseApiFormUnauthorizedError`](./src/models/errors/vcideferredparseapiformunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`VciDeferredIssueApiUnauthorizedError`](./src/models/errors/vcideferredissueapiunauthorizederror.ts): . Status code `401`. Applicable to 1 of 114 methods.*
* [`ServiceGetApiForbiddenError`](./src/models/errors/servicegetapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ServiceGetListApiForbiddenError`](./src/models/errors/servicegetlistapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ServiceCreateApiForbiddenError`](./src/models/errors/servicecreateapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ServiceUpdateApiForbiddenError`](./src/models/errors/serviceupdateapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ServiceDeleteApiForbiddenError`](./src/models/errors/servicedeleteapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ServiceConfigurationApiForbiddenError`](./src/models/errors/serviceconfigurationapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientGetApiForbiddenError`](./src/models/errors/clientgetapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientGetListApiForbiddenError`](./src/models/errors/clientgetlistapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientCreateApiForbiddenError`](./src/models/errors/clientcreateapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientUpdateApiForbiddenError`](./src/models/errors/clientupdateapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientDeleteApiForbiddenError`](./src/models/errors/clientdeleteapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientFlagUpdateApiForbiddenError`](./src/models/errors/clientflagupdateapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientSecretRefreshApiForbiddenError`](./src/models/errors/clientsecretrefreshapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientSecretUpdateApiForbiddenError`](./src/models/errors/clientsecretupdateapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientSecretUpdateApiFormForbiddenError`](./src/models/errors/clientsecretupdateapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationGetListApiForbiddenError`](./src/models/errors/clientauthorizationgetlistapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationUpdateApiForbiddenError`](./src/models/errors/clientauthorizationupdateapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationUpdateApiFormForbiddenError`](./src/models/errors/clientauthorizationupdateapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationDeleteApiForbiddenError`](./src/models/errors/clientauthorizationdeleteapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientGrantedScopesGetApiForbiddenError`](./src/models/errors/clientgrantedscopesgetapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientGrantedScopesDeleteApiForbiddenError`](./src/models/errors/clientgrantedscopesdeleteapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientExtensionRequestablesScopesGetApiForbiddenError`](./src/models/errors/clientextensionrequestablesscopesgetapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientExtensionRequestablesScopesUpdateApiForbiddenError`](./src/models/errors/clientextensionrequestablesscopesupdateapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientExtensionRequestablesScopesDeleteApiForbiddenError`](./src/models/errors/clientextensionrequestablesscopesdeleteapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationApiForbiddenError`](./src/models/errors/authauthorizationapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationApiFormForbiddenError`](./src/models/errors/authauthorizationapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationFailApiForbiddenError`](./src/models/errors/authauthorizationfailapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationFailApiFormForbiddenError`](./src/models/errors/authauthorizationfailapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationIssueApiForbiddenError`](./src/models/errors/authauthorizationissueapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationIssueApiFormForbiddenError`](./src/models/errors/authauthorizationissueapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`GetApiServiceIdAuthAuthorizationTicketInfoForbiddenError`](./src/models/errors/getapiserviceidauthauthorizationticketinfoforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`PostApiServiceIdAuthAuthorizationTicketUpdateForbiddenError`](./src/models/errors/postapiserviceidauthauthorizationticketupdateforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`PostApiServiceIdAuthAuthorizationTicketUpdateFormForbiddenError`](./src/models/errors/postapiserviceidauthauthorizationticketupdateformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`PushedAuthReqApiForbiddenError`](./src/models/errors/pushedauthreqapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`PushedAuthReqApiFormForbiddenError`](./src/models/errors/pushedauthreqapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthTokenApiForbiddenError`](./src/models/errors/authtokenapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthTokenApiFormForbiddenError`](./src/models/errors/authtokenapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthTokenFailApiForbiddenError`](./src/models/errors/authtokenfailapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthTokenFailApiFormForbiddenError`](./src/models/errors/authtokenfailapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthTokenIssueApiForbiddenError`](./src/models/errors/authtokenissueapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthTokenIssueApiFormForbiddenError`](./src/models/errors/authtokenissueapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`IdtokenReissueApiForbiddenError`](./src/models/errors/idtokenreissueapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionApiForbiddenError`](./src/models/errors/authintrospectionapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionApiFormForbiddenError`](./src/models/errors/authintrospectionapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionStandardApiForbiddenError`](./src/models/errors/authintrospectionstandardapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionStandardApiFormForbiddenError`](./src/models/errors/authintrospectionstandardapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthRevocationApiForbiddenError`](./src/models/errors/authrevocationapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthRevocationApiFormForbiddenError`](./src/models/errors/authrevocationapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoApiForbiddenError`](./src/models/errors/authuserinfoapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoApiFormForbiddenError`](./src/models/errors/authuserinfoapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoIssueApiForbiddenError`](./src/models/errors/authuserinfoissueapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoIssueApiFormForbiddenError`](./src/models/errors/authuserinfoissueapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`GrantMApiForbiddenError`](./src/models/errors/grantmapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ServiceJwksGetApiForbiddenError`](./src/models/errors/servicejwksgetapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationApiForbiddenError`](./src/models/errors/clientregistrationapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationApiFormForbiddenError`](./src/models/errors/clientregistrationapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationGetApiForbiddenError`](./src/models/errors/clientregistrationgetapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationUpdateApiForbiddenError`](./src/models/errors/clientregistrationupdateapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationUpdateApiFormForbiddenError`](./src/models/errors/clientregistrationupdateapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationDeleteApiForbiddenError`](./src/models/errors/clientregistrationdeleteapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationDeleteApiFormForbiddenError`](./src/models/errors/clientregistrationdeleteapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationApiForbiddenError`](./src/models/errors/backchannelauthenticationapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationApiFormForbiddenError`](./src/models/errors/backchannelauthenticationapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationIssueApiForbiddenError`](./src/models/errors/backchannelauthenticationissueapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationIssueApiFormForbiddenError`](./src/models/errors/backchannelauthenticationissueapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationFailApiForbiddenError`](./src/models/errors/backchannelauthenticationfailapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationFailApiFormForbiddenError`](./src/models/errors/backchannelauthenticationfailapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationCompleteApiForbiddenError`](./src/models/errors/backchannelauthenticationcompleteapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationCompleteApiFormForbiddenError`](./src/models/errors/backchannelauthenticationcompleteapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`DeviceAuthorizationApiForbiddenError`](./src/models/errors/deviceauthorizationapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`DeviceAuthorizationApiFormForbiddenError`](./src/models/errors/deviceauthorizationapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`DeviceVerificationApiForbiddenError`](./src/models/errors/deviceverificationapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`DeviceVerificationApiFormForbiddenError`](./src/models/errors/deviceverificationapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`DeviceCompleteApiForbiddenError`](./src/models/errors/devicecompleteapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`DeviceCompleteApiFormForbiddenError`](./src/models/errors/devicecompleteapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthTokenGetListApiForbiddenError`](./src/models/errors/authtokengetlistapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthTokenCreateApiForbiddenError`](./src/models/errors/authtokencreateapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthTokenCreateApiFormForbiddenError`](./src/models/errors/authtokencreateapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthTokenUpdateApiForbiddenError`](./src/models/errors/authtokenupdateapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthTokenUpdateApiFormForbiddenError`](./src/models/errors/authtokenupdateapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthTokenDeleteApiForbiddenError`](./src/models/errors/authtokendeleteapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthTokenRevokeApiForbiddenError`](./src/models/errors/authtokenrevokeapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`AuthTokenRevokeApiFormForbiddenError`](./src/models/errors/authtokenrevokeapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`JoseVerifyApiForbiddenError`](./src/models/errors/joseverifyapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`JoseVerifyApiFormForbiddenError`](./src/models/errors/joseverifyapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`FederationConfigurationApiForbiddenError`](./src/models/errors/federationconfigurationapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`FederationRegistrationApiForbiddenError`](./src/models/errors/federationregistrationapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`FederationRegistrationApiFormForbiddenError`](./src/models/errors/federationregistrationapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`InfoApiForbiddenError`](./src/models/errors/infoapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`HskCreateApiForbiddenError`](./src/models/errors/hskcreateapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`HskCreateApiFormForbiddenError`](./src/models/errors/hskcreateapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`HskDeleteApiForbiddenError`](./src/models/errors/hskdeleteapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`HskGetApiForbiddenError`](./src/models/errors/hskgetapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`HskGetListApiForbiddenError`](./src/models/errors/hskgetlistapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciMetadataApiForbiddenError`](./src/models/errors/vcimetadataapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciMetadataApiFormForbiddenError`](./src/models/errors/vcimetadataapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciJwtissuerApiForbiddenError`](./src/models/errors/vcijwtissuerapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciJwtissuerApiFormForbiddenError`](./src/models/errors/vcijwtissuerapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciJwksApiForbiddenError`](./src/models/errors/vcijwksapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciJwksApiFormForbiddenError`](./src/models/errors/vcijwksapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciOfferCreateApiForbiddenError`](./src/models/errors/vcioffercreateapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciOfferCreateApiFormForbiddenError`](./src/models/errors/vcioffercreateapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciOfferInfoApiForbiddenError`](./src/models/errors/vciofferinfoapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciOfferInfoApiFormForbiddenError`](./src/models/errors/vciofferinfoapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciSingleParseApiForbiddenError`](./src/models/errors/vcisingleparseapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciSingleParseApiFormForbiddenError`](./src/models/errors/vcisingleparseapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciSingleIssueApiForbiddenError`](./src/models/errors/vcisingleissueapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciBatchParseApiForbiddenError`](./src/models/errors/vcibatchparseapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciBatchParseApiFormForbiddenError`](./src/models/errors/vcibatchparseapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciBatchIssueApiForbiddenError`](./src/models/errors/vcibatchissueapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciDeferredParseApiForbiddenError`](./src/models/errors/vcideferredparseapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciDeferredParseApiFormForbiddenError`](./src/models/errors/vcideferredparseapiformforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`VciDeferredIssueApiForbiddenError`](./src/models/errors/vcideferredissueapiforbiddenerror.ts): . Status code `403`. Applicable to 1 of 114 methods.*
* [`ServiceGetApiInternalServerError`](./src/models/errors/servicegetapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ServiceGetListApiInternalServerError`](./src/models/errors/servicegetlistapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ServiceCreateApiInternalServerError`](./src/models/errors/servicecreateapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ServiceUpdateApiInternalServerError`](./src/models/errors/serviceupdateapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ServiceDeleteApiInternalServerError`](./src/models/errors/servicedeleteapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ServiceConfigurationApiInternalServerError`](./src/models/errors/serviceconfigurationapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientGetApiInternalServerError`](./src/models/errors/clientgetapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientGetListApiInternalServerError`](./src/models/errors/clientgetlistapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientCreateApiInternalServerError`](./src/models/errors/clientcreateapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientUpdateApiInternalServerError`](./src/models/errors/clientupdateapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientDeleteApiInternalServerError`](./src/models/errors/clientdeleteapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientFlagUpdateApiInternalServerError`](./src/models/errors/clientflagupdateapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientSecretRefreshApiInternalServerError`](./src/models/errors/clientsecretrefreshapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientSecretUpdateApiInternalServerError`](./src/models/errors/clientsecretupdateapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientSecretUpdateApiFormInternalServerError`](./src/models/errors/clientsecretupdateapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationGetListApiInternalServerError`](./src/models/errors/clientauthorizationgetlistapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationUpdateApiInternalServerError`](./src/models/errors/clientauthorizationupdateapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationUpdateApiFormInternalServerError`](./src/models/errors/clientauthorizationupdateapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientAuthorizationDeleteApiInternalServerError`](./src/models/errors/clientauthorizationdeleteapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientGrantedScopesGetApiInternalServerError`](./src/models/errors/clientgrantedscopesgetapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientGrantedScopesDeleteApiInternalServerError`](./src/models/errors/clientgrantedscopesdeleteapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientExtensionRequestablesScopesGetApiInternalServerError`](./src/models/errors/clientextensionrequestablesscopesgetapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientExtensionRequestablesScopesUpdateApiInternalServerError`](./src/models/errors/clientextensionrequestablesscopesupdateapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientExtensionRequestablesScopesDeleteApiInternalServerError`](./src/models/errors/clientextensionrequestablesscopesdeleteapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationApiInternalServerError`](./src/models/errors/authauthorizationapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationApiFormInternalServerError`](./src/models/errors/authauthorizationapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationFailApiInternalServerError`](./src/models/errors/authauthorizationfailapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationFailApiFormInternalServerError`](./src/models/errors/authauthorizationfailapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationIssueApiInternalServerError`](./src/models/errors/authauthorizationissueapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthAuthorizationIssueApiFormInternalServerError`](./src/models/errors/authauthorizationissueapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`GetApiServiceIdAuthAuthorizationTicketInfoInternalServerError`](./src/models/errors/getapiserviceidauthauthorizationticketinfointernalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`PostApiServiceIdAuthAuthorizationTicketUpdateInternalServerError`](./src/models/errors/postapiserviceidauthauthorizationticketupdateinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`PostApiServiceIdAuthAuthorizationTicketUpdateFormInternalServerError`](./src/models/errors/postapiserviceidauthauthorizationticketupdateforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`PushedAuthReqApiInternalServerError`](./src/models/errors/pushedauthreqapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`PushedAuthReqApiFormInternalServerError`](./src/models/errors/pushedauthreqapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthTokenApiInternalServerError`](./src/models/errors/authtokenapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthTokenApiFormInternalServerError`](./src/models/errors/authtokenapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthTokenFailApiInternalServerError`](./src/models/errors/authtokenfailapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthTokenFailApiFormInternalServerError`](./src/models/errors/authtokenfailapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthTokenIssueApiInternalServerError`](./src/models/errors/authtokenissueapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthTokenIssueApiFormInternalServerError`](./src/models/errors/authtokenissueapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`IdtokenReissueApiInternalServerError`](./src/models/errors/idtokenreissueapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionApiInternalServerError`](./src/models/errors/authintrospectionapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionApiFormInternalServerError`](./src/models/errors/authintrospectionapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionStandardApiInternalServerError`](./src/models/errors/authintrospectionstandardapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthIntrospectionStandardApiFormInternalServerError`](./src/models/errors/authintrospectionstandardapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthRevocationApiInternalServerError`](./src/models/errors/authrevocationapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthRevocationApiFormInternalServerError`](./src/models/errors/authrevocationapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoApiInternalServerError`](./src/models/errors/authuserinfoapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoApiFormInternalServerError`](./src/models/errors/authuserinfoapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoIssueApiInternalServerError`](./src/models/errors/authuserinfoissueapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthUserinfoIssueApiFormInternalServerError`](./src/models/errors/authuserinfoissueapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`GrantMApiInternalServerError`](./src/models/errors/grantmapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ServiceJwksGetApiInternalServerError`](./src/models/errors/servicejwksgetapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationApiInternalServerError`](./src/models/errors/clientregistrationapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationApiFormInternalServerError`](./src/models/errors/clientregistrationapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationGetApiInternalServerError`](./src/models/errors/clientregistrationgetapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationUpdateApiInternalServerError`](./src/models/errors/clientregistrationupdateapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationUpdateApiFormInternalServerError`](./src/models/errors/clientregistrationupdateapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationDeleteApiInternalServerError`](./src/models/errors/clientregistrationdeleteapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`ClientRegistrationDeleteApiFormInternalServerError`](./src/models/errors/clientregistrationdeleteapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationApiInternalServerError`](./src/models/errors/backchannelauthenticationapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationApiFormInternalServerError`](./src/models/errors/backchannelauthenticationapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationIssueApiInternalServerError`](./src/models/errors/backchannelauthenticationissueapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationIssueApiFormInternalServerError`](./src/models/errors/backchannelauthenticationissueapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationFailApiInternalServerError`](./src/models/errors/backchannelauthenticationfailapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationFailApiFormInternalServerError`](./src/models/errors/backchannelauthenticationfailapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationCompleteApiInternalServerError`](./src/models/errors/backchannelauthenticationcompleteapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`BackchannelAuthenticationCompleteApiFormInternalServerError`](./src/models/errors/backchannelauthenticationcompleteapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`DeviceAuthorizationApiInternalServerError`](./src/models/errors/deviceauthorizationapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`DeviceAuthorizationApiFormInternalServerError`](./src/models/errors/deviceauthorizationapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`DeviceVerificationApiInternalServerError`](./src/models/errors/deviceverificationapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`DeviceVerificationApiFormInternalServerError`](./src/models/errors/deviceverificationapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`DeviceCompleteApiInternalServerError`](./src/models/errors/devicecompleteapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`DeviceCompleteApiFormInternalServerError`](./src/models/errors/devicecompleteapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthTokenGetListApiInternalServerError`](./src/models/errors/authtokengetlistapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthTokenCreateApiInternalServerError`](./src/models/errors/authtokencreateapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthTokenCreateApiFormInternalServerError`](./src/models/errors/authtokencreateapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthTokenUpdateApiInternalServerError`](./src/models/errors/authtokenupdateapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthTokenUpdateApiFormInternalServerError`](./src/models/errors/authtokenupdateapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthTokenDeleteApiInternalServerError`](./src/models/errors/authtokendeleteapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthTokenRevokeApiInternalServerError`](./src/models/errors/authtokenrevokeapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`AuthTokenRevokeApiFormInternalServerError`](./src/models/errors/authtokenrevokeapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`JoseVerifyApiInternalServerError`](./src/models/errors/joseverifyapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`JoseVerifyApiFormInternalServerError`](./src/models/errors/joseverifyapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`FederationConfigurationApiInternalServerError`](./src/models/errors/federationconfigurationapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`FederationRegistrationApiInternalServerError`](./src/models/errors/federationregistrationapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`FederationRegistrationApiFormInternalServerError`](./src/models/errors/federationregistrationapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`InfoApiInternalServerError`](./src/models/errors/infoapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`HskCreateApiInternalServerError`](./src/models/errors/hskcreateapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`HskCreateApiFormInternalServerError`](./src/models/errors/hskcreateapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`HskDeleteApiInternalServerError`](./src/models/errors/hskdeleteapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`HskGetApiInternalServerError`](./src/models/errors/hskgetapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`HskGetListApiInternalServerError`](./src/models/errors/hskgetlistapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciMetadataApiInternalServerError`](./src/models/errors/vcimetadataapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciMetadataApiFormInternalServerError`](./src/models/errors/vcimetadataapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciJwtissuerApiInternalServerError`](./src/models/errors/vcijwtissuerapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciJwtissuerApiFormInternalServerError`](./src/models/errors/vcijwtissuerapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciJwksApiInternalServerError`](./src/models/errors/vcijwksapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciJwksApiFormInternalServerError`](./src/models/errors/vcijwksapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciOfferCreateApiInternalServerError`](./src/models/errors/vcioffercreateapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciOfferCreateApiFormInternalServerError`](./src/models/errors/vcioffercreateapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciOfferInfoApiInternalServerError`](./src/models/errors/vciofferinfoapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciOfferInfoApiFormInternalServerError`](./src/models/errors/vciofferinfoapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciSingleParseApiInternalServerError`](./src/models/errors/vcisingleparseapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciSingleParseApiFormInternalServerError`](./src/models/errors/vcisingleparseapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciSingleIssueApiInternalServerError`](./src/models/errors/vcisingleissueapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciBatchParseApiInternalServerError`](./src/models/errors/vcibatchparseapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciBatchParseApiFormInternalServerError`](./src/models/errors/vcibatchparseapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciBatchIssueApiInternalServerError`](./src/models/errors/vcibatchissueapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciDeferredParseApiInternalServerError`](./src/models/errors/vcideferredparseapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciDeferredParseApiFormInternalServerError`](./src/models/errors/vcideferredparseapiforminternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
* [`VciDeferredIssueApiInternalServerError`](./src/models/errors/vcideferredissueapiinternalservererror.ts): . Status code `500`. Applicable to 1 of 114 methods.*
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
  const result = await autheleteBundled.serviceManagement.serviceGetApi({
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
  const result = await autheleteBundled.serviceManagement.serviceGetApi({
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
  const result = await autheleteBundled.serviceManagement.serviceGetApi({
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
