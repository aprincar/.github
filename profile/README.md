<p align="center">
  <img src="./assets/aprincar-logo.svg" alt="Aprincar — Aprender acontece brincando." width="460" />
</p>

<p align="center">
  <strong>Uma plataforma aberta, local-first e offline-first para aprender brincando.</strong>
</p>

<p align="center">
  <a href="https://aprincar.github.io/platform/"><strong>Experimentar o beta</strong></a>
  ·
  <a href="https://github.com/aprincar/.github/blob/main/docs/GETTING_STARTED.md">Rodar localmente</a>
  ·
  <a href="https://github.com/aprincar/.github/blob/main/docs/EXTENSIONS.md">Criar um jogo</a>
  ·
  <a href="https://github.com/aprincar/.github/blob/main/CONTRIBUTING.md">Contribuir</a>
</p>

## Status

**Beta aberto para testes.** A plataforma V1 está publicada e o ecossistema já possui runtime isolado para jogos, progresso local, Skill Graph, integração curricular e templates de autoria.

O catálogo oficial de jogos está entrando agora em uma rodada específica de **hardening de experiência, precisão pedagógica e confiabilidade**. Isso significa que o beta já pode ser explorado, mas os jogos ainda não devem ser tratados como conteúdo final validado para uso pedagógico sem supervisão.

Veja [como testar o beta e reportar problemas](../docs/BETA_TESTING.md).

<p align="center">
  <a href="https://aprincar.github.io/platform/">
    <img src="https://raw.githubusercontent.com/aprincar/platform/v1.0.0/_validation/screenshots/tablet-home.png" alt="Tela inicial do Aprincar V1 em tablet" width="760" />
  </a>
</p>

## O que é o Aprincar?

O Aprincar nasce da junção de **APRender + brINCAR**. A proposta é oferecer experiências educacionais em que a criança explora, tenta, cria e descobre — sem transformar a brincadeira em um LMS infantil.

Princípios centrais:

- local-first e offline-first;
- sem login obrigatório para a criança;
- sem anúncios infantis, loot boxes, FOMO ou moedas pagas;
- privacidade infantil e permissões sensíveis em default-deny;
- jogos executados em sandbox e integrados ao host por SDK;
- evidência de atividade não é automaticamente domínio de uma habilidade;
- BNCC é mapeada por meio do Skill Graph, nunca diretamente pelo jogo.

## Ecossistema

| Repositório | Papel |
| --- | --- |
| [platform](https://github.com/aprincar/platform) | Aplicação web/PWA, Hub, runtime, SDK, progresso, armazenamento e distribuição |
| [games-official](https://github.com/aprincar/games-official) | Catálogo oficial e código-fonte dos jogos mantidos pelo projeto |
| [community-games](https://github.com/aprincar/community-games) | Fluxo de publicação e curadoria de jogos da comunidade |
| [curriculum-bncc](https://github.com/aprincar/curriculum-bncc) | Adaptador curricular e mapeamentos conservadores para a BNCC |
| [game-template-vite](https://github.com/aprincar/game-template-vite) | Template mínimo para extensões web |
| [game-template-react](https://github.com/aprincar/game-template-react) | Template para jogos e atividades em React |
| [game-template-phaser](https://github.com/aprincar/game-template-phaser) | Template para experiências 2D com Phaser |
| [game-template-threejs](https://github.com/aprincar/game-template-threejs) | Template para experiências 3D com Three.js |
| [.github](https://github.com/aprincar/.github) | Contratos do produto, documentação transversal e governança |

## Arquitetura em uma frase

`React App → GameHost → sandboxed iframe → game.html ↔ MessageChannel → Aprincar SDK`

O jogo não acessa diretamente IndexedDB da aplicação, DOM do responsável, PIN, dados completos do perfil ou APIs privilegiadas. Capacidades passam pelo host.

## Para começar

**Quero testar:** abra o [beta publicado](https://aprincar.github.io/platform/) e siga o roteiro de [teste do beta](../docs/BETA_TESTING.md).

**Quero desenvolver o Aprincar:** consulte [Começando](../docs/GETTING_STARTED.md), [Arquitetura](../docs/ARCHITECTURE.md) e [Operação](../docs/OPERATIONS.md).

**Quero criar um jogo:** comece por [Extensões](../docs/EXTENSIONS.md) e escolha um dos templates oficiais.

**Quero entender as regras do produto:** leia primeiro o [Product Contract](../docs/product/PRODUCT_CONTRACT.md), depois [Visão](../docs/product/VISION.md) e [Princípios](../docs/product/PRINCIPLES.md).

## Versões

A plataforma possui release pública **v1.0.0**. Manifest Schema e protocolo do SDK usam versionamento independente do SemVer dos pacotes.

A V1 estabelece a base técnica. A próxima etapa de produto prioriza qualidade dos jogos, acessibilidade, ergonomia de autoria e robustez de uso real.

---

**Aprincar — Aprender acontece brincando.**
