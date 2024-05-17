---
layout: post
title: "OAuth2 Proxy with Okta"
description: "Using OAuth2 Proxy with Okta"
date: "2022-01-15"
---

**Hello world**, this is my first Jekyll blog post.

Do you have an application that doesnt support authentication?

Do you have Okta?  Lets use Okta.

## Introducing OAuth2 Proxy

"""
A reverse proxy and static file server that provides authentication using Providers (Google, Keycloak, GitHub and others) to validate accounts by email, domain or group.
"""

Documentation: https://oauth2-proxy.github.io/oauth2-proxy/
Code: https://github.com/oauth2-proxy/oauth2-proxy

## Configuration

There are multiple ways to deploy OAuth2 Proxy, but here are the important bits to get it working with Okta.

### Environment Variables
We are deploying in Kubernetes, using ConfigMaps and Secrets.

Store in Configmap:

    OAUTH2_PROXY_PROVIDER: "oidc"
    OAUTH2_PROXY_HTTP_ADDRESS: "0.0.0.0:4180"
    OAUTH2_PROXY_PROVIDER_DISPLAY_NAME: "My Company Okta"
    OAUTH2_PROXY_REDIRECT_URL: "https://myapp.com/oauth2/callback"
    OAUTH2_PROXY_OIDC_ISSUER_URL: "https://yoursubdomain.okta.com"
    OAUTH2_PROXY_UPSTREAMS: "http://127.0.0.1:8080/"
    OAUTH2_PROXY_EMAIL_DOMAINS: "yourdomain.com"
    OAUTH2_PROXY_PASS_ACCESS_TOKEN: "true"
    OAUTH2_PROXY_SKIP_PROVIDER_BUTTON: "true"

Store in Secret:

    OAUTH2_PROXY_CLIENT_ID: "{OKTA_OIDC_APP_CLIENT_ID}",
    OAUTH2_PROXY_CLIENT_SECRET: "{OKTA_OIDC_APP_CLIENT_SECRET}",
    OAUTH2_PROXY_COOKIE_NAME: "SESSION",
    OAUTH2_PROXY_COOKIE_SECRET: "{GENERATED_SECRET}"

### Generating a Cookie Secret

https://oauth2-proxy.github.io/oauth2-proxy/configuration/overview

    python -c 'import os,base64; print(base64.urlsafe_b64encode(os.urandom(32)).decode())'