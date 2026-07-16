# Vesta — Landing Page

Landing page da Vesta, servida via GitHub Pages em
**https://dev-vesta.github.io/landing_page/**.

## Estrutura

```
index.html                ← landing publicada (HTML/CSS estático + JS vanilla)
favicon.svg               ← ícone oficial da Vesta
vesta_logo_dark.svg       ← logo para fundo escuro (tema dark)
uploads/
  vesta_logo_light.svg    ← logo para fundo claro (tema light, padrão)
.github/workflows/
  pages.yml               ← deploy automático no GitHub Pages
redesign/                 ← exports originais do editor de design (arquivo-fonte)
  Landing Vesta v2.dc.html  ← protótipo que originou o index.html atual
  Landing Vesta.dc.html
  Vesta.dc.html             ← redesign do app administrativo
  support.js                ← runtime do protótipo (só necessário para os .dc.html)
```

## Como a página funciona

O `index.html` é **estático**: HTML/CSS com um bloco pequeno de JavaScript
vanilla no fim do arquivo. Sem React, sem build, sem CDN de runtime — apenas
as fontes vêm do Google Fonts (com fallback de sistema).

Interações implementadas em JS puro:

- tema claro/escuro (persistido em `localStorage`)
- palavra rotativa no título do hero
- barra de progresso, ticker e texto gigante guiados pelo scroll
- gráfico de barras do painel com hover/tap e auto-avanço
- stepper lateral de seções (IntersectionObserver)
- reveals ao rolar (com fallback: sem JS, tudo fica visível)
- FAQ acordeão e compromissos em hover

## Deploy

Automático via GitHub Actions a cada push na branch `main`
(`.github/workflows/pages.yml`, com Pages auto-habilitado).

## Editando

Para mudar textos e seções, edite o `index.html` diretamente — é HTML comum.
Os protótipos em `redesign/` são o arquivo-fonte de design original; mudanças
feitas neles **não** se propagam automaticamente para o `index.html`.
