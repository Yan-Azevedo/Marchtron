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
