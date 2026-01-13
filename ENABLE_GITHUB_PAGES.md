# Enable GitHub Pages

Your pages are returning 404, which means GitHub Pages needs to be enabled.

## Quick Steps

1. **Go to GitHub Pages Settings:**
   - Visit: https://github.com/imransm/vitalpath-website/settings/pages

2. **Enable GitHub Pages:**
   - Under "Source", select: **"Deploy from a branch"**
   - Branch: **`main`**
   - Folder: **`/ (root)`**
   - Click **"Save"**

3. **Wait 1-2 minutes** for GitHub to build your site

4. **Verify:**
   - Visit: https://imransm.github.io/vitalpath-website/privacy.html
   - Visit: https://imransm.github.io/vitalpath-website/support.html
   - Both should load correctly

## Your App Store URLs

Once GitHub Pages is enabled, use these URLs in App Store Connect:

- **Privacy Policy URL**: `https://imransm.github.io/vitalpath-website/privacy.html`
- **Support URL**: `https://imransm.github.io/vitalpath-website/support.html`

## Troubleshooting

If pages still show 404 after enabling:
- Wait a few more minutes (can take up to 10 minutes)
- Check repository is **public** (required for free GitHub Pages)
- Verify files exist: `privacy.html` and `support.html` in root directory
- Check GitHub Actions tab for any build errors
