# RailwayAdmin

A mobile-first blue-and-white Railway hosting control panel built with Next.js and Railway's official GraphQL Public API.

## Dashboard capabilities

- Multi-token account support in the existing dashboard.
- Project and service overview, create project, create service, rename and remove service.
- GitHub repository browser, GitHub deployment workflows, ZIP deployment and code editor (existing dashboard features).
- Deploy, deployment history, redeploy, restart, rollback, stop, cancel and remove deployment.
- Runtime logs, build logs and environment-wide logs.
- Environment variables: list, create/update and delete.
- Railway-provided domains and custom domains: list, generate, add, inspect DNS/certificate status and delete.
- Environments: list, create, rename and delete.
- Volumes: create, delete, list backups, create backups and restore backups.
- GraphQL schema explorer and authenticated API query runner.
- Mobile responsive navigation and blue-white styling.

## Setup

1. Deploy the Next.js application.
2. Open the main dashboard and add a Railway API token.
3. Open **Advanced Control** and select the project, service and environment.
4. Use each section to load live data before taking actions.

## Security notes

- The legacy dashboard stores Railway tokens in this browser's localStorage. This is convenient for a personal, single-user panel but is not a secure multi-user credential vault. Do not use this on a shared device. A production multi-user version should use authenticated server-side sessions and encrypted secret storage.
- The API proxy is same-origin only and does not return token previews or full Railway response bodies in debug logs.
- Never share screenshots containing environment-variable values, tokens, or private deployment logs.
- Destructive operations (deleting environments, services, volumes, domains, or deployments) should be used carefully. Volume deletion permanently removes data; environment deletion removes its deployments.

## API limitations

- Railway's public API is GraphQL and its schema can evolve. Every operation is validated by Railway at request time; permissions depend on the token scope.
- CPU, memory, disk and network metrics are available in Railway's observability surfaces and CLI. The public GraphQL API docs do not currently provide a stable metrics query example, so the dashboard does not invent usage values. The Metrics / API page inspects the live GraphQL query schema and provides an API explorer.
- Log and deployment data is live only when the selected token can access the selected project and environment.

## Official documentation

- Public API: https://docs.railway.com/integrations/api
- GraphQL overview: https://docs.railway.com/integrations/api/graphql-overview
- API cookbook: https://docs.railway.com/integrations/api/api-cookbook
- Manage deployments: https://docs.railway.com/integrations/api/manage-deployments
- Manage variables: https://docs.railway.com/integrations/api/manage-variables
- Manage environments: https://docs.railway.com/integrations/api/manage-environments
- Manage domains: https://docs.railway.com/integrations/api/manage-domains
- Manage volumes: https://docs.railway.com/integrations/api/manage-volumes
