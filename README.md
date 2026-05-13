# Tal3ni website

Static landing page + Privacy Policy + Terms for the Tal3ni mobile app.

**Live at:** [https://tal3ni.github.io/](https://tal3ni.github.io/)

## Files

| File | Purpose |
| --- | --- |
| `index.html` / `index-ar.html` | Landing page (EN / AR) |
| `privacy.html` / `privacy-ar.html` | Privacy Policy (EN / AR) — submit the EN URL to the stores |
| `terms.html` / `terms-ar.html` | Terms & Conditions (EN / AR) |
| `style.css` | Shared styling for all pages |

No build step, no JavaScript, no dependencies. Just plain HTML + CSS.

## URLs for App Store / Play Console submission

| Field in submission form | URL |
| --- | --- |
| Privacy Policy URL | `https://tal3ni.github.io/privacy.html` |
| Terms URL | `https://tal3ni.github.io/terms.html` |
| Support URL | `https://tal3ni.github.io/` |
| Marketing URL (optional) | `https://tal3ni.github.io/` |

## Updating content

1. Edit the relevant `.html` file (and its `-ar.html` companion if it's a legal change).
2. If editing Privacy or Terms, bump the **Effective Date** and **Last Updated** lines at the top and bottom of the page.
3. Commit and push to `main`:

   ```bash
   git add .
   git commit -m "Update privacy policy"
   git push
   ```

GitHub Pages auto-redeploys within ~1 minute.

If you change anything that affects what data the app collects or shares, **also update `d:\tal3ni\lib\legalContent.js`** in the app repo so the in-app legal modal stays in sync with the web version.

## Adding a custom domain later (optional)

If you register `tal3ni.app` (or similar) and want to use it instead of the github.io URL:

1. Repo Settings → Pages → Custom domain → enter `tal3ni.app` → Save.
2. At your domain registrar, add these DNS records:
   - Four `A` records pointing to GitHub's IPs:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - One `CNAME` record for `www` pointing to `tal3ni.github.io`
3. Wait for DNS propagation (a few minutes to a few hours).
4. Back in repo Settings → Pages, check **Enforce HTTPS** once it becomes available.

After the custom domain is live, you can update the URLs in the App Store / Play Console listings. The github.io URLs will keep working (they redirect to your custom domain).

## Local preview

Open any `.html` file directly in your browser — it works as a file, no server needed.
