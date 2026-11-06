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

## Who can edit

The repo belongs to the GitHub account `dmasdmas` (Didrik). Anyone added under
**Settings → Collaborators** can edit it; collaborators can change any file
and publish, but not the repo settings, the custom domain or the collaborator
list.

**Everything pushed to `main` is live on gcdir.org within a minute or two.**
There is no review step, so preview larger changes first (see below).

### Editing in the browser

Good for text changes:

1. Open the file on github.com (for example `people.html`) and click the
   pencil icon.
2. Make the change, then **Commit changes**. Choose "Create a new branch" if
   you want someone to look at it first; otherwise it goes live directly.
3. To add a photo, open the folder (for example `assets/images/people/`) and
   use **Add file → Upload files**.

### Editing on your computer

Clone the repo, edit, preview locally (below), then push to `main`. Claude
Code works well here: open the folder and describe the change.

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
| Styles | `assets/css/site.css` |
| Header, footer, shared blocks, icons | `_includes/` |

To add a blog post, create a Markdown file in `_posts/` with this front matter:

```yaml
---
title: "Post title"
date: 2026-01-31
author: "GCDIR Team"
excerpt: "One-sentence summary shown in the blog list and at the top of the post."
---
```

## Previewing locally

Needs Ruby (for example `brew install ruby`). Then, from this folder:

```bash
bundle install
bundle exec jekyll serve
```

Open <http://localhost:4000>. The `Gemfile` is only for local previews; GitHub
Pages builds the live site with its own pinned Jekyll version.
