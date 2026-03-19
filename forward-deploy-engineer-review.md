# Forward Deployment Engineer Review notes

SAML, SSO, RestApi, architecture Design, basic network considerations

best practices for version control,ci/cd pipeline, deployment patterns

identify issues such as data drift, model degradation, unexpected output,

SQL data manipulation, reporting and performance tuning

what is an rest api and how does it fit in a broader integration strategy.

# What is SAML, SSO and how does it compare to Oauth, openId connect?

SAML(Security Assertion Markup Language) is an open standard used in cloud services for authentication and authorization. ALlows users to log in once and access mulptiple applications without reentering credentials, which is called single sign on (SSO)

SAML lets a trusted identity provider confirm who you are, so other applications dont need to authenticate you themselves.

Key components

identity provider
example okta,Azure active directory

service provider is the application you want to access
example salefore or aws

SAML assertion
an xml document that contains authentication data (user identity, permissions)

How does it work?

1. Client tries to access a cloud app
2. the app redirects you tho the idp
3. you login or are already logged in
4. the idp sends back a saml assertion
5. the app virifies it and grants access

Oauth is used for authorization like access to API's but does not verify an identity
OpenID Connect(OIDC) is a modern authetnication layer built on oauth which uses json and jwt tokens to autheticate and authorize.

# What is a SAML Assertion?

A SAML Assertion is an XML document issued by the IdP that contains:

Authentication statement (user is authenticated)

Attributes (user info like email, role)

Authorization decision (optional)

# How is SAML secure?

Assertions are digitally signed

Can be encrypted

Uses HTTPS

Includes timestamps to prevent replay attacks

# What is a RelayState?

RelayState is a parameter that preserves the user’s original destination URL so they can be redirected back after authentication.

# What is metadata in SAML?

Metadata is an XML file exchanged between IdP and SP that contains:

Endpoints (login URLs)

Certificates (for signing)

Entity IDs

# What are common SAML issues?

Clock skew (time mismatch)

Invalid signatures

Incorrect audience/issuer

Misconfigured endpoints

# What is JWT?

Json Web tokens are compact token format used to transmit data
often used in apis and modern authentication

its made up of a header, payload, and signature

oauth2.0 is an authorization framework, lets apps acess resources on behalf of users like login in with google

# what is OIDC?

Open ID connect is a authentication layer built ontop of oauth. Adds authentication using jwt tokens.

Modern flow is User -> App -> IDP -> JWT_Acces token -> API/backend
No xml, no browser resirects for apis. lightweight and fast

SAML is xml very verbose and heavy
jwt json lightweight and fast

saml is for enterpise sso( internal tools and legacy systems)

jwt.oidc modern apps, mobile apps, apis and microservices

saml is slower because of xml parsing and redirects
jwt faster stateless, no db lookup

jwt is better for disctributed systems and apis
