# Aprincar — Versioning and Release Policy

## Linhas de versão independentes

| Componente | Política |
|---|---|
| Platform | SemVer |
| Game SDK package | SemVer |
| SDK wire protocol | inteiro monotônico |
| Extension Manifest schema | inteiro monotônico |
| games-official catalog | SemVer |
| jogo individual | SemVer |
| curriculum-bncc dataset | SemVer |
| game templates | SemVer |

## Baseline V1

A promoção para V1 deve alinhar as versões públicas e internas efetivamente publicadas. Nenhuma versão deve ser alterada apenas para “parecer V1” sem que o commit correspondente tenha passado pelos gates de release.

## Regras

- breaking change: major;
- nova capability compatível: minor;
- correção compatível: patch;
- protocol/schema só sobem quando o wire/data contract muda;
- Platform não precisa compartilhar número com catálogo de jogos;
- Platform deve pin-ar ref imutável do catálogo oficial;
- release registra commit SHA, checks, known issues e migration notes.

## Gate

Nenhuma release recebe tag até CI, security, E2E e artifact integrity estarem verdes no commit exato.
