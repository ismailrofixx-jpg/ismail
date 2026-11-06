MarÃ© restaurant: styles
   Palette: sea salt, tide (teal), deep (near-black teal), brass accent
   Type: Instrument Serif (display), Hanken Grotesk (text)
   ========================================================================== */

:root {
  --salt: #edf0ea;
  --salt-2: #e1e7e1;
  --mist: #c9d6d0;
  --tide: #0e3b3f;
  --tide-2: #15494d;
  --deep: #072224;
  --ink: #12231f;
  --brass: #b9924f;
  --brass-2: #cfa862;
  --muted: #5b6f6a;

  --font-display: "Instrument Serif", "Iowan Old Style", Georgia, serif;
  --font-body: "Hanken Grotesk", system-ui, -apple-system, "Segoe UI", sans-serif;

  --header-h: 76px;
  --container: 1180px;
  --radius: 6px;
  --ease: cubic-bezier(.2, .7, .2, 1);
}

*, *::before, *::after { box-sizing: border-box; }

html { scroll-behavior: smooth; scroll-padding-top: calc(var(--header-h) + 12px); }

body {
  margin: 0;
  font-family: var(--font-body);
  font-size: 1.0625rem;
  line-height: 1.65;
  color: var(--ink);
  background: var(--salt);
  -webkit-font-smoothing: antialiased;
  text-rendering: optimizeLegibility;
}

img, svg { display: block; max-width: 100%; }
img { height: auto; }
a { color: inherit; }
ul { margin: 0; padding: 0; list-style: none; }
h1, h2, h3, p, dl, dd, figure, address { margin: 0; }
address { font-style: normal; }
button { font: inherit; color: inherit; cursor: pointer; }

:focus-visible { outline: 2px solid var(--brass); outline-offset: 3px; }

.container { width: min(100% - 2.5rem, var(--container)); margin-inline: auto; }

.skip-link {
  position: absolute; left: 1rem; top: -4rem; z-index: 200;
  background: var(--brass); color: var(--deep); padding: .6rem 1rem; border-radius: var(--radius);
}
.skip-link:focus { top: 1rem; }

/* ---------- Type ---------- */
h1, h2, h3 { font-family: var(--font-display); font-weight: 400; letter-spacing: -.01em; }
h2 { font-size: clamp(2.3rem, 4.6vw, 3.6rem); line-height: 1.05; }
h3 { font-size: 1.5rem; line-height: 1.2; }

/* ---------- Buttons ---------- */
.btn {
  display: inline-flex; align-items: center; justify-content: center;
  padding: .85rem 1.6rem; border-radius: 999px; border: 1px solid transparent;
  font-weight: 500; font-size: .98rem; letter-spacing: .01em; text-decoration: none;
  transition: background .25s var(--ease), color .25s var(--ease), border-color .25s var(--ease), transform .25s var(--ease);
}
.btn:active { transform: translateY(1px); }
.btn-brass { background: var(--brass); color: var(--deep); }
.btn-brass:hover { background: var(--brass-2); }
.btn-deep { background: var(--deep); color: var(--salt); }
.btn-deep:hover { background: var(--tide); }
.btn-ghost { border-color: rgba(237, 240, 234, .55); color: var(--salt); }
.btn-ghost:hover { background: rgba(237, 240, 234, .12); border-color: var(--salt); }
.btn-block { width: 100%; }

/* ---------- Header ---------- */
.site-header {
  position: fixed; inset: 0 0 auto 0; z-index: 100; height: var(--header-h);
  color: var(--salt);
  transition: background .35s var(--ease), box-shadow .35s var(--ease);
}
.site-header.is-scrolled { background: rgba(7, 34, 36, .94); backdrop-filter: blur(10px); box-shadow: 0 1px 0 rgba(237, 240, 234, .08); }
.header-inner {
  height: 100%; width: min(100% - 2.5rem, var(--container)); margin-inline: auto;
  display: flex; align-items: center; justify-content: space-between; gap: 2rem;
}
.brand { display: inline-flex; align-items: center; gap: .7rem; text-decoration: none; }
.brand-mark { width: 38px; height: 38px; color: var(--brass-2); }
.brand-name { font-family: var(--font-display); font-size: 2rem; line-height: 1; letter-spacing: .01em; }

.main-nav { display: flex; align-items: center; gap: 2.2rem; }
.main-nav ul { display: flex; gap: 2rem; }
.main-nav li a {
  text-decoration: none; font-size: .98rem; padding: .4rem 0; position: relative;
}
.main-nav li a::after {
  content: ""; position: absolute; left: 0; bottom: 0; height: 1px; width: 100%;
  background: var(--brass-2); transform: scaleX(0); transform-origin: left; transition: transform .3s var(--ease);
}
.main-nav li a:hover::after { transform: scaleX(1); }
.nav-cta { padding: .65rem 1.3rem; }

.nav-toggle {
  display: none; width: 44px; height: 44px; background: none; border: 0; position: relative; z-index: 120;
}
.nav-toggle span {
  position: absolute; left: 11px; right: 11px; height: 1.5px; background: currentColor;
  transition: transform .3s var(--ease), top .3s var(--ease);
}
.nav-toggle span:first-child { top: 18px; }
.nav-toggle span:last-child { top: 26px; }
.nav-toggle[aria-expanded="true"] span:first-child { top: 22px; transform: rotate(45deg); }
.nav-toggle[aria-expanded="true"] span:last-child { top: 22px; transform: rotate(-45deg); }

/* ---------- Hero ---------- */
.hero {
  position: relative; min-height: 100vh; min-height: 100svh;
  display: flex; flex-direction: column; justify-content: flex-end;
  color: var(--salt); background: var(--deep); overflow: hidden;
  padding: calc(var(--header-h) + 3rem) 0 0;
}
.hero-media { position: absolute; inset: 0; }
.hero-media img { width: 100%; height: 100%; object-fit: cover; }
.hero-media::after {
  content: ""; position: absolute; inset: 0;
  background:
    linear-gradient(180deg, rgba(7, 34, 36, .55) 0%, rgba(7, 34, 36, .25) 35%, rgba(7, 34, 36, .88) 100%),
    linear-gradient(90deg, rgba(7, 34, 36, .65) 0%, rgba(7, 34, 36, 0) 65%);
}
.hero-inner, .hero-hours { position: relative; width: min(100% - 2.5rem, var(--container)); margin-inline: auto; }
.hero-inner { padding-bottom: 3.5rem; max-width: var(--container); }
.hero-kicker { font-size: 1.05rem; color: var(--brass-2); margin-bottom: 1.1rem; }
.hero h1 {
  font-size: clamp(3.4rem, 10vw, 9rem); line-height: .94; letter-spacing: -.025em;
  max-width: 12ch;
}
.hero-actions { display: flex; flex-wrap: wrap; gap: .9rem; margin-top: 2.4rem; }

.hero-hours {
  display: flex; gap: clamp(1.5rem, 5vw, 4rem); flex-wrap: wrap;
  padding: 1.4rem 0 2rem; border-top: 1px solid rgba(237, 240, 234, .22);
}
.hero-hours dt { font-size: .85rem; color: var(--mist); }
.hero-hours dd { font-family: var(--font-display); font-size: 1.5rem; line-height: 1.2; }

/* One orchestrated page-load moment: the hero text rises in once */
@media (prefers-reduced-motion: no-preference) {
  .hero-kicker, .hero h1, .hero-actions, .hero-hours { animation: rise 1s var(--ease) both; }
  .hero h1 { animation-delay: .12s; }
  .hero-actions { animation-delay: .3s; }
  .hero-hours { animation-delay: .45s; }
  .hero-media img { animation: settle 2.4s var(--ease) both; }
}
@keyframes rise { from { opacity: 0; transform: translateY(28px); } to { opacity: 1; transform: none; } }
@keyframes settle { from { transform: scale(1.06); } to { transform: scale(1); } }

/* ---------- Sections ---------- */
.section { padding: clamp(4.5rem, 9vw, 8rem) 0; }
.section-head { max-width: 640px; margin-bottom: 3rem; }
.section-head p { margin-top: 1rem; color: var(--muted); }
.section-head-light p { color: var(--mist); }

/* ---------- Menu ---------- */
.menu-tabs {
  display: flex; gap: .4rem; flex-wrap: wrap; margin-bottom: 2.5rem;
  border-bottom: 1px solid var(--mist);
}
.menu-tab {
  background: none; border: 0; padding: .9rem 1.3rem; font-family: var(--font-display);
  font-size: 1.6rem; color: var(--muted); position: relative; transition: color .25s var(--ease);
}
.menu-tab::after {
  content: ""; position: absolute; left: 0; right: 0; bottom: -1px; height: 2px;
  background: var(--brass); transform: scaleX(0); transition: transform .3s var(--ease);
}
.menu-tab:hover { color: var(--tide); }
.menu-tab[aria-selected="true"] { color: var(--deep); }
.menu-tab[aria-selected="true"]::after { transform: scaleX(1); }

.menu-panel { display: grid; grid-template-columns: repeat(2, 1fr); gap: 2.2rem 3.5rem; }
.menu-item { display: grid; grid-template-columns: 112px 1fr; gap: 1.2rem; align-items: start; }
.menu-item .thumb {
  width: 112px; height: 112px; border-radius: var(--radius); overflow: hidden;
  background: linear-gradient(135deg, var(--tide), var(--deep));
}
.menu-item .thumb img { width: 100%; height: 100%; object-fit: cover; transition: transform .6s var(--ease); }
.menu-item:hover .thumb img { transform: scale(1.06); }
.menu-item-head { display: flex; align-items: baseline; gap: .6rem; }
.menu-item-head h3 { white-space: normal; }
.menu-item-head .leader { flex: 1; border-bottom: 1px dotted var(--muted); min-width: 1rem; transform: translateY(-.25rem); }
.menu-item-head .price { font-family: var(--font-display); font-size: 1.5rem; color: var(--tide); }
.menu-item p { margin-top: .3rem; font-size: .97rem; color: var(--muted); line-height: 1.55; }
.menu-item .tag { display: inline-block; margin-top: .5rem; font-size: .8rem; color: var(--brass); font-weight: 500; }
.menu-note { margin-top: 3rem; font-size: .9rem; color: var(--muted); }

@media (prefers-reduced-motion: no-preference) {
  .menu-panel.is-changing { animation: fade .45s var(--ease); }
}
@keyframes fade { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: none; } }

/* ---------- About ---------- */
.about { background: var(--salt-2); }
.about-grid { display: grid; grid-template-columns: 1.05fr 1fr; gap: clamp(2.5rem, 7vw, 6rem); align-items: center; }
.about-media { position: relative; padding-bottom: 4rem; }
.photo { overflow: hidden; border-radius: var(--radius); background: linear-gradient(135deg, var(--tide), var(--deep)); }
.photo img { width: 100%; height: 100%; object-fit: cover; }
.photo-tall { aspect-ratio: 4 / 5; width: 82%; }
.photo-small {
  position: absolute; right: 0; bottom: 0; width: 52%; aspect-ratio: 1; border: 8px solid var(--salt-2);
}
.about-copy h2 { margin-bottom: 1.5rem; }
.about-copy p { max-width: 52ch; color: #2b3d39; }
.about-copy p + p { margin-top: 1rem; }
.facts { display: flex; gap: 2.2rem; flex-wrap: wrap; margin: 2.2rem 0 2.4rem; padding-top: 1.8rem; border-top: 1px solid var(--mist); }
.facts li { display: flex; flex-direction: column; max-width: 11rem; }
.facts strong { font-family: var(--font-display); font-weight: 400; font-size: 2.8rem; line-height: 1; color: var(--tide); }
.facts span { font-size: .92rem; color: var(--muted); margin-top: .35rem; }

/* ---------- Gallery ---------- */
.gallery { background: var(--deep); color: var(--salt); }
.gallery-grid {
  display: grid; grid-template-columns: repeat(4, 1fr); grid-auto-rows: 240px; gap: 14px;
}
.g-item {
  position: relative; padding: 0; border: 0; overflow: hidden; border-radius: var(--radius);
  background: linear-gradient(135deg, var(--tide-2), var(--tide));
}
.g-wide { grid-column: span 2; }
.g-tall { grid-row: span 2; }
.g-item img { width: 100%; height: 100%; object-fit: cover; transition: transform .8s var(--ease), filter .4s var(--ease); }
.g-item:hover img { transform: scale(1.05); filter: brightness(1.08); }

/* ---------- Reservation band ---------- */
.band { background: var(--tide); color: var(--salt); padding: clamp(3rem, 6vw, 4.5rem) 0; }
.band-inner { display: flex; align-items: center; justify-content: space-between; gap: 2rem; flex-wrap: wrap; }
.band h2 { font-size: clamp(1.9rem, 3.6vw, 2.8rem); max-width: 22ch; }

/* ---------- Contact ---------- */
.contact-grid { display: grid; grid-template-columns: 1fr 1.1fr; gap: clamp(2rem, 6vw, 5rem); align-items: stretch; }
.contact-info h2 { margin-bottom: 2rem; }
.contact-info address { display: grid; gap: 1.6rem; margin-bottom: 2.2rem; }
.contact-info h3 { font-size: 1.25rem; color: var(--tide); margin-bottom: .3rem; }
.contact-info a:not(.btn) { text-decoration-color: var(--brass); text-underline-offset: 3px; }
.contact-info a:not(.btn):hover { color: var(--tide); }
.hours { border-collapse: collapse; font-size: .98rem; }
.hours th { text-align: left; font-weight: 500; padding: .2rem 1.5rem .2rem 0; white-space: nowrap; }
.hours td { color: var(--muted); }
.map-wrap { min-height: 420px; border-radius: var(--radius); overflow: hidden; background: var(--salt-2); border: 1px solid var(--mist); }
.map-wrap iframe { width: 100%; height: 100%; min-height: 420px; border: 0; filter: saturate(.75) contrast(1.02); }

/* ---------- Footer ---------- */
.site-footer { background: var(--deep); color: var(--salt); padding: 2.5rem 0; }
.footer-inner { display: flex; align-items: center; justify-content: space-between; gap: 1.5rem; flex-wrap: wrap; }
.footer-links { display: flex; gap: 1.6rem; flex-wrap: wrap; }
.footer-links a { text-decoration: none; font-size: .95rem; color: var(--mist); }
.footer-links a:hover { color: var(--brass-2); }
.copyright { font-size: .88rem; color: var(--mist); }

/* ---------- Dialogs ---------- */
dialog { padding: 0; border: 0; color: var(--ink); }
dialog::backdrop { background: rgba(7, 34, 36, .72); backdrop-filter: blur(4px); }

.modal { width: min(100% - 1.5rem, 640px); max-height: calc(100vh - 2rem); background: var(--salt); border-radius: 10px; overflow: auto; }
.modal-card { position: relative; padding: clamp(1.6rem, 4vw, 2.6rem); }
.modal-close {
  position: absolute; top: .8rem; right: .9rem; width: 40px; height: 40px; z-index: 2;
  background: none; border: 0; font-size: 2rem; line-height: 1; color: var(--muted); border-radius: 50%;
}
.modal-close:hover { color: var(--deep); background: rgba(14, 59, 63, .08); }
.modal h2 { font-size: clamp(2rem, 5vw, 2.6rem); }
.modal-lead { margin: .5rem 0 1.6rem; color: var(--muted); }

.field { display: flex; flex-direction: column; gap: .35rem; margin-bottom: 1rem; }
.field-row { display: grid; grid-template-columns: 1fr 1fr; gap: 0 1rem; }
.field-row-3 { grid-template-columns: 1.2fr 1fr .9fr; }
label { font-size: .9rem; font-weight: 500; }
.optional { font-weight: 400; color: var(--muted); }
input, select, textarea {
  width: 100%; font: inherit; color: var(--ink); background: #fff;
  border: 1px solid var(--mist); border-radius: var(--radius); padding: .75rem .85rem;
  transition: border-color .2s var(--ease), box-shadow .2s var(--ease);
}
input:focus, select:focus, textarea:focus { outline: none; border-color: var(--tide); box-shadow: 0 0 0 3px rgba(185, 146, 79, .35); }
textarea { resize: vertical; min-height: 84px; }
.field.has-error input, .field.has-error select { border-color: #a63a2b; }
.error { min-height: 1.1em; font-size: .82rem; color: #a63a2b; }
.form-hint { margin-top: .9rem; font-size: .88rem; color: var(--muted); text-align: center; }

.confirm { text-align: center; padding: 1.5rem 0 .5rem; }
.confirm[hidden] { display: none; }
.confirm-icon { width: 64px; height: 64px; margin: 0 auto 1rem; color: var(--brass); }
.confirm p { margin: .8rem auto 1.8rem; max-width: 40ch; color: var(--muted); }

.lightbox {
  width: 100vw; max-width: 100vw; height: 100vh; max-height: 100vh; background: transparent;
  align-items: center; justify-content: center;
}
.lightbox[open] { display: flex; }
.lightbox img { max-width: min(92vw, 1400px); max-height: 86vh; border-radius: var(--radius); object-fit: contain; }
.lightbox .modal-close { color: var(--salt); top: 1.2rem; right: 1.2rem; font-size: 2.4rem; }
.lightbox .modal-close:hover { color: var(--brass-2); background: rgba(255, 255, 255, .1); }
.lb-nav {
  position: absolute; top: 50%; transform: translateY(-50%); width: 52px; height: 52px; border-radius: 50%;
  background: rgba(237, 240, 234, .12); border: 0; color: var(--salt); font-size: 2.2rem; line-height: 1;
  display: grid; place-items: center; padding-bottom: 4px;
}
.lb-nav:hover { background: rgba(237, 240, 234, .26); }
.lb-prev { left: 1.2rem; }
.lb-next { right: 1.2rem; }

/* ---------- Fallback when a photo fails to load ---------- */
img.img-failed { visibility: hidden; }

/* ==========================================================================
   Responsive
   ========================================================================== */

/* Large desktop / external displays */
@media (min-width: 1500px) {
  :root { --container: 1320px; }
  body { font-size: 1.125rem; }
}

/* Laptops and below (MacBook 13" ~1280px is fine at default) */
@media (max-width: 1100px) {
  .menu-panel { gap: 2rem 2.5rem; }
  .gallery-grid { grid-auto-rows: 210px; }
}

/* Tablet */
@media (max-width: 900px) {
  .about-grid, .contact-grid { grid-template-columns: 1fr; }
  .about-media { max-width: 520px; }
  .menu-panel { grid-template-columns: 1fr; }
  .gallery-grid { grid-template-columns: repeat(2, 1fr); grid-auto-rows: 200px; }
  .g-wide { grid-column: span 2; }

  .nav-toggle { display: block; }
  .main-nav {
    position: fixed; inset: 0; background: var(--deep); flex-direction: column; justify-content: center;
    gap: 2.4rem; opacity: 0; visibility: hidden; transition: opacity .35s var(--ease), visibility .35s;
  }
  .main-nav.is-open { opacity: 1; visibility: visible; }
  .main-nav ul { flex-direction: column; align-items: center; gap: 1.4rem; }
  .main-nav li a { font-family: var(--font-display); font-size: 2.6rem; }
  .nav-cta { font-size: 1.05rem; padding: .9rem 1.8rem; }
}

/* Mobile */
@media (max-width: 600px) {
  :root { --header-h: 68px; }
  body { font-size: 1rem; }
  .container, .header-inner, .hero-inner, .hero-hours { width: min(100% - 2rem, var(--container)); }
  .hero { padding-top: calc(var(--header-h) + 2rem); }
  .hero-inner { padding-bottom: 2.5rem; }
  .hero-actions .btn { flex: 1 1 100%; }
  .hero-hours { gap: 1rem 2rem; padding-bottom: 1.5rem; }
  .hero-hours dd { font-size: 1.25rem; }

  .menu-tabs { flex-wrap: nowrap; overflow-x: auto; scrollbar-width: none; margin-inline: -1rem; padding-inline: 1rem; }
  .menu-tabs::-webkit-scrollbar { display: none; }
  .menu-tab { padding: .8rem 1rem; font-size: 1.4rem; flex-shrink: 0; }
  .menu-item { grid-template-columns: 88px 1fr; gap: 1rem; }
  .menu-item .thumb { width: 88px; height: 88px; }

  .about-media { padding-bottom: 3rem; }
  .facts { gap: 1.5rem; }

  .gallery-grid { grid-template-columns: 1fr 1fr; grid-auto-rows: 150px; gap: 10px; }
  .g-wide { grid-column: span 2; }
  .g-tall { grid-row: span 2; }

  .band-inner .btn { width: 100%; }
  .map-wrap, .map-wrap iframe { min-height: 320px; }
  .footer-inner { flex-direction: column; align-items: flex-start; }

  .field-row, .field-row-3 { grid-template-columns: 1fr; }
  .lb-nav { width: 44px; height: 44px; }
  .lb-prev { left: .4rem; }
  .lb-next { right: .4rem; }
}

@media (prefers-reduced-motion: reduce) {
  html { scroll-behavior: auto; }
  *, *::before, *::after { transition-duration: .01ms !important; animation: none !important; }
}
