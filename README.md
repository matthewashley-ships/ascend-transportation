# Ascend Transportation — Website

Static website for Ascend Transportation, an authorized independent Landstar Agent.

## Hosting on GitHub Pages

1. Create a new GitHub repository named `ascend-transportation` (or your preferred name)
2. Upload all files in this folder to the repository
3. Go to **Settings → Pages**
4. Under **Source**, select `Deploy from a branch`
5. Select `main` branch, `/ (root)` folder
6. Click **Save**
7. Your site will be live at `https://yourusername.github.io/ascend-transportation/`

## Custom Domain (recommended)

To use a domain like `ascendtransportation.com`:
1. Purchase the domain (Namecheap, GoDaddy, Cloudflare Registrar)
2. In GitHub Pages settings, enter your custom domain
3. Add these DNS records at your registrar:
   - A record → 185.199.108.153
   - A record → 185.199.109.153
   - A record → 185.199.110.153
   - A record → 185.199.111.153
4. Check "Enforce HTTPS" in GitHub Pages settings

## Files

- `index.html` — Main page
- `styles.css` — All styles
- `assets/logo.png` — Ascend triangle logo
- `assets/landstar-agent.jpg` — Landstar Agent badge

## Updating Content

- Agent info: search for agent names in `index.html`
- Phone/email: update in the Team section and Contact section
- Services: edit the `.service-card` blocks in `index.html`
