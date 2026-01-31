# Complete Setup Guide: Netlify + Sveltia CMS + Custom Domain

This guide will walk you through migrating from GitHub Pages to Netlify, setting up Sveltia CMS, and connecting your Namecheap domain.

## ✅ What's Already Done

All configuration files have been created and pushed to your GitHub repository:
- ✅ `netlify.toml` - Netlify build configuration
- ✅ `admin/config.yml` - Sveltia CMS configuration
- ✅ `admin/index.html` - CMS admin interface
- ✅ `_config.yml` - Updated for ssthistlegorm.com

---

## Step 1: Deploy to Netlify

### 1.1 Create Netlify Account
1. Go to https://app.netlify.com/signup
2. Sign up with your GitHub account (recommended for easier integration)

### 1.2 Create New Site from GitHub
1. Click **"Add new site"** → **"Import an existing project"**
2. Select **"Deploy with GitHub"**
3. Authorize Netlify to access your GitHub repositories
4. Select the repository: **`lolandese1/ssthistlegorm.github.io`**

### 1.3 Configure Build Settings
The build settings should be auto-detected from `netlify.toml`, but verify:
- **Branch to deploy:** `master`
- **Build command:** `bundle exec jekyll build`
- **Publish directory:** `_site`
- **Environment variables:** (will be set automatically from netlify.toml)

5. Click **"Deploy site"**

### 1.4 Wait for Deployment
- Netlify will assign a random subdomain like `random-name-123.netlify.app`
- First build takes 2-5 minutes
- Watch the deploy log for any errors

---

## Step 2: Configure Custom Domain (ssthistlegorm.com)

### 2.1 Add Domain in Netlify
1. In your Netlify site dashboard, go to **"Domain settings"**
2. Click **"Add custom domain"**
3. Enter: `ssthistlegorm.com`
4. Click **"Verify"**
5. Netlify will show DNS configuration instructions

### 2.2 Configure DNS at Namecheap
1. Log in to your Namecheap account
2. Go to **Domain List** → Select `ssthistlegorm.com`
3. Click **"Manage"** → **"Advanced DNS"** tab

#### Option A: Using Netlify DNS (Recommended)
If you want Netlify to manage your DNS:
1. In Netlify, go to **Domain settings** → **"Set up Netlify DNS"**
2. Netlify will provide 4 nameservers (e.g., `dns1.p03.nsone.net`)
3. In Namecheap, select **"Custom DNS"** under Nameservers
4. Add all 4 Netlify nameservers
5. Click **"Save"**
6. DNS propagation takes 1-48 hours (usually < 4 hours)

#### Option B: Using Namecheap DNS (Alternative)
Keep Namecheap as DNS provider:

1. **Remove existing A records for @** (if any)
2. **Add new A record:**
   - Type: `A Record`
   - Host: `@`
   - Value: `75.2.60.5` (Netlify load balancer IP)
   - TTL: `Automatic`

3. **Add CNAME for www:**
   - Type: `CNAME Record`
   - Host: `www`
   - Value: `your-site-name.netlify.app` (replace with your actual Netlify subdomain)
   - TTL: `Automatic`

4. Click **"Save All Changes"**

### 2.3 Enable HTTPS in Netlify
1. In Netlify dashboard → **"Domain settings"** → **"HTTPS"**
2. Once DNS propagates, click **"Verify DNS configuration"**
3. Click **"Provision certificate"** (Let's Encrypt SSL - free)
4. Enable **"Force HTTPS"** (redirect HTTP to HTTPS)

**Note:** SSL certificate provisioning happens automatically after DNS verification.

---

## Step 3: Set Up GitHub OAuth for Sveltia CMS

To allow editors to log in to the CMS, you need to configure GitHub OAuth.

### 3.1 Create GitHub OAuth App
1. Go to https://github.com/settings/developers
2. Click **"OAuth Apps"** → **"New OAuth App"**
3. Fill in the details:
   - **Application name:** `Sveltia CMS - SS Thistlegorm`
   - **Homepage URL:** `https://ssthistlegorm.com`
   - **Authorization callback URL:** `https://api.netlify.com/auth/done`
4. Click **"Register application"**
5. Copy the **Client ID** (you'll need this)
6. Click **"Generate a new client secret"**
7. Copy the **Client Secret** (you'll need this immediately - it won't be shown again)

### 3.2 Configure GitHub OAuth in Netlify
1. In Netlify dashboard → **"Site settings"** → **"Access control"**
2. Scroll to **"OAuth"** section
3. Click **"Install provider"** → Select **"GitHub"**
4. Enter:
   - **Key (Client ID):** Paste the Client ID from GitHub
   - **Secret (Client Secret):** Paste the Client Secret from GitHub
5. Click **"Install"**

---

## Step 4: Access and Use Sveltia CMS

### 4.1 Access the CMS
Once everything is deployed:
1. Go to: `https://ssthistlegorm.com/admin/`
2. Click **"Login with GitHub"**
3. Authorize the OAuth app
4. You'll be redirected to the Sveltia CMS dashboard

### 4.2 Using Sveltia CMS
The CMS is configured with three collections:

1. **Blog Posts** (`_posts/`)
   - Create new blog posts
   - Edit existing posts
   - Manage categories and tags

2. **Pages** (individual pages like Home, About, Book, Contact, etc.)
   - Edit main site pages
   - Update content and taglines

3. **Other Wrecks** (`other-wrecks/`)
   - Add new wreck documentation
   - Edit existing wreck pages

### 4.3 Editorial Workflow
- **Draft:** Create and save drafts
- **In Review:** Submit for review
- **Ready:** Approve and publish
- Changes are committed directly to your GitHub repository
- Netlify automatically rebuilds the site on each commit

---

## Step 5: Verify Everything Works

### Checklist
- [ ] Site accessible at `https://ssthistlegorm.com`
- [ ] `https://www.ssthistlegorm.com` redirects to main domain
- [ ] HTTPS is working (padlock icon in browser)
- [ ] Old GitHub Pages URL redirects to new domain
- [ ] CMS accessible at `https://ssthistlegorm.com/admin/`
- [ ] Can log in to CMS with GitHub
- [ ] Can edit and publish content through CMS
- [ ] Site rebuilds automatically on CMS changes

---

## Troubleshooting

### DNS Not Resolving
- DNS changes take time (1-48 hours)
- Check DNS propagation: https://dnschecker.org
- Clear your browser cache and DNS cache: `sudo systemd-resolve --flush-caches`

### Build Failing on Netlify
- Check build logs in Netlify dashboard
- Verify Ruby version is correct (3.2.0)
- Ensure all gems are specified in Gemfile

### CMS Login Not Working
- Verify OAuth app callback URL is exactly: `https://api.netlify.com/auth/done`
- Check GitHub OAuth app is properly installed in Netlify
- Try clearing browser cookies and cache

### SSL Certificate Issues
- Wait for DNS to fully propagate before provisioning
- Try removing and re-adding the domain in Netlify
- Contact Netlify support if issues persist

---

## Additional Configuration (Optional)

### Deploy Notifications
Set up Slack/email notifications for successful/failed deployments:
- Netlify dashboard → **"Notifications"**

### Branch Deploys
Enable preview deploys for pull requests:
- Netlify dashboard → **"Build & deploy"** → **"Continuous deployment"**
- Enable "Deploy previews"

### Environment Variables
If you need to add secrets or API keys:
- Netlify dashboard → **"Site settings"** → **"Environment variables"**

---

## Next Steps

1. Test the CMS by creating a new blog post
2. Update your social media links to point to ssthistlegorm.com
3. Set up Google Analytics or other tracking (if needed)
4. Consider setting up form handling through Netlify Forms
5. Remove CNAME file from repository (Netlify handles this)

---

## Support Resources

- **Netlify Docs:** https://docs.netlify.com
- **Sveltia CMS Docs:** https://github.com/sveltia/sveltia-cms
- **Jekyll Docs:** https://jekyllrb.com/docs/

Your site is now running on modern infrastructure with a user-friendly CMS! 🚀
