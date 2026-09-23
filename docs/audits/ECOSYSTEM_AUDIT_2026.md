# Aprincar — Ecosystem Audit 2026

Data: 2026-09-22

## Escopo

Auditoria baseada no estado real da organização `aprincar` no GitHub:

- `.github`
- `platform`
- `games-official`
- `community-games`
- `curriculum-bncc`
- `game-template-vite`
- `game-template-react`
- `game-template-phaser`
- `game-template-threejs`

## Resumo executivo

O ecossistema já implementa a maior parte da arquitetura pretendida: extensões isoladas, SDK/MessageChannel, Evidence separada de SkillState, Progress Engine, Reward Engine, Skill Graph, BNCC como crosswalk, PWA/local-first, trust levels, generators com fuzz/property testing e E2E semântico dos jogos oficiais.

Não foi identificado P0 confirmado durante a auditoria. O fechamento deve corrigir incoerências de fronteira e formalizar releases, sem reescrever o produto.

## P1 antes da V1 final

1. **Sensitive permissions:** `network`, `camera`, `microphone` e `geolocation` precisam de grant explícito do Host; declaração no manifesto não pode conceder capability.
2. **Registry merge:** App e Hub devem usar a implementação compartilhada com prioridade de trust; Official deve vencer conflitos independentemente da ordem da fonte.
3. **Distribuição oficial:** `games-official` deve permanecer source of truth; snapshots em App/Hub devem ser gerados deterministicamente a partir de ref imutável.
4. **Releases/versionamento:** formalizar versões e GitHub Releases somente após gates verdes no commit exato.
5. **Templates TS:** os quatro templates precisam de `tsconfig` e script explícito de `typecheck`.
6. **Documentação canônica:** Product Contract, Vision, Principles, Versioning, Roadmap e Glossary.
7. **Marca:** completar família de assets vetoriais e guidelines sem rebrand destrutivo.

## P2

- viewport explícito 393×852;
- axe/ARIA/focus regression;
- cobertura mais ampla de reduced-motion;
- READMEs dos templates mais completos;
- bundle/artifact budgets;
- release notes automáticas;
- link checker;
- matriz browser/PWA;
- testes de migration/versionamento do IndexedDB.

## Evidências relevantes

### Jogos oficiais

O catálogo auditado contém dez experiências oficiais. Há generators seedable, fuzz/property tests em milhares de seeds e E2E semântico cobrindo erro, recuperação, sucesso e propagação de Evidence.

### Progress/Trust

Experimental é ignorado pelo progresso real; Community recebe peso reduzido; consolidação exige múltiplas evidências/contextos confiáveis.

### BNCC

O crosswalk valida Skill IDs conhecidos, códigos BNCC presentes no catálogo local, versão, etapa, ano quando aplicável, relação e confidence. A expansão deve continuar conservadora.

### CI

No momento da auditoria, os workflows recentes relevantes estavam verdes, incluindo verificações de segurança no Platform. Isso é uma fotografia do estado auditado, não garantia de execuções futuras.

## Ordem de implementação

1. documentação canônica em `.github`;
2. runtime/Registry/distribuição em `platform`;
3. alinhamento de contrato em `games-official`;
4. templates;
5. `community-games`;
6. releases somente após validação dos commits finais.
