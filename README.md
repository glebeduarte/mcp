# Marvel Crisis Protocol RN

Site comunitário para organizar eventos de Marvel Crisis Protocol, com referência de missões e Encontros Definitivos em português.

## Estrutura

```
index.html                     Página inicial: eventos, missões e encontros
assets/
  css/mcp-ds.css               Design system (documentos A4 e páginas web)
  fonts/                       Bebas Neue e Crimson Pro
  img/                         Logo e artes dos encontros
eventos/
  bootcamp-2026/
    index.html                 Página web do evento
    guia.html                  Guia do organizador em páginas A4 (imprime direto)
    MCP_Bootcamp_Guia.pdf      PDF gerado do guia.html
missoes/index.html             Cartas de Crise resumidas
encontros/
  index.html                   Hub dos Encontros Definitivos
  ultron.html                  Tudo Será Metal (regras + painel de mesa)
  hulk.html                    O Incrível Hulk (regras + painel de mesa)
design-system/index.html       Guia do design system, com componentes e modelos
ultron.html, hulk.html         Redirecionamentos dos links antigos
```

## Como criar um evento novo

1. Copie `eventos/bootcamp-2026/` para `eventos/<nome-do-evento>/`.
2. Edite `index.html` (página web) e `guia.html` (documento A4). Os dois usam o mesmo CSS, então o visual fica igual.
3. Para gerar o PDF, abra `guia.html` no navegador e imprima em A4 com margens zero e gráficos de fundo ligados. Ou use o Chromium sem interface:
   ```
   chromium --headless --print-to-pdf=MCP_<nome>.pdf --no-margins guia.html
   ```
4. Inclua um card do evento em `index.html` na raiz.

## Como adicionar uma missão

Copie um card em `missoes/index.html`, troque o `id`, o nome, o tipo (Secure ou Extraction) e o resumo. Se o evento usa a missão, linke a partir da página do evento.

## Como adicionar um Encontro Definitivo

Coloque o HTML em `encontros/` e inclua um card em `encontros/index.html` e em `index.html`.

## Design system

Tudo está em `assets/css/mcp-ds.css`. Componentes:

- Documento A4: `.page`, `.band`, `.page-num`, `.cover`
- Texto: `h1` a `h4`, `.lead`, `.small`, `.mute`, `.columns`, `.grid-2`, `.grid-3`
- Regras: `table.mcp`, `.stat`, `.example`, `.note` (com `--alert` e `--gold`)
- Jogo: `.squad`, `.threat`, `.pill`, `.glyph`, `.steps`
- Site: `.topbar`, `.hero`, `.section`, `.cards`, `.card`, `.btn`, `.kpis`, `.sched`, `.versus`, `.checklist`, `.footer`

O guia completo, com exemplos, está em `design-system/index.html`.

## Créditos

Marvel Crisis Protocol e as artes oficiais pertencem à Marvel e à Atomic Mass Games. Material comunitário sem fins comerciais.
