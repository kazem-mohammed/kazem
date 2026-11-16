# Kazem Salah — Portfolio

A bilingual (English / Arabic) professional portfolio built from the CV and the real,
published client work. Static HTML + CSS + vanilla JavaScript — no build step, no
framework, no tracking.

**Live URLs in this file are all real and verifiable.** Every project card links to a
site that is published, and the CV files are the original PDFs, unchanged.

---

## Primary conversion goal

**Job seeker / professional hiring.** The site is built to make one thing easy: understand
what Kazem can do, then reach him.

- Primary CTA — **Hire Me** (hero + header + mobile menu)
- Secondary CTA — **View My Work**
- Tertiary CTA — **Download CV** (opens a preview with a choice of two original files)
- Contact — WhatsApp, email, phone, LinkedIn, GitHub and the other profiles

Deliberately **not** included, because there is no real content for them: fake testimonials,
fake pricing, invented availability status, invented performance figures, or a contact form
that pretends to send messages when no backend exists.

---

## What's inside

| Area | Implementation |
|---|---|
| **Theme engine** | Dark / Light / System. Dark is the default — it carries the amber + teal identity best. Choice is stored in `localStorage` (`ks-theme`) and applied before first paint by an inline script, so there is no flash of the wrong theme. Every colour is a CSS variable, so the whole site re-themes in one step. |
| **Custom cursor** | A minimal tech ring + dot that scales over interactive elements. Desktop only — it is disabled on coarse pointers and under `prefers-reduced-motion`, and it never intercepts clicks. |
| **Typography** | `Space Grotesk` (display) + `Plus Jakarta Sans` (body) + `IBM Plex Sans Arabic` (Arabic). All sizes use `clamp()` for fluid scaling; the Arabic subset only downloads when Arabic is selected. |
| **Project viewer** | Accessible modal with role, year, location, full description, feature list, gallery, tools, live-site link and source link. |
| **Gallery + lightbox** | Full-screen viewer with next/previous buttons, arrow-key navigation, swipe on touch, counter and caption. |
| **Filters** | Built only from the real projects: Restaurants (3), Cafés (2), Desserts & Ice Cream (1), Digital Menus (6), Featured (3). |
| **CV download** | Two original PDFs with an in-page preview and a `download` attribute. Nothing is regenerated. |
| **Contact** | Copy-to-clipboard for email and phone, one-tap WhatsApp / LinkedIn / GitHub, and a quick-message composer that opens the visitor's own email client (or WhatsApp) with the text pre-filled. It does **not** pretend to submit anything. |
| **Language** | Full Arabic/English switch with `dir` flipping, `localStorage` persistence and a `?lang=` URL parameter so a link can carry a language. Company names, certificates and technologies are never translated. |
| **Navigation** | Sticky header with a sliding active-section indicator, smooth scrolling, mobile sheet menu, and a bottom bar on small screens. |
| **Visitor tools** | Scroll progress, back-to-top, share via the Web Share API with a copy-link fallback, and a reading-progress rule. |
| **Accessibility** | Semantic landmarks, skip link, focus-visible rings, focus trapping in dialogs, ARIA labels, alt text on every image, live regions, touch-sized controls, and a full `prefers-reduced-motion` path. |

---

## Featured projects rule

Featured is not arbitrary. A project is marked featured when it has **five or more real
gallery assets** *and* complete metadata — those are Beetle (7 assets), Galal Coffee (5)
and Al-Saidi Ice Cream (5). The remaining three still appear in the grid with their own
detail view.

---

## Files

```
index.html                     single page, semantic markup
assets/css/styles.css          design tokens + all components
assets/js/data.js              bilingual dictionary, project data, skill graph, stack
assets/js/app.js               theme, i18n, cursor, viewer, lightbox, filters, a11y
assets/img/profile/            portraits
assets/img/projects/           project covers
assets/img/projects/gallery/   gallery photography from the real sites
assets/img/favicon.svg
Kazem-Salah-CV.pdf             original CV (unchanged)
Kazem-Salah-CV-Compact.pdf     original second CV layout (unchanged, renamed for clarity)
site.webmanifest, robots.txt, sitemap.xml
```

---

## Run locally

```bash
python -m http.server 8000
# then open http://localhost:8000
```

A local server is recommended over opening `index.html` directly — the CV preview uses an
`<iframe>` and some browsers restrict that on `file://`.

---

## Publish on GitHub Pages

1. Create a repository.
2. Push every file and folder in this package to the root of the default branch.
3. **Settings → Pages → Deploy from a branch → `main` / `/ (root)` → Save.**
4. Update the `canonical`, `og:url` and `sitemap.xml` values in `index.html` and
   `sitemap.xml` to the final domain.

No server, no build pipeline, no dependencies.

---

## Before publishing — checklist

- [ ] Confirm the CVs and the phone number are intended for public display.
- [ ] Replace the `https://kazem-salah.github.io/` URLs with the final domain.
- [ ] Re-check that every project link still resolves (the six client sites are real and
      live — but clients can take a site down).
- [ ] Add campaign results, client quotes or new project media **only when they exist**.
- [ ] Update the `og:image` if you want a different share preview.

The portfolio deliberately makes no claim about advertising performance figures, client
testimonials, availability, or pricing — because none of those are documented in the source
material.

---

## Content source of truth

Everything on the site comes from two places, and nothing else:

1. `Kazem-Salah-CV.pdf` and `DOC-20260509-WA0032.pdf` — role, objective, experience,
   education, training, skills, languages, hobbies, contact details.
2. The six published client websites — project names, categories, locations, features,
   technologies and the real photography used in the galleries.

Skills are grouped and labelled by how they are used. There are **no skill percentages,
progress bars or ratings** anywhere on the site.
