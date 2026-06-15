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
 - Versão do app (`manifest.json`) elevada para 1.3.0.
- Configuração `mcp.json` do servidor MCP do Learn (transporte HTTP, sem autenticação).
- Arquivos base do repositório: `CHANGELOG.md`, `CODEOWNERS`, `LICENSE.md`, `README.md`.

### Changed
- instruction.txt convertido de JSON para texto puro estruturado, para legibilidade e manutenção.
- instruction.txt condensado para caber no limite de 8000 caracteres do declarative agent, mantendo persona, regra inegociável, roteamento Learn/MRC, passo a passo e proibições de resumo/pitch.
 - Conversation starters substituídos pelos temas reais do agente: novidades de Copilot Studio, Workflows, Copilot M365 e Copilot chat (1.3.4).

### Changed
- instruction.txt convertido de JSON para texto puro estruturado, para legibilidade e manutenção.
- Reforço de concisão nas respostas (corte de respostas longas e seções em excesso).
- Uso de emoji limitado a moderação.
- Acionamento obrigatório do MRC em perguntas de roadmap/novidades (antes respondidas apenas com Learn).
- Agente não oferece mais conteúdos extras não solicitados no final das respostas.
- Proibição explícita de seções de resumo (TL;DR, resumo executivo, leitura estratégica) e de ofertas de conteúdo extra não solicitado ao final.
- Tabelas restritas a comparações diretas.
- Roteamento de perguntas combinadas: parte de roadmap sempre acionando o MRC, mesmo quando a pergunta mistura temas de Learn.
- Versão do app elevada para 1.3.2.
- Metadados de publicação preenchidos no `manifest.json`: developer (Yan Azevedo), nome completo, descrições e URLs de privacidade e termos de uso.
- `contact_email` do `ai-plugin.json` atualizado.
- Versão do app elevada para 1.3.0.
- Persona refinada: Marchtron declarado como assistente técnico e de atualização focado em desenvolvimento de agentes e automação Microsoft (Copilot Studio, Power Automate, Dataverse, Copilot M365).
- Comportamento de resposta ajustado: resposta curta e direta por padrão; passo a passo numerado obrigatório em procedimentos "como fazer".
- Adicionada orientação de manutenção de contexto da conversa entre turnos.

### Added
- Documentos `PRIVACY.md` e `TERMS.md` na raiz do repositório.

### Pendente
- Definição da persona e do `instruction.txt` (regra de resposta: priorizar sempre a informação mais atualizada via Learn MCP).
- `conversation_starters` no `declarativeAgent.json`.
- Ajuste de `contact_email` e `description_for_human` no `ai-plugin.json`.
- Primeiro provisionamento e teste ponta a ponta no Microsoft 365 Copilot.

---

Autoria: Yan Azevedo
