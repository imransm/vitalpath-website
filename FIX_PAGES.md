# Fix GitHub Pages Redirect Issue

## The Problem
GitHub Pages is returning 404, but you're seeing redirects to vitalpath.app. This is likely because:
1. GitHub Pages isn't enabled, OR
2. Custom domain is still configured in GitHub Pages settings, OR  
3. Browser cache is showing old redirects

## Solution Steps

### Step 1: Enable GitHub Pages (If Not Enabled)

1. Go to: https://github.com/imransm/vitalpath-website/settings/pages
2. Under "Source":
   - Select: **"Deploy from a branch"**
   - Branch: **`main`**
   - Folder: **`/ (root)`**
   - Click **"Save"**

### Step 2: Remove Custom Domain (Critical!)

1. Still in Settings → Pages
2. Scroll to **"Custom domain"** section
3. If you see `vitalpath.app` or any domain:
   - **Delete/clear** the domain field (make it blank)
   - **Uncheck** "Enforce HTTPS" 
   - Click **"Save"**
4. Wait 2-3 minutes

### Step 3: Clear Browser Cache Completely

**Chrome:**
- Press `Cmd + Shift + Delete` (Mac) or `Ctrl + Shift + Delete` (Windows)
- Select "Cached images and files"
- Time range: "All time"
- Click "Clear data"

**Safari:**
- Safari → Preferences → Advanced → Show Develop menu
- Develop → Empty Caches
- Or: Safari → Clear History → All History

**Or use Incognito/Private mode:**
- Chrome: `Cmd + Shift + N`
- Safari: `Cmd + Shift + N`

### Step 4: Test in Incognito Mode

Open a new incognito/private window and test:
- https://imransm.github.io/vitalpath-website/privacy.html
- https://imransm.github.io/vitalpath-website/support.html

### Step 5: Verify GitHub Pages is Built

1. Go to: https://github.com/imransm/vitalpath-website/actions
2. Look for "pages build and deployment" workflow
3. Should show green checkmark if successful

## If Still Redirecting

Try accessing directly via IP (bypasses DNS):
- Check what GitHub Pages IP resolves to
- Or wait 10-15 minutes for all caches to clear

## Quick Test Command

```bash
# Test from terminal (bypasses browser cache)
curl -I https://imransm.github.io/vitalpath-website/privacy.html

# Should return HTTP 200, not 404 or redirect
```
