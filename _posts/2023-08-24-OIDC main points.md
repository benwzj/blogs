---
layout: post
title: " OIDC Main Points "
date: 2023-08-24
---

# What is OIDC

- OpenID Connect (OIDC) provides an authentication layer atop OAuth 2.0.
- It adds an additional token called an **ID token**.
- OpenID Connect also standardizes areas that OAuth 2.0 leaves up to choice, such as scopes, endpoint discovery, and dynamic registration of clients.
- It addresses the lack of an authentication mechanism in OAuth, which is a weakness when it comes to authorizing sensitive transactions such as payments.
- OIDC is just a special, simplified case of OAuth, not a replacement. It uses the same terminology and concepts.

# Flow

- A typical OpenID Connect workflow involves three parties, namely, the relying party (RP), the end user and the identity provider. The client, or the Relying Party, sends the end user to the identity provider, where the end user authenticates the identity and authorizes access to the client.
- The identity provider sends an authorization code to the client, which then uses it to request access and ID tokens from the identity provider. Once the client gets the tokens, it is allowed it to perform an action on behalf of the end user.
- OpenID Connect uses a signed and cryptographically verifiable JSON Web Token to ensure that the access and **ID tokens** are not tampered with during the exchange of information between parties.
