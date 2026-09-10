# KodarosLanding — Plataforma de Crescimento KODAROS

![Site](https://img.shields.io/badge/site-live-D4AF6A?style=flat-square&label=kelvinoliveiracode.github.io%2FKodarosLanding)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Zero deps](https://img.shields.io/badge/depend%C3%AAncias-0-2EA44F?style=flat-square)

Página oficial do ecossistema **KODAROS** — software, educação e ferramentas para pequenos negócios. Single-page application em **HTML/CSS/JS puro** (679 linhas de HTML + 939 de JS, zero dependências de build), com funil de diagnóstico interativo ("Oráculo"), biblioteca de e-books com filtros e painel de softwares. Direção de arte "Dossiê": obsidiana `#070709`, tipografia Cinzel + Cormorant Garamond + Figtree, acento dourado `#D4AF6A` e partículas douradas em canvas nos dois cantos inferiores.

**Live:** https://kelvinoliveiracode.github.io/KodarosLanding/ (case-sensitive)

---

## 🇧🇷 Português

### O que é

O hub central do ecossistema KODAROS (4 sites em produção). Reúne em uma página:

- **Hero** com identidade da marca (navbar KODAROS em Cinzel + busto dourado, fundo bg-salao.jpg);
- **Roteiro** — como funciona a plataforma, passo a passo;
- **Ecossistema** em 3 painéis acessíveis (roles ARIA `tablist`/`tab`/`tabpanel`, `aria-selected`, estados `hidden`):
  - **Biblioteca** — 8 e-books com filtros por categoria;
  - **Diagnóstico "Oráculo"** — quiz interativo com máquina de estados (intro → perfil → 4 perguntas adaptadas ao perfil → resultado), brinde gratuito e vitrine de produtos → site principal com UTM `utm_source=funil`;
  - **Softwares** — vitrine dos produtos;
- **Ferramentas** — link para as 53 calculadoras do PWA KODAROS Ferramentas;
- **Diferenciais, depoimentos e contato** — fechamento comercial.

### E-books da biblioteca

| Título | Categoria |
|---|---|
| Arquitetura de Aquisição | Aquisição & Tráfego |
| Lançamento Milionário | Lançamento |
| Tráfego Que Vende | Aquisição & Tráfego |
| Venda Mais Hoje | Vendas |
| Os 10 Pilares da Gestão Empresarial | Gestão |
| Os 10 Pilares do Controle Financeiro | Financeiro |
| Use Seu Site Para Escalar Sua Empresa | Sites |
| Transforme Reclamações em Vendas | Suporte |

Preço de vitrine: de R$ 47,00 por R$ 12,99 (Hotmart). Bônus gratuito: e-book "Do Zero ao Patrimônio" (PDF).

### Engenharia do funil Oráculo

O diagnóstico é uma state machine em JS puro:

```
state = { profile, qIndex, answers }
steps: .step → intro → profile → quiz (4 perguntas adaptadas) → result
```

- Perguntas adaptam-se ao perfil declarado (básico/intermediário/avançado);
- O resultado combina respostas, entrega brinde + 2 vitrines e direciona ao site principal com UTM de rastreamento;
- Catálogo de produtos espelhado em objeto único `PRODUCTS` — fonte de verdade para preços, capas e URLs.

### Decisões técnicas

- **Zero dependências**: sem framework, sem build step — o site é o deliverable; deploy direto no GitHub Pages;
- **Acessibilidade**: painéis com roles ARIA completos e estados `hidden` nativos;
- **SEO**: meta description, Open Graph (og:title/description/image/type), JSON-LD `Organization` com `sameAs` (Instagram oficial), theme-color e favicon dedicados;
- **Performance**: partículas em canvas único (dois emissores nos cantos inferiores), animações em `cubic-bezier(0.22,1,0.36,1)`, `scroll-behavior: smooth`;
- **Design system em CSS custom properties**: paleta pedra (obsidiana, basalto, temple, coluna), tintas (primary/muted/dim), acento áureo em 6 tons e papel claro para contraste.

### Estrutura

```
KodarosLanding/
├── index.html    # 679 linhas — toda a página + CSS embutido
├── script.js     # 939 linhas — partículas, tabs, funil Oráculo, catálogo
└── assets        # capas dos e-books, logos, bg-salao.jpg
```

### Autor

**Kelvin Oliveira** — fundador do ecossistema KODAROS · [GitHub](https://github.com/KelvinOliveiraCode) · [LinkedIn](https://www.linkedin.com/in/kelvin-oliveira-0282033b4/)

---

## 🇺🇸 English

The official hub of the **KODAROS** ecosystem — software, education and tools for small businesses. A single-page application in **vanilla HTML/CSS/JS** (679 lines of HTML + 939 of JS, zero build dependencies), featuring an interactive diagnosis funnel ("Oráculo"), a filterable e-book library and a software showcase. "Dossier" art direction: obsidian `#070709`, Cinzel + Cormorant Garamond + Figtree typography, gold accent `#D4AF6A` and golden canvas particles rising from both bottom corners.

**Live:** https://kelvinoliveiracode.github.io/KodarosLanding/ (case-sensitive)

### What's in it

- **Hero** with brand identity (KODAROS navbar in Cinzel + golden bust, bg-salao.jpg backdrop);
- **Journey** — how the platform works, step by step;
- **Ecosystem** in 3 accessible panels (full ARIA tablist/tab/tabpanel roles):
  - **Library** — 8 e-books with category filters;
  - **"Oráculo" diagnosis** — interactive quiz as a state machine (intro → profile → 4 profile-adaptive questions → result), free lead magnet and product showcases → main site with `utm_source=funil`;
  - **Software** — product showcase;
- **Tools** — link to the 53 calculators in the KODAROS Ferramentas PWA;
- **Differentiators, testimonials and contact** — commercial close.

### Oráculo funnel engineering

The diagnosis is a state machine in pure JS:

```
state = { profile, qIndex, answers }
steps: .step → intro → profile → quiz (4 adaptive questions) → result
```

Questions adapt to the declared profile; the result combines answers, delivers a free gift + 2 showcases and forwards to the main site with tracking UTM. The product catalog lives in a single `PRODUCTS` object — the source of truth for prices, covers and URLs.

### Technical decisions

- **Zero dependencies**: no framework, no build step — the site is the deliverable; direct GitHub Pages deploy;
- **Accessibility**: panels with complete ARIA roles and native `hidden` states;
- **SEO**: meta description, Open Graph, JSON-LD `Organization` with official `sameAs`, dedicated theme-color and favicon;
- **Performance**: single-canvas particles (two emitters at bottom corners), `cubic-bezier(0.22,1,0.36,1)` easing, smooth scroll;
- **CSS custom-property design system**: stone palette, ink tones, six-step gold accent and light paper for contrast.

### Author

**Kelvin Oliveira** — KODAROS ecosystem founder · [GitHub](https://github.com/KelvinOliveiraCode) · [LinkedIn](https://www.linkedin.com/in/kelvin-oliveira-0282033b4/)
