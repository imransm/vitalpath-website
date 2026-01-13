# GitHub Authentication Setup

GitHub no longer accepts passwords for Git operations. You need to use one of these methods:

## Option 1: Personal Access Token (Easiest)

### Step 1: Create a Personal Access Token

1. Go to GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
   - Direct link: https://github.com/settings/tokens
2. Click "Generate new token" → "Generate new token (classic)"
3. Give it a name: "VitalPath Website"
4. Select expiration (90 days, 1 year, or no expiration)
5. Select scopes: Check **"repo"** (this gives full repository access)
6. Click "Generate token"
7. **COPY THE TOKEN IMMEDIATELY** (you won't see it again!)

### Step 2: Use Token Instead of Password

When you run `git push`, use the token as your password:

```bash
cd ../vitalpath-website
git push -u origin main
```

When prompted:
- Username: `imransm`
- Password: **Paste your Personal Access Token** (not your GitHub password)

### Step 3: Save Credentials (Optional)

To avoid entering the token every time:

```bash
# Configure Git to store credentials
git config --global credential.helper osxkeychain

# Then push (will prompt once, then remember)
git push -u origin main
```

## Option 2: SSH Keys (More Secure, One-Time Setup)

### Step 1: Check for Existing SSH Key

```bash
ls -al ~/.ssh
```

Look for `id_rsa.pub` or `id_ed25519.pub`

### Step 2: Generate SSH Key (if needed)

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Press Enter to accept default file location, then set a passphrase (optional).

### Step 3: Add SSH Key to GitHub

```bash
# Copy your public key
cat ~/.ssh/id_ed25519.pub
# Or if you have id_rsa:
cat ~/.ssh/id_rsa.pub
```

1. Copy the entire output
2. Go to GitHub → Settings → SSH and GPG keys
3. Click "New SSH key"
4. Paste your key and save

### Step 4: Change Remote URL to SSH

```bash
cd ../vitalpath-website
git remote set-url origin git@github.com:imransm/vitalpath-website.git
git push -u origin main
```

## Option 3: GitHub CLI (Alternative)

```bash
# Install GitHub CLI
brew install gh

# Authenticate
gh auth login

# Then push normally
cd ../vitalpath-website
git push -u origin main
```

## Quick Fix: Use Token Now

The fastest way right now:

1. Get a token from: https://github.com/settings/tokens
2. Run:
```bash
cd ../vitalpath-website
git push -u origin main
```
3. When prompted for password, paste your token
