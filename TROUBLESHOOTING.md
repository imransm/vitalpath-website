# Troubleshooting GitHub Pages 404 Error

If you're getting "Page not found" (404), check these:

## Step 1: Verify Repository is Public

GitHub Pages requires the repository to be **public** (for free accounts).

1. Go to: https://github.com/imransm/vitalpath-website
2. Click **Settings** (top menu)
3. Scroll all the way down to **"Danger Zone"**
4. Check if it says "Change repository visibility"
5. If it's private, click "Change visibility" → "Make public"

## Step 2: Enable GitHub Pages

1. Go to: https://github.com/imransm/vitalpath-website/settings/pages
2. Under **"Source"**:
   - Select: **"Deploy from a branch"**
   - Branch: **`main`**
   - Folder: **`/ (root)`**
3. Click **"Save"**
4. Wait 1-2 minutes

## Step 3: Check GitHub Actions

1. Go to: https://github.com/imransm/vitalpath-website/actions
2. Look for any failed builds
3. If there are errors, check the logs

## Step 4: Verify Files Are in Root

Your files should be in the root directory:
- ✅ `privacy.html` (in root)
- ✅ `support.html` (in root)

## Step 5: Test URLs

After enabling Pages, test:
- https://imransm.github.io/vitalpath-website/privacy.html
- https://imransm.github.io/vitalpath-website/support.html

## Common Issues

### Still 404 after enabling?
- Wait 5-10 minutes (can take time to propagate)
- Clear browser cache
- Try incognito/private browsing
- Check repository is public

### Repository is private?
- Free GitHub Pages only works with public repos
- Options:
  1. Make repo public (recommended for these pages)
  2. Upgrade to GitHub Pro ($4/month) for private repo Pages

### Files not showing?
- Verify files are committed: `git log --oneline`
- Check files are in root, not in a subfolder
- Make sure you pushed: `git push`

## Quick Check Commands

```bash
# Verify files are committed
cd ../vitalpath-website
git ls-files | grep html

# Should show:
# privacy.html
# support.html

# Check if pushed
git log origin/main --oneline | head -1
```
