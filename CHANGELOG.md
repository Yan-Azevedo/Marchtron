# Changelog

Todas as mudanças relevantes deste projeto são documentadas neste arquivo.

O formato é baseado em [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/),
e este projeto adere ao [Versionamento Semântico](https://semver.org/lang/pt-BR/).

## [Unreleased]

## [1.3.7] - 2026-06-16

### Added
- Estrutura inicial do agente declarativo **Marchtron** via Microsoft 365 Agents Toolkit.
- Conexão com o **Microsoft Learn MCP Server** (`https://learn.microsoft.com/api/mcp`, público, sem autenticação) como fonte de grounding obrigatória, com 3 tools:
  - `microsoft_docs_search` — busca semântica na documentação oficial.
  - `microsoft_docs_fetch` — recuperação de página completa em markdown.
  - `microsoft_code_sample_search` — busca de exemplos de código oficiais.
- Conexão com o **Microsoft Release Communications MCP Server** (`https://www.microsoft.com/releasecommunications/mcp`, público, sem autenticação) com 4 tools:
  - `get_recent_m365_roadmaps` — roadmap do Microsoft 365.
  - `get_m365_roadmap_by_id` — item específico do roadmap M365.
  - `get_recent_azure_updates` — atualizações e retirements do Azure.
  - `get_azure_update_by_id` — item específico do Azure.
- Action MCP consolidada em `ai-plugin.json` (7 functions, 2 runtimes `RemoteMCPServer`, sem autenticação).
- Configuração `mcp.json` com os servidores MCP do Learn e do MRC (transporte HTTP).
- Instruções de comportamento do agente em `instruction.txt`: persona de especialista técnico, regra inegociável de grounding obrigatório via MCP, fluxo de raciocínio (search → fetch → code_sample) e regras de veracidade.
- Conversation starters com os temas reais do agente: novidades de Copilot Studio, Workflows, Copilot M365 e Copilot chat.
- Documentos `PRIVACY.md` e `TERMS.md` na raiz do repositório.
- Arquivos base do repositório: `README.md`, `CHANGELOG.md`, `LICENSE.md`, `CODEOWNERS`.

### Changed
- `instruction.txt` convertido de JSON para texto puro estruturado, para legibilidade e manutenção.
- `instruction.txt` condensado para caber no limite de 8000 caracteres do declarative agent, mantendo persona, regra inegociável, roteamento Learn/MRC, passo a passo e proibições de resumo/pitch.
- Persona refinada: Marchtron declarado como assistente técnico e de atualização focado em desenvolvimento de agentes e automação Microsoft (Copilot Studio, Power Automate, Dataverse, Copilot M365).
- Comportamento de resposta ajustado: resposta curta e direta por padrão; passo a passo numerado obrigatório em procedimentos "como fazer".
- Adicionada orientação de manutenção de contexto da conversa entre turnos.
- Acionamento obrigatório do MRC em perguntas de roadmap/novidades (antes respondidas apenas com Learn).
- Roteamento de perguntas combinadas: a parte de roadmap sempre aciona o MRC, mesmo quando a pergunta mistura temas do Learn.
- Tabelas restritas a comparações diretas; emoji limitado a uso moderado.
- Proibição explícita de seções de resumo (TL;DR, resumo executivo, leitura estratégica) e de ofertas de conteúdo extra não solicitado ao final das respostas.
- Reforço da regra de encerramento de resposta: proibição literal de ofertas de material extra e de blocos de leitura estratégica; agente não presume o papel do usuário.
- Metadados de publicação preenchidos no `manifest.json`: developer (Yan Azevedo), nome completo, descrições e URLs de privacidade e termos de uso.
- `contact_email` do `ai-plugin.json` atualizado.
- Removido o sufixo de ambiente do nome do agente; exibido como "Marchtron".
- Versão do app (`manifest.json`) elevada progressivamente até 1.3.5.

---

Autoria: Yan Azevedo