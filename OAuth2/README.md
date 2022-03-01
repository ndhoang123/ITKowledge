# OAuth
- Content:
    1. [Access Token](#access-token)
    2. [Bearer Token](#bearer-token)
    3. [The difference between bearer token and JWT](#the-difference-between-bearer-token-and-jwt-token)
    4. [OAuth2](#oauth2)
    5. [Reference](#reference)

## Access Token

- **Access tokens** are used in token-based authentication to allow an application to access an API. 
- The application **receives** the **access token** after a user successfully authenticate and authorizes access, then passes the access token as a crendential when it calls the target API.

- The passed token informs the API that the bearer of the token have been authorized to access the API and perform specific actions by the scope that was granted during the authorization.

- Types of access token:

### Opaque access token:

- **Opaque access token** are tokens in a proprietary format that you cannot access and typically contain some identifier to information in a servers's persistent storage.

- **To validate** opaque access token, the recipent of the tokens needs to call the server that issued the token.

- Opaque access token has a format that is not intended to read by the users. Only the issuer knows the format.

### JWT access token:

- **Json web token (JWT) access tokens** conform to the **JWT standard** and contain information about an entity in the form of claims. They are self-contained therefore it is not neccessary for the receiver to call a server to validate the token.

- Access token issued for the Management API and access token issued for any custom API that you have registered with Auth0 follow the JWT standard, which means that their basic structure conforms to the typical **JWT structure** and they contain standard **JWT claims** asserted about the token itself.

### Access token lifetime:
- By default, the **access token for a custom API** is valid for **86400 seconds** (24 hours).

- Access tokens issued strictly for the purpose of accessing the OIDC `/userinfo` endpoint have a default lifetime and can't be changed. The length of lifetime depends on the flow used to obtain the token.

## Bearer Token
- In OAuth 1, there are two components to the access token, a public and private string. The private string is used when signing the request, and never sent accross the wire.

- The common way of accessing OAuth 2.0 APIs is using a "Bearer Token". This is a single string acts as the authentication of the API request, sent in an HTTP "Authorization" header. The string is meaningless to clients using it, and may be of varying lengths.

- **Bearer Token** are much a simpler way of making API requests, since they don't require cryptoraphic signing of each request. The **tradeoff** is that all API requests must be made over an HTTPS connection, since the request contains a plaintext token that could be used by anyone if it were intercepted.

- The **advantage** of the **bearer token** is that it does not require complex libraries to make requests and is much simpler for both client and servers to implement.

- But, in the **downside**, the **bearer token** is that there is nothing preventing other apps from using a Bearer token if it can get access to it.

## The difference between Bearer Token and JWT Token:
- JWT is simply an encoding standard for tokens that contains a JSON payload that can be signed and encrypted.
- JWT can be used for many things, among those are bearer tokens.

## OAuth2
### OAuth2 terms
- **Resource owner**: The user.
- **Client**: The application wants to retrieve the information from the server.
- **Authorization server**: It verifies the identity of the user, and issues access tokens to the application.
- **Resource server**: It contains the resources to be accessed, where client attempts to retrieve. In some cases, the authorization server and resource server stay at the same server, or seperate in the different place.
- **Grants**: Methods to get access token from the authorization server are called **grants**. The same method used to request a token is also used by the resource server to validate a token.
- **Scope**: It is used to restrict the client accessing in allowed area that the client was registed in the past.
- **Token endpoint**: It is used by clients to get an access token from the authorization server.
### Tokens
- The two token types involved in OAuth 2 authentication are **Access Token** and **Refresh Token**.
1. **Access token**:
- The access token is used to for authentication and authorization to get access to the resources from the resource server.
2. **Refresh Token**:
- The refresh token normally is sent together with the access token.

- The refresh token is used to get a new access token, when the old one expires. Instead of the normal grant type, the client provides the refresh token, and receives a new access token.

### Grants types


## Reference: 
1. [Acess Token](https://auth0.com/docs/secure/tokens/access-tokens)
2. [Bearer Token](https://www.oauth.com/oauth2-servers/differences-between-oauth-1-2/bearer-tokens/)
3. [Difference between bearer token and JWT](https://stackoverflow.com/questions/40375508/whats-the-difference-between-jwts-and-bearer-token)
4. [OAuth2 overview](https://www.soapui.org/docs/oauth2/oauth2-overview/)
5. [OAuth2 in vietnamese version, well explaination and easy understanding](https://letjar.com/spring-boot-oauth2-openid/)