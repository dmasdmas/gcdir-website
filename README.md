# gcdir.org

Website of the Global Center for Digital Influence Research (GCDIR), live at
[gcdir.org](https://gcdir.org).

## How it is hosted

- **Site:** GitHub Pages builds the `main` branch of this repo with Jekyll.
  Pushing to `main` publishes the site within a minute or two.
- **Domain:** registered at GoDaddy, which also hosts the DNS. The apex points
  at GitHub Pages (A records `185.199.108–111.153`), `www` redirects to the
  apex, and the TXT record `_github-pages-challenge-dmasdmas` verifies the
  domain for this account. HTTPS is enforced.
- **Email:** `contact@gcdir.org` runs on Microsoft 365. Leave the MX,
  `autodiscover` and SPF records in GoDaddy DNS alone when changing anything
  else.

## Where things live

| What | File |
| --- | --- |
| Site name, nav, contact email | `_config.yml` |
| Headline numbers (campaigns, brands, …) | `_data/stats.yml` |
| Research areas | `_data/areas.yml` |
| Symposium date, venue (used by the top bar, home page and /events/) | `_data/symposium.yml` |
| Top announcement bar on or off | `announcement` in `_config.yml` |
| Where the /apply/ form sends applications | `apply_form_endpoint` in `_config.yml` (empty = opens the applicant's email app; a Formspree URL = sent directly) |
| Pages | `index.html`, `research.html`, `data.html`, `people.html`, `events.html`, `apply.html`, `integrity.html`, `about.html`, `contact.html`, `blog.html` |
| Team photos | `assets/images/people/` (square JPEGs, about 320 px) |
| Blog posts | `_posts/YYYY-MM-DD-title.md` |
| Styles (colors, type and every component) | `assets/css/site.css` |
| Header, footer, shared blocks | `_includes/` |
| GCDIR mark (globe with three arcs) | `_includes/mark.svg`, `assets/images/favicon.svg` |
| Trudy, as herself (the real SVGs, never redrawn) | `assets/images/trudy/`, `_includes/trudy-note.html` |
| Social share image | `assets/images/og-card.png` (1200 x 630) |

To add a blog post, create a Markdown file in `_posts/` with this front matter:

```yaml
---
title: "Post title"
date: 2026-01-31
author: "GCDIR Team"
excerpt: "One-sentence summary shown in the blog list and at the top of the post."
---
```

## Look and voice

The site shares a family look with Trudy's own materials (the Smart Girls
pages, the Equip deck, the personality and values tests): cream paper, deep
green bands, lilac, periwinkle and orange accents, speech-bubble shapes and
sparkles. Display type is Fraunces with its soft setting, which stands in for
Recoleta; body text is DM Sans and labels are DM Mono. The colors are listed at
the top of `assets/css/site.css`.

The copy follows the Trudy tone of voice: short, dry, warm. Playful at the
door, plain at the table. No em dashes, no exclamation marks, no hype words
(authentic, unlock, leverage, game-changer and friends). Policies and
disclosures stay plain. Trudy herself appears only where she discloses the
relationship ("We share humans, and I give them data") and on the 404 page.

Each inner page can set two extra front-matter fields:

```yaml
bubble: Who believes whom?   # short line in the speech bubble beside the title
accent: peri                 # bubble color: lilac, peri, orange, lime or teal
```

## Previewing locally

Needs Ruby (for example `brew install ruby`). Then, from this folder:

```bash
bundle install
bundle exec jekyll serve
```

Open <http://localhost:4000>. The `Gemfile` is only for local previews; GitHub
Pages builds the live site with its own pinned Jekyll version.
