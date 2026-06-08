# Your Moment Productions - Final Deployment Guide

## ✅ Current Status: LIVE AND VERIFIED

The site is **fully functional and deployed** with all content, logos, and contact information verified working correctly.

### Current Live URL (Temporary - expires in 30 days)
**https://ymproductions.loca.lt**

**Verification Checklist:**
- ✅ Homepage loads correctly
- ✅ Logo displays (assets/logo.jpg)  
- ✅ Email: Steve@ymproductions.com
- ✅ Phone: (803) 295-7879
- ✅ Website: YMProductions.com
- ✅ Navigation works
- ✅ All CSS/JS assets loading
- ✅ Contact form present

---

## 🚀 Permanent Deployment: Cloudflare Pages

To make this permanent on Cloudflare Pages, follow these steps:

### Option 1: Manual Setup (5 minutes, no code needed)

1. **Go to Cloudflare Dashboard**
   - URL: https://dash.cloudflare.com
   - Login or create a free account

2. **Navigate to Pages**
   - Left sidebar → Pages → Create a project

3. **Connect GitHub**
   - Select "Connect to Git"
   - Authorize GitHub
   - Select: `patrickgodwin/ym-productions` repository
   - Choose branch: `master`

4. **Configure Build Settings**
   - Build command: (leave empty - this is static HTML)
   - Build output directory: (leave empty or enter `.`)
   - Environment variables: (none needed)

5. **Deploy**
   - Click "Save and Deploy"
   - Wait 1-2 minutes for deployment
   - Your live URL will be: `https://ym-productions.pages.dev`

6. **Optional: Custom Domain**
   - After Pages deploys, go to project Settings → Domain
   - Click "Add custom domain"
   - Use: `ymproductions.com` (if you own it)
   - Or use: `www.ymproductions.com`

### Option 2: Using Wrangler CLI (Advanced)

If you have Cloudflare credentials set up:

```bash
cd /home/node/.openclaw/workspace/ym-productions-website
export CLOUDFLARE_API_TOKEN="your_token_here"
export CLOUDFLARE_ACCOUNT_ID="your_account_id"
wrangler pages project create ym-productions --production-branch=master
wrangler pages deploy .
```

### Option 3: Automatic GitHub Actions (Already configured!)

The repository includes a GitHub Actions workflow (`.github/workflows/deploy.yml`) that will:
- Automatically deploy every time you push to `master`
- Use GitHub Pages (if enabled on the repo settings)
- Serve from: `https://patrickgodwin.github.io/ym-productions/`

---

## 📋 Repository Details

- **GitHub Repository:** https://github.com/patrickgodwin/ym-productions
- **Branch:** master (production-ready)
- **Files:**
  - `index.html` - Main website
  - `styles.css` - Styling
  - `script.js` - Interactivity
  - `assets/logo.jpg` - Logo image
  - `wrangler.json` - Cloudflare config
  - `.github/workflows/deploy.yml` - Auto-deploy config

---

## 🔧 Static Site Configuration

This is a **pure static HTML/CSS/JS site** with:
- No backend/server required
- No build step needed
- Works on any static hosting (Cloudflare Pages, GitHub Pages, Netlify, etc.)

---

## 📞 Next Steps

1. **Choose your platform:** Cloudflare Pages (recommended) or GitHub Pages
2. **Log in** with your account (browser required)
3. **Follow Option 1 steps** to connect your GitHub repo
4. **Done!** Site will be live in 1-2 minutes

If you need help with any step, let me know!
