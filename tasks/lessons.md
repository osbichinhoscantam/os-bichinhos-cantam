---
ingestado: true
data_ingestion: 2026-05-08
---

# lessons.md — Preferências e aprendizados do site Os Bichinhos Cantam

---

## 2026-05-08 — Estado festivo pós-countdown (aprovado por Jr)

**Contexto:** quando o countdown zera (lançamento em 12/05/2026), o bloco do countdown no hero vira um painel festivo.

**Design aprovado — "Vitrine expandida":**
- Fundo com radial dourado suave pulsante (`@keyframes live-glow`, 3.2s)
- 4 estrelinhas ✦ nos cantos com `@keyframes live-twinkle` (opacidade + escala + rotate, delays escalonados)
- Eyebrow: `✦ Já disponível ✦` em dourado com text-shadow brilhante
- Título "Vol. 1 chegou!" com shimmer animado via `background-position` (`@keyframes live-shimmer`, gradiente dourado→laranja→dourado, 3s linear infinite)
- Subtítulo com data destacada em `var(--moon-gold)`
- Dois botões side-by-side: Spotify (verde) + Apple Music (rosa)
- Texto link "Ver todos os links ↓" linkando para `#links`

**Preferência do Jr:** festivo, com movimento, coerente com o tema noturno/mágico — NÃO usar versão minimalista tipo "Foco no CTA" (Opção C). A animação e as estrelinhas são apreciadas.

**Classes CSS envolvidas:** `.countdown-live`, `.live-spark`, `.live-spark-[1-4]`, `.live-eyebrow`, `.live-title`, `.live-sub`, `.live-cta-row`, `.live-btn`, `.live-btn-spotify`, `.live-btn-apple`, `.live-links-note`

**Animações:** `live-glow`, `live-twinkle`, `live-shimmer` — todas desativadas em `prefers-reduced-motion`.

---

## 2026-05-08 — Padrão de hover nos CTAs (aprovado)

**Preferência:** botões de ação principais (`.button-presave` no hero e `.char-listen` nos cards) ficam com pill dourada em repouso e **mudam para verde Spotify** no hover/foco. O estado de repouso dourado é o "padrão da casa"; o hover verde reforça que a ação leva ao Spotify.

---

## 2026-05-08 — Revisão de boas práticas (sessão de code review)

### Performance
- **`loading="eager"` na imagem LCP do hero.** A capa dentro do `.hero-cover-card` é visível imediatamente no desktop — nunca usar `loading="lazy"` em imagens acima da dobra.
- **`background-attachment: fixed` desabilitar no mobile.** Causa jank de scroll em iOS/Android (sem aceleração GPU). Desabilitar via `@media (max-width: 768px) { body { background-attachment: scroll; } }`.

### Acessibilidade
- **`aria-live` em contadores/timers = ruidoso.** Qualquer container que atualiza automaticamente (countdown, relógio) deve ter `aria-live="off"`. Anunciar somente o evento importante (lançamento) via `aria-live="assertive"` setado pelo JS no momento certo — não declarado no HTML estático.

### CSS — organização
- **Nunca ter dois blocos `@media` com o mesmo breakpoint.** Gera confusão de manutenção e especificidade imprevisível. Sempre mesclar em um único bloco.
- **`figure { margin: 0; }` no reset global.** Browsers adicionam `margin: 1em 40px` em `<figure>` por padrão; sem reset explícito pode quebrar layout em flexbox/grid.
- **Incluir `h4` no reset de `margin-top`.** O reset `h1, h2, h3, p, ul { margin-top: 0; }` deve incluir `h4` se o projeto usa `<h4>` (como nos cards de personagem).

### JavaScript
- **`var` → `const`/`let` em todo código novo.** `var` tem escopo de função e hoisting opaco; `const`/`let` têm escopo de bloco e comportamento previsível.
- **Data UTC explícita no countdown.** Usar `new Date("2026-05-12T03:00:00Z").getTime()` em vez de `Date.parse("...−03:00")` — UTC elimina dependência de parsing de offset pelo engine.
- **`let timer` declarado antes do primeiro `tick()`.** Com `const`, `timer` estaria na TDZ quando `tick()` é chamado, causando `ReferenceError` se o countdown já zerou. Declarar `let timer` antes e atribuir depois de `tick()`.
- **`audio.play().catch(() => {})` sempre.** `HTMLMediaElement.play()` retorna `Promise`; sem `.catch`, o browser joga `Uncaught (in promise) DOMException` no console quando autoplay é bloqueado.

---

## 2026-05-08 — Lua crescente na marca (aprovado)

**Preferência:** o `brand-mark` no header usa o símbolo `#i-moon-brand` (lua crescente SVG, `var(--moon-gold)`), coerente com o tema noturno. NÃO usar pseudo-elementos CSS abstratos.
