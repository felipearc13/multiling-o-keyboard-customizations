# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## O que é este repositório

Arquivos de configuração exportados do app Android [Multiling O Keyboard](https://play.google.com/store/apps/details?id=kl.ime.oh) — não é código, é customização de settings do app (tema escuro inspirado no Gboard, teclas extras CTRL/TAB, layout com acentuação em português). Repositório **público**.

## Estrutura

- `settings.mok.txt` — export das configurações gerais do teclado, importável via "Settings > Misc. > Import | Export > Settings" no app.
- `202209246.theme.mok.txt` — export do tema.
- `W7.JSON`, `W8.JSON`, `WEEZY` — layouts/perfis adicionais.
- `screenshot/` — capturas de tela usadas no `README.md`.

Não há build, lint ou testes — a "instalação" é manual, colando o conteúdo de `settings.mok.txt` dentro do app.
