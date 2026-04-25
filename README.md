# github-copilot-mcps_tech-summit-2026-04
Conteúdos da apresentação "Como o GitHub Copilot + MCPs podem ser úteis no setup inicial e documentação de novas aplicações?"

Prompt file e arquivos utilizados na demonstração com o GitHub Copilot: https://github.com/renatogroffe/github-copilot-dotnet10-minimalapi-otel-grafana-docker-prompt

Alguns MCPs públicos para testes:

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
