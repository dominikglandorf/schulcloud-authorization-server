This repository contains a Docker Compose definition to set up the authorization server required for OAuth2. It relies on [Ory Hydra](https://github.com/ory/hydra)

# Requirements
* Docker

# Set up
1. Copy .env.example to .env
2. In .env:
⋅⋅* set `SYSTEM_SECRET` and `OIDC_SUBJECT_TYPE_PAIRWISE_SALT` to random and secure strings
⋅⋅* If you use a test environment without HTTPS, set `SERVE_PARAMS=--dangerous-force-http`
⋅⋅* If you use HTTP for last mile, set `HTTPS_ALLOW_TERMINATION_FROM` to the SSL server's subnet
⋅⋅* Set `OAUTH2_CONSENT_URL` and `OAUTH2_LOGIN_URL` to the client's corresponding URLs
⋅⋅* Set Postgres credentials and update them inside `DATABASE_URL`
3. Run docker-compose up