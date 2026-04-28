# github-copilot-mcps_tech-summit-2026-04
Conteúdos da apresentação "Como o GitHub Copilot + MCPs podem ser úteis no setup inicial e documentação de novas aplicações?"

Prompt file e arquivos utilizados na demonstração com o GitHub Copilot: https://github.com/renatogroffe/github-copilot-dotnet10-minimalapi-otel-grafana-docker-prompt

Tecnologias utilizadas: **.NET 10, ASP.NET Core, C#, Docker, Docker Compose, Grafana, Grafana Tempo, OpenTelemetry, OpenAPI, GitHub Copilot, Visual Studio Code...**

Alguns MCPs úteis:

| Descrição | Comando / URL de Ativação | Link |
|-----------|---------------------------|------|
| MCP Oficial do Microsoft Learn | `https://learn.microsoft.com/api/mcp` | https://github.com/microsoftdocs/mcp |
| MCP de geração de dados fake | `docker run -i --rm renatogroffe/dotnet10-consoleapp-mcp-fakedata` | https://github.com/renatogroffe/dotnet10-consoleapp-mcp-fakedata |
| MCP Oficial do draw.io | https://mcp.draw.io/mcp | https://github.com/jgraph/drawio-mcp |
| MCP Oficial do Excalidraw | https://mcp.excalidraw.com | https://github.com/excalidraw/excalidraw-mcp |
| Extensão Oficial do Postgres (inclui MCP Server) | - | https://marketplace.visualstudio.com/items?itemName=ms-ossdata.vscode-pgsql |
| Extensão Oficial do SQL Server (inclui MCP Server) | - | https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql |
| Extensão Oficial do Mermaid (inclui MCP Server) | - | https://marketplace.visualstudio.com/items?itemName=MermaidChart.vscode-mermaid-chart |


Um arquivo mcp.json com outros MCPs públicos para testes:

```json
{
	"servers": {
		"nuget": {
			"type": "stdio",
			"command": "dnx",
			"args": [
				"NuGet.Mcp.Server@1.1.29",
				"--yes"
			]
		},
		"docker": {
			"command": "docker",
			"args": [
				"run",
				"-i",
				"--rm",
				"-e",
				"HUB_PAT_TOKEN=${input:hub_pat_token}",
				"mcp/dockerhub"
			],
			"type": "stdio"
		},
		"github": {
		  "type": "http",
		  "url": "https://api.githubcopilot.com/mcp/"
		}
	},
	"inputs": [
		{
			"id": "hub_pat_token",
			"type": "promptString",
			"description": "Docker Hub Personal Access Token",
			"password": true
		}
	]
}
```

Referências:
- https://docs.github.com/en/copilot/tutorials/customization-library/prompt-files
