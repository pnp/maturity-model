# Maturity Model for Microsoft 365
Maturity Model for Microsoft 365 Pnp Site Repository.
This repository creates the website content at https://pnp.github.io/maturity-model

## Build Docs Locally

From the repository root:

```powershell
dotnet tool update -g docfx
docfx docs/docfx.json
```

Build output is generated in `docs/_site`.

## Serve Docs Locally

From the repository root:

```powershell
docfx docs/docfx.json --serve --port 8081
```

Then open `http://localhost:8081`.

## Troubleshooting

- If you are in the `docs` folder, use `docfx docfx.json` (not `docfx docs/docfx.json`).
- If port `8080` is in use, run with a different port (for example `--port 8081`).

<img src="https://m365-visitor-stats.azurewebsites.net/maturity-model/README"/>
