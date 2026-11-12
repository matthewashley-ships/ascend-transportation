# Ascend Transportation: Website

Public marketing site for **ascend-transportation.com**: Ascend Transportation, an independent
Landstar agency. Plain static HTML and CSS, no build step, hosted on GitHub Pages.

This site holds **no customer, carrier, rate, or operational data** and no secrets. The internal
sourcing tool and future broker portal live in a separate, private repository.

## Files

| Path | Purpose |
|---|---|
| `index.html` | The site (single page: hero, HVHR, services, why Ascend, quote form) |
| `styles.css` | All styles. Design tokens are at the top under `:root` |
| `404.html` | Not-found page. Uses absolute paths (`/styles.css`) so it works at any URL |
| `assets/` | Logo, Landstar Agent badge, favicons, `og-image.png` (1200×630 link preview) |
| `CNAME` | Custom domain for GitHub Pages (`ascend-transportation.com`) |
| `robots.txt`, `sitemap.xml` | Search engine hints. Update `<lastmod>` in the sitemap when content changes |

## Run it locally

```bash
python3 -m http.server 8080
```

Then open http://localhost:8080.

## Quote form

The form posts to Formspree (`action` on `#contact-form` in `index.html`). Formspree emails each
submission to the account owner and keeps a copy in the Formspree dashboard.

- Required fields: origin, destination, equipment, pickup date, first/last name, company, email.
- Spam: the hidden `_gotcha` field is a honeypot. Formspree discards submissions that fill it in.
- The subject line comes from the hidden `_subject` field.
- Validation runs in the browser (see the script at the bottom of `index.html`). Without
  JavaScript the form still posts and the browser's built-in validation applies.

To test end to end, submit the form on the live site and confirm the email arrives.

## Deployment

GitHub Pages serves the `main` branch from the repository root.

1. Repository **Settings → Pages**: Source = *Deploy from a branch*, Branch = `main`, `/ (root)`.
2. Custom domain = `ascend-transportation.com`, with **Enforce HTTPS** turned on.
3. DNS (managed at the registrar):
   - `A` records for the apex: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `www` is a `CNAME` to `matthewashley-ships.github.io`

GitHub Pages can't publish from a private repository on a free plan. Either keep this repository
public (it contains only public website content) or use a paid plan.

**Workflow:** work on a feature branch, open a pull request into `main`, and review it. Merging to
`main` publishes the site within a minute or two.

## Content rules

- Ascend is an independent agency. Don't imply Ascend is Landstar or owns Landstar assets.
- Only publish claims you can substantiate. No invented statistics, customers, or testimonials.
- Use Landstar marks only as approved under the Landstar agent branding guidelines.
