Plan — what I'll cover

- Steps to create Auth0 + MongoDB Atlas (Data API) accounts.
- Exactly where to place credentials in the repo.
- Answer whether the spec mentions an Atlas dev version and recommendations.

Quick steps — create accounts and configure

- Auth0
    1. Create a tenant at Auth0 and register a new Application (type: Single Page Application).
    2. Create an API in Auth0 (API → Create API). Note its Identifier (use as `AUTH0_AUDIENCE`).
    3. In the SPA app settings, set Allowed Callback URLs and Allowed Logout URLs to:
        - `http://localhost:5173` (dev) and your production domain.
    4. Copy values:
        - Domain → `AUTH0_ISSUER_BASE_URL` (format: [https://your-tenant.auth0.com/](vscode-file://vscode-app/c:/Users/Life%20Work/AppData/Local/Programs/Microsoft%20VS%20Code/ce099c1ed2/resources/app/out/vs/code/electron-browser/workbench/workbench.html))
        - Client ID → frontend `VITE_AUTH0_CLIENT_ID`
        - API Identifier → `AUTH0_AUDIENCE`
- MongoDB Atlas (Data API)
    1. Create a MongoDB Atlas project (use a separate project/cluster for dev).
    2. Create a cluster (a free-tier M0 is ok for development; use a dedicated dev cluster to avoid polluting prod).
    3. In Atlas, open App Services (Realm/Atlas App Services) and create an App for your project.
    4. Enable the Data API for that App (App Services → Data API). Create an API Key with least privileges needed.
    5. Copy values:
        - Data API URL → `ATLAS_DATA_API_URL` (the endpoint like [https://data.mongodb-api.com/app/…/endpoint/data/v1](vscode-file://vscode-app/c:/Users/Life%20Work/AppData/Local/Programs/Microsoft%20VS%20Code/ce099c1ed2/resources/app/out/vs/code/electron-browser/workbench/workbench.html))
        - API Key → `ATLAS_DATA_API_KEY`

Where to put the credentials (local dev)

- Backend: copy and edit
    - Copy [local.settings.example.json](vscode-file://vscode-app/c:/Users/Life%20Work/AppData/Local/Programs/Microsoft%20VS%20Code/ce099c1ed2/resources/app/out/vs/code/electron-browser/workbench/workbench.html) to `api/local.settings.json` and fill:
        - `ATLAS_DATA_API_URL`
        - `ATLAS_DATA_API_KEY`
        - `AUTH0_AUDIENCE`
        - `AUTH0_ISSUER_BASE_URL`
- Frontend: copy and edit
    - Copy [.env.example](vscode-file://vscode-app/c:/Users/Life%20Work/AppData/Local/Programs/Microsoft%20VS%20Code/ce099c1ed2/resources/app/out/vs/code/electron-browser/workbench/workbench.html) to `frontend/.env` and fill:
        - `VITE_AUTH0_DOMAIN` (your Auth0 domain, without trailing slash)
        - `VITE_AUTH0_CLIENT_ID`
        - `VITE_AUTH0_AUDIENCE` (same audience/identifier as backend)

Security notes

- `api/local.settings.json` and `frontend/.env` must remain local and not be committed — the repo’s [.gitignore](vscode-file://vscode-app/c:/Users/Life%20Work/AppData/Local/Programs/Microsoft%20VS%20Code/ce099c1ed2/resources/app/out/vs/code/electron-browser/workbench/workbench.html) already excludes `api/local.settings.json` and `.env`.
- For CI/CD, store secrets in GitHub Actions/Azure pipeline secret stores and inject into deployment environment (do not commit secrets).

About Atlas “dev” version / what the spec says

- Yes — the spec explicitly recommends using a dedicated “Cloud Development Atlas Cluster” for local development (to avoid using production data). The spec also states the app uses the MongoDB Atlas Data API (stateless HTTPS REST).
- Practical implication: the Atlas Data API is a cloud service (configured via Atlas App Services). There is no local emulator for the Atlas Data API, so you must use an Atlas cloud project (a free M0 cluster + an App Services app with Data API enabled) for local development and testing.
- Recommendation: create a separate Atlas project/cluster named e.g. `kipnuni-dev` (or use an M0 sandbox) and enable Data API there; restrict the API key permissions and rotate keys if possible.

E2E / test auth tip

- For Playwright E2E, avoid real UI logins repeatedly. Create a stable test account (or a backend-generated test token) and save `playwright/.auth/user.json` via a setup script so tests reuse `storageState` as described in the spec.

Want me to do any of these for you?

- I can draft step-by-step instructions to create the Auth0 app and show exact fields to set.
- I can produce a short `README.md` (or sample `api/local.settings.json` and `frontend/.env` templates with placeholders) for you to edit. Which would you like next?