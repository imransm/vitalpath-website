# Custom Domain Setup for vitalpath.app

## Step 1: DNS Configuration

You need to configure DNS records at your domain registrar (where you bought vitalpath.app).

### Option A: CNAME Record (Recommended - Easier)

1. Go to your domain registrar's DNS settings
2. Add a new CNAME record:
   - **Type**: CNAME
   - **Name/Host**: `@` or leave blank (for root domain)
   - **Value/Target**: `imransm.github.io`
   - **TTL**: 3600 (or default)

**Note**: Some registrars don't allow CNAME on root domain (@). If that's the case, use Option B.

### Option B: A Records (If CNAME not allowed on root)

Add these A records (all four are required):

1. **Type**: A
   - **Name**: `@` or leave blank
   - **Value**: `185.199.108.153`
   - **TTL**: 3600

2. **Type**: A
   - **Name**: `@` or leave blank
   - **Value**: `185.199.109.153`
   - **TTL**: 3600

3. **Type**: A
   - **Name**: `@` or leave blank
   - **Value**: `185.199.110.153`
   - **TTL**: 3600

4. **Type**: A
   - **Name**: `@` or leave blank
   - **Value**: `185.199.111.153`
   - **TTL**: 3600

### Option C: Use www Subdomain (Alternative)

If you prefer `www.vitalpath.app`:

1. Add CNAME record:
   - **Name**: `www`
   - **Value**: `imransm.github.io`

2. Update CNAME file to: `www.vitalpath.app`

## Step 2: Enable Custom Domain in GitHub

1. Go to: https://github.com/imransm/vitalpath-website/settings/pages
2. Under "Custom domain", enter: `vitalpath.app`
3. Check "Enforce HTTPS" (will be available after DNS propagates)
4. Click "Save"

## Step 3: Wait for DNS Propagation

- DNS changes can take 5 minutes to 48 hours
- Usually takes 10-30 minutes
- Check propagation: https://www.whatsmydns.net/#A/vitalpath.app

## Step 4: Verify Setup

Once DNS propagates:

1. Visit: https://vitalpath.app/privacy.html
2. Visit: https://vitalpath.app/support.html
3. Both should load correctly
4. GitHub will automatically get an SSL certificate (may take a few minutes)

## Step 5: Update App Store Connect URLs

Once verified, update your App Store Connect URLs:

- **Privacy Policy URL**: `https://vitalpath.app/privacy.html`
- **Support URL**: `https://vitalpath.app/support.html`

## Troubleshooting

### Domain not resolving?
- Wait longer (up to 48 hours)
- Check DNS records are correct
- Verify CNAME file is in repository root

### HTTPS not working?
- Wait 10-30 minutes after DNS propagates
- GitHub needs time to issue SSL certificate
- Check "Enforce HTTPS" is enabled in GitHub Pages settings

### Still showing GitHub Pages URL?
- Clear browser cache
- Try incognito/private browsing
- Verify DNS records are correct

## Current Status

✅ CNAME file created and pushed to repository
⏳ Next: Configure DNS at your domain registrar
⏳ Then: Enable custom domain in GitHub Pages settings
