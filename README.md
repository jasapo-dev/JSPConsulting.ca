# JSP Consulting — Website

**Live site:** https://jspconsulting.ca

Built with plain HTML/CSS/JS. No frameworks, no build tools — just push to GitHub and it's live.

---

## Hosting on GitHub Pages

### First-time setup
1. Create a new repository on GitHub — name it `jspconsulting` (or anything you like)
2. Upload `index.html` and this `README.md` to the repo
3. Go to **Settings → Pages**
4. Under *Source*, select **Deploy from branch → main → / (root)**
5. Hit Save — your site will be live at `https://yourusername.github.io/reponame` in ~2 minutes

### Custom domain (jspconsulting.ca)
1. In your repo, create a file called `CNAME` (no extension) containing just:
   ```
   jspconsulting.ca
   ```
2. In your domain registrar (GoDaddy, Namecheap, etc.), point your DNS:
   - Add 4 A records pointing to GitHub's IPs:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - Add a CNAME record: `www` → `yourusername.github.io`
3. Back in GitHub Pages settings, enter `jspconsulting.ca` under *Custom domain*
4. Check **Enforce HTTPS** — GitHub provides free SSL automatically ✓

---

## Updating the site

Every update is just editing `index.html` and pushing:

```bash
# Clone the repo (first time only)
git clone https://github.com/yourusername/jspconsulting.git
cd jspconsulting

# Edit index.html in any text editor (VS Code recommended)
# Then push your changes:
git add index.html
git commit -m "Update services section"
git push
```

The site updates automatically within 1–2 minutes of every push.

### Editing directly on GitHub (no Git needed)
1. Open your repo on github.com
2. Click `index.html`
3. Click the pencil icon (Edit)
4. Make changes
5. Click **Commit changes** — done. Site updates in ~2 minutes.

---

## Adding a contact form (optional upgrade)

The current form uses a `mailto:` link. For a real backend form on GitHub Pages, use one of these free services:

| Service | Free tier | Setup |
|---|---|---|
| **Formspree** | 50 submissions/mo | Add `action="https://formspree.io/f/YOUR_ID"` to form |
| **Web3Forms** | 250/mo | Similar, very simple |
| **Netlify Forms** | 100/mo | If you ever move back to Netlify |

Recommended: **Formspree** — sign up at formspree.io, create a form, replace the `handleSubmit()` JS function with a standard HTML form POST.

---

## File structure

```
/
├── index.html       ← entire site (all HTML, CSS, JS in one file)
├── CNAME            ← custom domain (create this yourself)
├── README.md        ← this file
└── banner.jpg       ← optional: add your logo/banner image
```

---

## Security checklist ✓

- [x] HTTPS enforced via GitHub Pages (free Let's Encrypt SSL, auto-renews)
- [x] No server-side code — no attack surface
- [x] No third-party scripts except Google Fonts
- [x] Contact form uses mailto (no backend to secure)
- [ ] Add CSP headers (optional — via `_headers` file if using Netlify)

---

*Managed by JSP Consulting · jspconsulting.ca*
