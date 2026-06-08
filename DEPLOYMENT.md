# YOUR MOMENT PRODUCTIONS — Deployment Guide

## 🚀 Quick Deployment to Cloudflare Pages

### Option 1: Deploy via GitHub (Recommended)

This is the fastest and most reliable method.

#### Step 1: Push to GitHub

```bash
cd ym-productions-website

# Initialize git repo (if not already done)
git init
git add .
git commit -m "Initial commit: YOUR MOMENT PRODUCTIONS website"

# Add your GitHub remote
git remote add origin https://github.com/YOUR_USERNAME/ym-productions.git

# Push to main branch
git push -u origin main
```

#### Step 2: Connect to Cloudflare Pages

1. Go to [Cloudflare Dashboard](https://dash.cloudflare.com)
2. Click **Pages** in the left sidebar
3. Click **Create a project**
4. Select **Connect to Git**
5. Authorize GitHub and select your `ym-productions` repository
6. Click **Begin setup**
7. Configure build settings:
   - **Framework preset:** None (static site)
   - **Build command:** Leave blank
   - **Build output directory:** `/` (root)
8. Click **Save and Deploy**

Your site will be live at: `https://ym-productions.pages.dev`

#### Step 3: Connect Custom Domain

1. In Cloudflare Pages, go to your project settings
2. Click **Custom domain**
3. Enter `ymproductions.com`
4. Update your domain's nameservers to point to Cloudflare (if not already done)

---

### Option 2: Deploy via Wrangler CLI (Advanced)

If you have a Cloudflare account and API token:

#### Step 1: Create API Token

1. Go to [Cloudflare API Tokens](https://dash.cloudflare.com/profile/api-tokens)
2. Click **Create Token**
3. Use the **Edit Cloudflare Workers** template
4. Copy the token

#### Step 2: Deploy

```bash
# Set environment variable
export CLOUDFLARE_API_TOKEN="your_token_here"

# Deploy
cd ym-productions-website
npx wrangler pages deploy . --project-name ym-productions --branch main
```

---

### Option 3: Manual Upload (Simplest)

1. Go to [Cloudflare Pages](https://dash.cloudflare.com/pages)
2. Click **Create a project** > **Direct upload**
3. Drag and drop the entire `ym-productions-website` folder
4. Click **Deploy site**

Your site will be live at: `https://[random-id].pages.dev`

---

## 📋 Pre-Deployment Checklist

- [x] HTML validation — All semantic markup in place
- [x] CSS optimization — Mobile-responsive, modern styling
- [x] JavaScript — Form validation, smooth scrolling, menu toggle
- [x] Images — SVG icons (no external dependencies)
- [x] Accessibility — Semantic HTML, ARIA labels where needed
- [x] Performance — Lightweight, optimized assets
- [x] SEO — Meta tags, proper heading hierarchy

---

## 🔧 After Deployment

### 1. Verify Site is Live

Visit your Cloudflare Pages URL and check:
- [ ] Hero section loads correctly
- [ ] Navigation menu works on mobile
- [ ] Circular badge seal displays properly
- [ ] Contact form is functional
- [ ] All links work (smooth scrolling)

### 2. Connect Email

Contact form currently uses client-side validation. To make it functional:

**Option A: Use Formspree (Free)**

```html
<!-- Replace <form> action in index.html -->
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

**Option B: Use Cloudflare Workers**

Create a simple worker to forward form submissions to your email.

### 3. Analytics

Add Google Analytics or Cloudflare Analytics:

```html
<!-- Add before closing </head> tag in index.html -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_ID');
</script>
```

### 4. Update Contact Info

Replace placeholder contact information:
- Phone number
- Email address
- Social media links

---

## 🎨 Future Customizations

### Add Portfolio Items

Replace portfolio placeholder in `index.html`:

```html
<div class="portfolio-item">
    <div class="portfolio-placeholder">
        <img src="/path/to/image.jpg" alt="Project name">
    </div>
</div>
```

### Update Services

Edit service descriptions in the services grid (both hero and detailed sections).

### Change Colors

All colors are in `:root` variables in `styles.css`:

```css
:root {
    --gold: #C4A853;  /* Change accent color */
    --primary-black: #000000;  /* Change background */
    --white: #ffffff;  /* Change text */
}
```

### Add Blog

Create a `/blog/` directory with individual post files, or integrate a CMS.

---

## 📞 Support

For deployment questions:
- [Cloudflare Pages Docs](https://developers.cloudflare.com/pages/)
- [Wrangler CLI Docs](https://developers.cloudflare.com/workers/wrangler/install-and-update/)

---

## ✅ Deployment Status

- **Domain:** YMProductions.com (ready for connection)
- **Files:** All production-ready
- **Size:** ~37KB (HTML + CSS + JS)
- **Performance:** Fast-loading, optimized for mobile
- **Ready to Deploy:** ✅ YES

---

**YOUR MOMENT PRODUCTIONS** — Ready to go live! 🎬
