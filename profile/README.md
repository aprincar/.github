<p align="center">
  <img src="./assets/aprincar-logo.svg" alt="Aprincar — Aprender acontece brincando." width="460" />
</p>

<p align="center">
  <strong>Uma plataforma aberta, local-first e offline-first para aprender brincando.</strong>
</p>

<p align="center">
  <a href="https://aprincar.github.io/platform/"><strong>Experimentar o beta</strong></a>
  ·
  <a href="https://github.com/aprincar/platform#quero-rodar-localmente">Rodar localmente</a>
  ·
  <a href="https://github.com/aprincar/platform/blob/main/docs/EXTENSIONS.md">Criar um jogo</a>
  ·
  <a href="https://github.com/aprincar/platform/blob/main/CONTRIBUTING.md">Contribuir</a>
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

## Repositório oficial

Todo o desenvolvimento do Aprincar está concentrado em [aprincar/platform](https://github.com/aprincar/platform).

| Diretório | Papel |
| --- | --- |
| [apps](https://github.com/aprincar/platform/tree/main/apps) | Aplicação e Hub |
| [packages](https://github.com/aprincar/platform/tree/main/packages) | Runtime, SDK, progresso e armazenamento |
| [games](https://github.com/aprincar/platform/tree/main/games) | Jogos oficiais e comunitários |
| [content](https://github.com/aprincar/platform/tree/main/content) | Currículo BNCC |
| [templates](https://github.com/aprincar/platform/tree/main/templates) | Exemplos de autoria |

Novas contribuições e issues devem ser encaminhadas ao repositório principal. Os antigos repositórios de desenvolvimento permanecem como referências históricas até o encerramento da migração. O repositório especial `.github` mantém o perfil e a governança da organização.

## Arquitetura em uma frase

`React App → GameHost → sandboxed iframe → game.html ↔ MessageChannel → Aprincar SDK`

O jogo não acessa diretamente IndexedDB da aplicação, DOM do responsável, PIN, dados completos do perfil ou APIs privilegiadas. Capacidades passam pelo host.

## Para começar

**Quero testar:** abra o [beta publicado](https://aprincar.github.io/platform/) e siga o roteiro de [teste do beta](../docs/BETA_TESTING.md).

**Quero desenvolver o Aprincar:** consulte [Começando](https://github.com/aprincar/platform#quero-rodar-localmente), [Arquitetura](https://github.com/aprincar/platform/blob/main/docs/ARCHITECTURE.md) e [Operação](https://github.com/aprincar/platform/blob/main/docs/OPERATIONS.md).

**Quero criar um jogo:** comece por [Extensões](https://github.com/aprincar/platform/blob/main/docs/EXTENSIONS.md) e escolha um dos templates oficiais.

**Quero entender as regras do produto:** leia primeiro o [Product Contract](../docs/product/PRODUCT_CONTRACT.md), depois [Visão](../docs/product/VISION.md) e [Princípios](../docs/product/PRINCIPLES.md).

## Versões

A plataforma possui release pública **v1.0.0**. Manifest Schema e protocolo do SDK usam versionamento independente do SemVer dos pacotes.

A V1 estabelece a base técnica. A próxima etapa de produto prioriza qualidade dos jogos, acessibilidade, ergonomia de autoria e robustez de uso real.

---

**Aprincar — Aprender acontece brincando.**
