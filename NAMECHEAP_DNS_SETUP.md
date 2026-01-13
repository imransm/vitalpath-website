# Namecheap DNS Setup for vitalpath.app

Your domain is registered with Namecheap. Here's how to configure it for GitHub Pages:

## Step 1: Log into Namecheap

1. Go to: https://www.namecheap.com/myaccount/login/
2. Log in with your Namecheap account

## Step 2: Access DNS Settings

1. Go to: https://www.namecheap.com/domains/list/
2. Find `vitalpath.app` in your domain list
3. Click "Manage" next to the domain
4. Click on the "Advanced DNS" tab

## Step 3: Configure DNS Records

### Remove Existing Records (if any)

Delete any existing A records or CNAME records for the root domain (@).

### Add CNAME Record

1. Click "Add New Record"
2. Select **CNAME Record**
3. Configure:
   - **Host**: `@` (or leave blank - this means root domain)
   - **Value**: `imransm.github.io`
   - **TTL**: Automatic (or 3600)
4. Click the checkmark to save

**Note**: If Namecheap doesn't allow CNAME on root domain (@), use A Records instead (see below).

### Alternative: Use A Records (if CNAME not allowed)

If you can't use CNAME on @, add these 4 A Records:

1. **Type**: A Record
   - **Host**: `@`
   - **Value**: `185.199.108.153`
   - **TTL**: Automatic

2. **Type**: A Record
   - **Host**: `@`
   - **Value**: `185.199.109.153`
   - **TTL**: Automatic

3. **Type**: A Record
   - **Host**: `@`
   - **Value**: `185.199.110.153`
   - **TTL**: Automatic

4. **Type**: A Record
   - **Host**: `@`
   - **Value**: `185.199.111.153`
   - **TTL**: Automatic

## Step 4: Save Changes

Click "Save All Changes" (green button at the bottom)

## Step 5: Enable Custom Domain in GitHub

1. Go to: https://github.com/imransm/vitalpath-website/settings/pages
2. Under "Custom domain", enter: `vitalpath.app`
3. Check "Enforce HTTPS" (will be available after DNS propagates)
4. Click "Save"

## Step 6: Wait for DNS Propagation

- Usually takes 10-30 minutes
- Can take up to 48 hours (rare)
- Check status: https://www.whatsmydns.net/#A/vitalpath.app

## Step 7: Verify

Once DNS propagates (you'll see GitHub's IPs in the DNS checker):

1. Visit: https://vitalpath.app/privacy.html
2. Visit: https://vitalpath.app/support.html
3. Both should load correctly
4. GitHub will automatically get an SSL certificate (may take a few minutes)

## Troubleshooting

### Domain not resolving?
- Wait longer (up to 48 hours)
- Verify DNS records are saved correctly in Namecheap
- Check that CNAME file exists in your GitHub repo (it does!)

### HTTPS not working?
- Wait 10-30 minutes after DNS propagates
- GitHub needs time to issue SSL certificate
- Check "Enforce HTTPS" is enabled in GitHub Pages settings

### Still showing placeholder page?
- DNS hasn't propagated yet
- Wait and check DNS propagation status
- Verify DNS records point to `imransm.github.io`

## Current Status

✅ CNAME file created in GitHub repository
✅ Domain registered with Namecheap
⏳ Next: Configure DNS records in Namecheap
⏳ Then: Enable custom domain in GitHub Pages settings
