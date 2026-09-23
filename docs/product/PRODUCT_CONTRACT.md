# Aprincar — Product Contract

Este documento define invariantes do produto. Implementações podem mudar; estes limites não mudam sem ADR explícito e revisão de produto/arquitetura.

## Identidade

**Aprincar = APrender + brINCAR**

Tagline: **Aprender acontece brincando.**

Aprincar é uma plataforma aberta, local-first, offline-first e extensível de aprendizagem através do brincar.

Não é apenas um portal de jogos e não é um LMS/ERP infantil.

## Princípios

1. O núcleo permanece open source.
2. A experiência infantil funciona localmente.
3. Internet não é requisito para continuar usando conteúdo preparado.
4. Criança não precisa criar conta para brincar.
5. Não há publicidade infantil.
6. Não há loot boxes, FOMO, streak compulsivo, moeda paga ou dark pattern.
7. Aprendizado não fica atrás de paywall.
8. Parent Mode e Child Mode têm objetivos de UX diferentes.
9. Jogos são extensões; não fazem parte do bundle React da plataforma.
10. Segurança e privacidade infantil são fronteiras arquiteturais.

## Runtime

```text
App
 ↓
GameHost
 ↓
sandboxed iframe
 ↓
game.html
 ↕ MessageChannel
Aprincar SDK
```

Um jogo não recebe acesso direto a DOM pai, IndexedDB da plataforma, PIN/controles do responsável, dados completos de perfil, storage de outro jogo ou APIs privilegiadas.

## Permissions

Permissões sensíveis: `network`, `camera`, `microphone` e `geolocation`.

Regras:
- são default-deny;
- declaração no manifesto não equivale a concessão;
- devem ser opcionais;
- exigem grant explícito do Host;
- Community não recebe privilégio adicional;
- Experimental não recebe bypass.

## Evidence e Progress

```text
Game → Evidence → Evidence Validator → Evidence Ledger → Progress Engine → SkillState
```

Skill states: `UNKNOWN`, `EXPLORING`, `DEVELOPING`, `COMFORTABLE`, `CONSOLIDATED`.

Regras:
- jogo nunca grava SkillState;
- jogo nunca declara mastery;
- consolidação exige múltiplas evidências e contextos;
- Community pode informar progresso com confiança reduzida;
- Experimental não altera progresso real.

## Reward

Reward é motivacional e independente de SkillState. Reward não é mastery e estrelas não significam `CONSOLIDATED`.

## Trust

Ordem: Official → Curated → Community → Experimental.

O Registry resolve conflitos respeitando trust. Child Mode mostra Official/Curated por padrão; Community exige opt-in do responsável; Experimental não participa do progresso real.

## Skill Graph e Curriculum

```text
Game → Aprincar Skill → Curriculum Mapping → BNCC
```

Game não referencia BNCC diretamente. Relações curriculares permitidas: `direct`, `partial`, `supports`, `prerequisite`.

## Registry, Library, Cache e Offline

- Registry: o que existe.
- Library: o que o perfil escolheu.
- Cache: artifacts presentes no dispositivo.
- Available Offline: extensão resolvida/verificada e pronta para execução sem rede.

Adicionar à biblioteca não implica download.

## Distribuição oficial

```text
games-official source
 → deterministic build
 → test/fuzz
 → manifest validation
 → security
 → SHA-256 integrity
 → immutable artifact
 → canonical registry
 → Platform/Hub
```

App e Hub não mantêm registries oficiais independentes.

## UX infantil e mobile

A criança deve sentir que está brincando, explorando, criando, tentando e descobrindo. Evitar tabelas, dashboards administrativos, excesso de texto, formulários longos, linguagem de prova e gamificação coercitiva.

Mobile é superfície primária. No Child Mode: topo = marca + perfil; bottom navigation = Início, Descobrir, Biblioteca, Perfil/Mais; jogos ocupam runtime focado; safe area é obrigatória; touch targets mínimos de 44px.

## Games

Renderer não determina resposta pedagógica.

```text
Generator(input) -> ChallengeSpec
Renderer(ChallengeSpec) -> interaction
```

Generators devem ser determinísticos por seed e submetidos a property/fuzz tests.

## Mudanças incompatíveis

Uma fronteira estruturalmente errada não é perpetuada apenas por compatibilidade. Mudança incompatível exige ADR, versão, migration, atualização de SDK/templates/docs, testes e release notes.
