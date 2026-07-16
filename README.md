# Vesta — Landing Page

Landing page da Vesta, servida via GitHub Pages em
**https://dev-vesta.github.io/landing_page/**.

## Estrutura

```
index.html                ← landing publicada (redesign "Landing Vesta v2")
support.js                ← runtime de render do protótipo (carrega React/Babel via CDN)
vesta_logo_dark.svg       ← logo para fundo escuro
uploads/
  vesta_logo_light.svg    ← logo para fundo claro
.github/workflows/
  pages.yml               ← deploy automático no GitHub Pages
redesign/                 ← exports de design originais (arquivo-fonte)
  Landing Vesta v2.dc.html
  Landing Vesta.dc.html
  Vesta.dc.html           ← redesign do app administrativo
  support.js
  vesta_logo_dark.svg
```

A página `index.html` é um export do editor de design (elementos `<x-dc>` +
templates `{{ }}`). O `support.js` interpreta esse markup no navegador,
carregando React e Babel automaticamente via unpkg — não há etapa de build.

## Deploy

O deploy é automático via GitHub Actions a cada push na branch `main`
(`.github/workflows/pages.yml`, com o Pages auto-habilitado).

Para trocar a landing publicada, substitua `index.html` por outro export de
`redesign/` (mantendo o `support.js` e os logos na raiz).
