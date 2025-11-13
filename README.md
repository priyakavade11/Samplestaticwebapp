
# Azure Static Web Apps + Blazor WebAssembly (Sample)

This repo contains a minimal **Blazor WebAssembly** app ready to deploy to **Azure Static Web Apps** via **GitHub Actions**.

## Prerequisites
- .NET 8 SDK: https://dotnet.microsoft.com/download
- Azure Subscription & Static Web App resource (Standard/Free)
- GitHub repository
- SWA Deployment Token as GitHub Secret: `AZURE_STATIC_WEB_APPS_API_TOKEN`

## Local Run
```bash
cd src/BlazorSwa.Client
dotnet restore
dotnet run
```
Open the URL printed in console (e.g., https://localhost:****).

## Deploy
1. Push this repo to GitHub (`main` branch).
2. Create a Static Web App in Azure or add `AZURE_STATIC_WEB_APPS_API_TOKEN` secret to the repo.
3. The GitHub Action in `.github/workflows/azure-static-web-apps.yml` will build and deploy:
   - app_location: `src/BlazorSwa.Client`
   - output_location: `wwwroot`

## Notes
- `staticwebapp.config.json` enables SPA fallback and sets secure headers.
- If you change the project path, update `app_location` in the workflow accordingly.
- For APIs, use SWA-managed Azure Functions (add `/api` project) or call external APIs with CORS enabled.
