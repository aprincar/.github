# Documentação geral do Aprincar

Este diretório é o ponto de entrada da organização Aprincar. Ele explica o produto, seus contratos arquiteturais, como os repositórios se conectam, como executar o sistema localmente, como criar extensões e como participar do fluxo de revisão.

## Produto

| Documento | Quando consultar |
| --- | --- |
| [Product Contract](product/PRODUCT_CONTRACT.md) | Invariantes que implementações não podem quebrar sem ADR |
| [Visão](product/VISION.md) | Objetivos do produto e critérios de decisão |
| [Princípios](product/PRINCIPLES.md) | Restrições de produto, privacidade, arquitetura e UX |
| [Versionamento](product/VERSIONING.md) | Versionamento e gates de release |
| [Roadmap](product/ROADMAP.md) | V1.0, V1.1 e V1.2 |
| [Glossário](product/GLOSSARY.md) | Vocabulário canônico do ecossistema |
| [Auditoria 2026](audits/ECOSYSTEM_AUDIT_2026.md) | Estado auditado e gaps P1/P2 |

## Engenharia

| Documento | Quando consultar |
| --- | --- |
| [Começando](GETTING_STARTED.md) | Primeira instalação e execução local |
| [Projetos](PROJECTS.md) | Escolher o repositório correto |
| [Arquitetura](ARCHITECTURE.md) | Entender App, Hub, jogos e dados |
| [Extensões](EXTENSIONS.md) | Criar, validar e publicar um jogo |
| [Operação e release](OPERATIONS.md) | CI, Pages, offline e troubleshooting |
| [Contribuição](../CONTRIBUTING.md) | Branches, commits, PRs e revisão |
| [Segurança](../SECURITY.md) | Reportar vulnerabilidades |

## Princípios rápidos

- O App é local-first e offline-first.
- Jogos são extensões independentes e isoladas pelo GameHost.
- Evidence não é mastery; somente o Progress Engine calcula SkillState.
- Recompensas são separadas de progresso pedagógico.
- BNCC é mapeamento do Skill Graph, nunca dependência direta do jogo.
- Permissões sensíveis são default-deny e exigem grant explícito do Host.
- Privacidade infantil, acessibilidade e segurança fazem parte da definição de pronto.

## Repositórios

Todos os repositórios públicos estão em [github.com/aprincar](https://github.com/aprincar). O site publicado está em [aprincar.github.io/platform](https://aprincar.github.io/platform/).
