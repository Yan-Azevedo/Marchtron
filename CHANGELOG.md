# Changelog

Todas as mudanças relevantes deste projeto são documentadas neste arquivo.

O formato é baseado em [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/),
e este projeto adere ao [Versionamento Semântico](https://semver.org/lang/pt-BR/).

## [Unreleased]

### Added
- Estrutura inicial do agente declarativo **Marchtron** via Microsoft 365 Agents Toolkit.
- Conexão com o **Microsoft Learn MCP Server** (`https://learn.microsoft.com/api/mcp`) como fonte de grounding obrigatória.
- Action MCP (`ai-plugin.json`) com as três operações do Learn:
  - `microsoft_docs_search` — busca semântica na documentação oficial.
  - `microsoft_docs_fetch` — recuperação de página completa em markdown.
  - `microsoft_code_sample_search` — busca de exemplos de código oficiais.
- Conexão com o Microsoft Release Communications MCP Server (`https://www.microsoft.com/releasecommunications/mcp`, público, sem autenticação) com 4 tools: get_recent_m365_roadmaps, get_m365_roadmap_by_id, get_recent_azure_updates, get_azure_update_by_id.
- Orientação no `instruction.txt` para uso do MRC em perguntas sobre roadmap, release notes, status de disponibilidade e retirements, com separação de consultas entre Azure Updates e Microsoft 365 Roadmap.
- Versão do app (`manifest.json`) elevada para 1.2.0.
- Configuração `mcp.json` do servidor MCP do Learn (transporte HTTP, sem autenticação).
- Arquivos base do repositório: `CHANGELOG.md`, `CODEOWNERS`, `LICENSE.md`, `README.md`.

### Changed
- instruction.txt convertido de JSON para texto puro estruturado, para legibilidade e manutenção.

### Pendente
- Definição da persona e do `instruction.txt` (regra de resposta: priorizar sempre a informação mais atualizada via Learn MCP).
- `conversation_starters` no `declarativeAgent.json`.
- Ajuste de `contact_email` e `description_for_human` no `ai-plugin.json`.
- Primeiro provisionamento e teste ponta a ponta no Microsoft 365 Copilot.

---

Autoria: Yan Azevedo
