# Push Instructions - Fixed Authentication

The remote URL has been switched back to HTTPS. Now follow these steps:

## Step 1: Create Personal Access Token

1. Go to: https://github.com/settings/tokens
2. Click "Generate new token" → "Generate new token (classic)"
3. Name: "VitalPath Website"
4. Expiration: Choose your preference
5. Scopes: Check **"repo"** (full repository access)
6. Click "Generate token"
7. **COPY THE TOKEN** - you won't see it again!

## Step 2: Push with Token

Run this command:

```bash
cd ../vitalpath-website
git push -u origin main
```

When prompted:
- **Username**: `imransm`
- **Password**: Paste your Personal Access Token (not your GitHub password)

## Step 3: Save Credentials (Optional)

After successful push, Git will ask if you want to save credentials. You can:
- Say "yes" to save the token in your keychain
- Or say "no" and enter it each time

## Troubleshooting

If you still see `i-shaik_sfemu` error:

1. Clear all GitHub credentials:
```bash
git credential-osxkeychain erase <<EOF
host=github.com
protocol=https
EOF
```

2. Try pushing again with your token

## Alternative: Use SSH (if you prefer)

If you want to use SSH instead:

1. Check which SSH key is for GitHub:
```bash
cat ~/.ssh/id_ed25519_github.pub
```

2. Make sure this key is added to your `imransm` GitHub account:
   - Go to: https://github.com/settings/ssh/new
   - Paste the key and save

3. Switch to SSH:
```bash
cd ../vitalpath-website
git remote set-url origin git@github.com:imransm/vitalpath-website.git
git push -u origin main
```
