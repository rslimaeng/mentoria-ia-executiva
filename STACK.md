# STACK — Mentoria IA Executiva

## Tecnologias

- **Fraunces** — fonte serif display variável para títulos; eixos: `opsz` (9–144), `SOFT` (0–100), `wght` (300–900); carregada via Google Fonts CDN. Usada com `font-variation-settings` explícito em cada contexto.
- **Inter Tight** — fonte sans-serif principal para corpo de texto, botões e labels; pesos 400–700; carregada via Google Fonts CDN.
- **CSS Custom Properties** — sistema de design tokens em `:root` com variáveis de cor (`--coral`, `--terra-*`, `--cream-*`, `--ocre-*`) e easing (`--ease-spring`).
- **CSS Grid** — layout de seções: `section-header` (120px · 1fr), `phase-grid` (2×2), `compare-grid` (1fr 1fr), `hero-stats-row` (repeat 4 · 1fr), `about-stats-row` (repeat 3 · 1fr).
- **CSS Flexbox** — sticky nav, hero CTA row, about-header com foto, about-links, pain card icon alignment, btn-cta interno.
- **`grid-template-rows: 0fr → 1fr`** — técnica CSS para animação suave de altura zero em accordions (FAQ e pain-resolve) sem JavaScript de altura fixa.
- **`max-height: 0 → 160px` + `overflow: hidden`** — reveal do contador de pain cards; usa transição suave sem `height: auto`.
- **`clamp()` CSS** — tipografia fluida nos títulos (`.hero-headline`, `.section-title`, `.price-main-dark`, `.closing-title`).
- **`font-variation-settings`** — controle manual dos eixos da Fraunces variável: `'opsz'` controla tamanho óptico, `'SOFT'` controla arredondamento de serifa (0 = clássico, 100 = suave).
- **IntersectionObserver API** — dois observadores: (1) scroll-reveal — adiciona `.visible` em elementos `.reveal` conforme entram na viewport; (2) sticky nav — aparece quando o `#hero` sai da viewport.
- **`cubic-bezier(.16, 1, .3, 1)`** — easing spring em todas as transições animadas (hover de botão, reveals, FAQ, pain-resolve). Guardado em `--ease-spring`.
- **`backdrop-filter: blur(20px)`** — efeito fosco na sticky nav ao fazer scroll.
- **WhatsApp API** — link `https://api.whatsapp.com/send?phone=5585999127104` em todos os CTAs (6 pontos: sticky nav, hero, investimento, fechamento, footer, float).

## Convenções de Código

- **Arquivo único** — todo CSS inline em `<style>` no `<head>`, JavaScript inline em `<script>` antes de `</body>`; sem dependências externas além das fontes Google.
- **Container** — `max-width: 920px; margin: 0 auto; padding: 0 32px` (mobile: 24px, 480px: 20px).
- **Paleta de ação** — coral (`#D97757`) como cor primária de ação; terra-900 (`#2B1F17`) para seções dark; cream-100 como fundo padrão de página.
- **Easing universal** — `var(--ease-spring)` em todos os hovers, reveals e transições de interface; nunca `linear` ou `ease-in`.
- **Breakpoints** — `768px` (tablet/mobile principal — colapsa grids e section-header), `480px` (mobile pequeno — padding reduzido, about-header empilhado).
- **Reveal pattern** — todo elemento animável recebe `.reveal`; delays com `.rd1`–`.rd5` (07s, 14s, 21s, 28s, 35s); o observer adiciona `.visible` e para de observar.
- **Dark sections** — usam `--terra-900` como bg; texto e bordas em rgba(255,255,255,.X) para evitar tokens separados de tema.
- **Organização CSS** — comentários `/* ── NOME ─── */` delimitam cada bloco; ordem: reset → tokens → animações → componentes por seção.

## GitHub Pages

- **Repo:** `rslimaeng/mentoria-ia-executiva`
- **URL:** `https://rslimaeng.github.io/mentoria-ia-executiva/`
- **Branch:** `main` → root `/`
- **Arquivo principal:** `index.html` (= v2 da página)
- **Assets locais:** `assets/rafael.png` (foto circular do Rafael)
