# Content Manager Guide - SS Thistlegorm Website

Welcome! This guide will help you manage content on the SS Thistlegorm website using Sveltia CMS.

## Accessing the Content Management System (CMS)

**CMS URL:** https://ssthistlegorm.com/admin/

The CMS provides a user-friendly interface to edit website content without needing to know technical details.

---

## First Time Login

### Step 1: Navigate to the CMS
Open your web browser and go to: **https://ssthistlegorm.com/admin/**

### Step 2: Choose Login Method
You'll see two login options:
- **"Sign In with GitHub"** - Requires a GitHub account (not recommended for you)
- **"Sign In with GitHub Using Token"** - Use this option

### Step 3: Enter Your Access Token
1. Click **"Sign In with GitHub Using Token"**
2. A text field will appear
3. Paste the Personal Access Token you received (it's a long string starting with `ghp_`)
4. Click **"Sign in"**

### Step 4: You're In!
The CMS dashboard will load, showing all available content collections.

---

## Important: Token Storage & Security

### How Token Storage Works
- Your token is saved in your browser's local storage
- You only need to enter it **once per browser**
- It persists even after closing the browser
- Works indefinitely unless the token expires

### When You Need to Re-enter the Token
- Using a different browser (Chrome, Firefox, Safari, etc.)
- Using a different device (laptop, tablet, phone)
- Using incognito/private browsing mode
- After clearing browser cache/data
- If the token expires (check expiration date)

### Security Best Practices
- ✅ Keep your token confidential - it's like a password
- ✅ Don't share it with anyone else
- ✅ Don't post it publicly or in screenshots
- ✅ Store it securely (password manager recommended)
- ⚠️ On a shared computer, use incognito mode so the token isn't saved
- ⚠️ Anyone with access to your browser can use the CMS if logged in

---

## Using the CMS

### Available Content Collections

**1. Blog Posts**
- Create new blog posts
- Edit existing posts
- Add categories and tags
- Schedule publishing dates

**2. Pages**
- Edit main website pages:
  - Home Page
  - About Page
  - Book Page
  - Contact Page
  - Past Expeditions
  - Work Page

**3. Other Wrecks**
- Add documentation for other wreck sites
- Edit existing wreck pages

### Making Changes

1. **Navigate to a collection** (Posts, Pages, or Other Wrecks)
2. **Select an item** to edit or click "New" to create
3. **Edit the content** using the visual editor
4. **Add images** by uploading or selecting from media library
5. **Save your changes** - click the **"Save"** button
6. **Publish** - Changes are committed to the repository

### Publishing Workflow

- **Draft:** Work in progress, not visible on the site
- **In Review:** Ready for review (optional workflow)
- **Published:** Changes are saved and will appear on the website

**Important:** After saving, the website automatically rebuilds (takes 1-2 minutes). Your changes will be live shortly after publishing.

---

## Content Editing Tips

### Text Formatting
- Use the rich text editor toolbar for formatting
- **Bold**, *italic*, lists, headings are all supported
- Markdown syntax also works if you're familiar with it

### Adding Images
1. Click the image button or drag & drop
2. Images are stored in `assets/images/`
3. Use descriptive filenames
4. Optimize images before uploading (compress large files)

### Front Matter Fields
Each content type has specific fields:
- **Title:** Page or post title
- **Date:** Publication date (for posts)
- **Layout:** Template used (usually pre-set)
- **Tagline:** Optional subtitle
- **Tags/Categories:** For organization and filtering
- **Body:** Main content area (markdown editor)

---

## Troubleshooting

### "Failed to load" or "Cannot connect"
- Check your internet connection
- Verify you're logged in (refresh the page)
- Token may have expired - re-enter it

### Changes Not Appearing
- Wait 2-3 minutes for the site to rebuild
- Clear your browser cache
- Check that you clicked "Publish" not just "Save"

### Lost Access Token
- Contact the site administrator to generate a new token
- Old token will be revoked when a new one is issued

### Need Help?
Contact the website administrator if you encounter issues or have questions.

---

## Quick Reference

| Action | How To |
|--------|--------|
| Login | https://ssthistlegorm.com/admin/ → "Sign In with Token" |
| Create Post | Blog Posts → New Post |
| Edit Page | Pages → Select page → Edit |
| Add Image | Upload button in editor |
| Preview Changes | Save as Draft → Preview button |
| Publish | Save → Publish button |
| Logout | Click your profile icon → Sign out |

---

## Website Information

- **Public Website:** https://ssthistlegorm.com
- **CMS Admin Panel:** https://ssthistlegorm.com/admin/
- **Hosting:** Netlify
- **Content Repository:** GitHub (all changes are version controlled)

---

*Last updated: January 31, 2026*
