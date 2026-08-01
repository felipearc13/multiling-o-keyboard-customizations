# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## O que é este repositório

Arquivos de configuração exportados do app Android [Multiling O Keyboard](https://play.google.com/store/apps/details?id=kl.ime.oh) — não é código, é customização de settings do app (tema escuro inspirado no Gboard, teclas extras CTRL/TAB, layout com acentuação em português). Repositório **público**.

## Estrutura completa

```text
multiling-o-keyboard-customizations/
├── README.md                    instruções de instalação, screenshots inline via raw.githubusercontent
├── CLAUDE.md
├── LICENSE                      Apache 2.0
├── settings.mok.txt             export das settings gerais (formato proprietário MOK)
├── 202209246.theme.mok.txt      export do tema (661 bytes)
├── W7.JSON                      layout de teclado custom, formato JSON do app
├── W8.JSON                      layout de teclado custom, variante do W7
├── WEEZY                        layout de teclado custom, formato texto plano (nome interno "DIY-2")
└── screenshot/                  7 imagens (JPG/PNG) usadas no README
```

## `settings.mok.txt`

Formato proprietário do Multiling O Keyboard: `OK_Settings_Begin` na primeira linha, depois uma linha por opção
no padrão `__Chave.subchave::valor::TIPO`, onde `TIPO` é `B` (boolean), `I` (integer) ou `S` (string). Exemplos
reais do arquivo: `__I.sw::true::B` (habilita algo do idioma inglês), `__V.mt::25::S`, `__S.emj9::😁\n😂\n...`
(lista de emojis do atalho 9). Importado via "Settings > Misc. > Import | Export > Settings" dentro do app —
colar o conteúdo bruto do arquivo.

## `202209246.theme.mok.txt`

Export de tema (`OK_Theme_Begin`, mesmo estilo `chave::valor::TIPO` do settings). O nome do arquivo é a data de
export em formato compacto (`20220924...`), não um identificador do tema em si.

## `W7.JSON` e `W8.JSON`

Dois layouts de teclado completos, formato JSON nativo do app (chave `title`, depois `onScreen` com as
sub-seções `main`/`shifted`/`sym`/`altGr` — cada uma é um array de 5 strings, uma por fileira de teclas — e
`topBar`, os atalhos da barra superior). Usam a sintaxe de tecla estendida `[XK:tecla-base<caracteres
alternativos por long-press>]` — ex.: `[XK:e|éèêëėęē]` é a tecla E com acentos em português/outras línguas
disponíveis via pressão longa.

Diferenças entre os dois:
- W7 tem uma seção `num` (não `123` como o W8) para o teclado numérico, com layout `+-123%` / `*/456[SPACE]` /
  `()789[DEL]` / `[Lock]=,0.[Enter]`.
- W8 tem `123` em vez de `num`, layout ligeiramente diferente: `+123-` / `*456/` / `[SPACE]789[DEL]` /
  `[Lock][XK:=()]=,0.[Enter]`.
- A tecla `M` minúscula difere: `[XK:m/]` no W7 (produz `/`) vs `[XK:m?]` no W8 (produz `?`).
- `topBar` do **W7** é bem mais longo que o do W8: além dos atalhos comuns (busca, copiar, colar, emoji,
  clipboard, tradutor, pontuação, aspas de vários idiomas), o W7 tem uma **assinatura de divulgação do
  desenvolvedor do app** embutida como um dos itens da barra —
  `D๑พทℓ๑α∂ Mบℓтïℓïทg👍OKεγв๑αя∂ https://play.google.com/store/apps/details?id=kl.ime.oh ⇦ԅ(ˆ。ˆԅ) 🆒🆕🇴🇰🇪🇾🇧🇴🇦🇷🇩🆓🆗
  #Multiling #OKeyboard #Android` — não é conteúdo do usuário, veio junto no layout (provavelmente W7/W8 são
  layouts de terceiros baixados/adaptados, não criados do zero pelo usuário).

## `WEEZY`

Terceiro layout, formato texto plano (não JSON) do app: começa com `OK_Layout_Begin` e `Name:DIY-2` — o nome
interno do layout é "DIY-2", diferente do nome do arquivo (`WEEZY`). Mesma sintaxe `[XK:...]` de teclas
estendidas do W7/W8, mas sem a estrutura JSON (`onScreen`/`topBar`) — é o formato de import/export mais antigo
do app, usado para um único layout por arquivo em vez do settings completo.

## `screenshot/`

7 arquivos (`1.jpg`, `new-1.jpg` a `new-4.jpg`, 2 `Screenshot_2022-09-03-*.png`) — capturas de tela reais do
teclado em uso, referenciadas pelo `README.md` via URL `raw.githubusercontent.com` (não `<img>` local, então o
README depende do repositório estar público e da branch `main` existir).

Não há build, lint ou testes — a "instalação" é manual, colando o conteúdo de `settings.mok.txt` dentro do app.
