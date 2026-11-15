# RailwayAdmin — Railway Hosting Control Panel

Mobile-first Railway dashboard powered by Railway's official GraphQL Public API.

## Included
- Multi-token connection support through the existing dashboard.
- Project and service overview.
- GitHub repository browsing and deployment workflows already present in the main dashboard.
- Advanced Control Center at `/control`:
  - Project, service and environment selection.
  - Deployment history, deploy, redeploy, restart, rollback, stop, cancel and remove.
  - Create, rename, connect/disconnect GitHub and delete services.
  - Per-environment build/start command updates.
  - Custom domain availability check and domain creation.
  - Volume creation, backup creation and deletion (deletion is destructive).
- Responsive blue-and-white mobile interface.

## Setup
1. Deploy this Next.js project.
2. Open the dashboard and add a Railway API token.
3. Save the token, then open **Advanced Control**.
4. Select a project, service and environment before performing service/deployment actions.

## Important
- The API token is currently retained in this browser's local storage by the legacy dashboard. Use a private device and clear it with the dashboard's Disconnect/Delete token action when finished. For a multi-user production deployment, replace browser token storage with encrypted server-side sessions and per-user authentication.
- Railway API permissions and schema availability depend on token scope and Railway's current API schema.
- Volume deletion permanently deletes stored data. Confirm before using it.
- CPU/RAM/usage metrics, complete log streaming, custom domain deletion, and full environment management are not represented as fake controls; add them only after wiring to the exact live API fields supported by the connected account.

API endpoint: `https://backboard.railway.com/graphql/v2`.
