# Deploy (in)Dependence Website to indep.app

## Quick Start Guide

### Method 1: GitHub Pages (Recommended - Easiest)

1. **Create a GitHub Repository**
   ```bash
   cd /home/user/workspace/website
   git init
   git add .
   git commit -m "Initial commit: (in)Dependence landing page"
   ```

2. **Push to GitHub**
   - Go to https://github.com/new
   - Create a new repository named `indep-app` (or any name)
   - Run these commands:
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/indep-app.git
   git branch -M main
   git push -u origin main
   ```

3. **Enable GitHub Pages**
   - Go to your repo Settings → Pages
   - Source: Deploy from branch
   - Branch: `main` → `/root` folder
   - Click Save
   - Wait 1-2 minutes for deployment

4. **Connect Custom Domain (indep.app)**
   - In GitHub Pages settings, add custom domain: `indep.app`
   - Click Save

5. **Update DNS Settings (At your domain registrar)**

   Add these DNS records:

   **A Records (for apex domain indep.app):**
   ```
   @ → 185.199.108.153
   @ → 185.199.109.153
   @ → 185.199.110.153
   @ → 185.199.111.153
   ```

   **CNAME Record (for www):**
   ```
   www → YOUR_USERNAME.github.io
   ```

6. **Create CNAME file** (if not auto-created)
   ```bash
   echo "indep.app" > CNAME
   git add CNAME
   git commit -m "Add custom domain"
   git push
   ```

7. **Wait for DNS propagation** (5-60 minutes)
   - Check status at: https://dnschecker.org
   - Your site will be live at https://indep.app

---

### Method 2: Netlify (Alternative - Also Easy)

1. **Sign up at Netlify**
   - Go to https://netlify.com
   - Sign up with GitHub

2. **Deploy**
   - Click "Add new site" → "Import an existing project"
   - Connect to GitHub
   - Select your `indep-app` repository
   - Build settings: Leave empty (static site)
   - Click "Deploy"

3. **Add Custom Domain**
   - Go to Site Settings → Domain Management
   - Add custom domain: `indep.app`
   - Follow Netlify's DNS instructions

---

### Method 3: Vercel (Alternative)

1. **Install Vercel CLI**
   ```bash
   npm i -g vercel
   ```

2. **Deploy**
   ```bash
   cd /home/user/workspace/website
   vercel --prod
   ```

3. **Add Custom Domain**
   - Go to project settings on vercel.com
   - Add domain: `indep.app`
   - Update DNS as instructed

---

## Files Included

- `index.html` - Main landing page
- `style.css` - Styles and animations
- `DEPLOYMENT.md` - This file

## Important: Before Going Live

1. **Update App Store Link**
   - Replace `YOUR_APP_ID` in index.html with your actual App Store ID
   - Find it in App Store Connect after submission
   - Example: `https://apps.apple.com/app/id1234567890`

2. **Create Privacy Policy**
   - Required for App Store submission
   - Create `/privacy.html` page
   - Add link to footer

3. **Create Terms of Service**
   - Create `/terms.html` page
   - Add link to footer

4. **Test Everything**
   - Test on mobile devices
   - Check all links work
   - Verify responsive design

---

## Customization Tips

### Change Colors
Edit `style.css` at the top:
```css
:root {
    --primary: #F59E0B;  /* Your brand color */
    --primary-dark: #D97706;
    --secondary: #10B981;
}
```

### Update Content
Edit `index.html`:
- Hero section: Update headline and subtitle
- Features: Add/remove feature cards
- Testimonials: Add real user reviews
- Pricing: Update when you finalize pricing

### Add Analytics
Before `</body>` tag in index.html:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

---

## Recommended Next Steps

1. ✅ Deploy to GitHub Pages (5 minutes)
2. ✅ Connect indep.app domain (5-60 minutes for DNS)
3. ✅ Create privacy policy page
4. ✅ Create terms of service page
5. ✅ Update App Store link when available
6. ✅ Add Google Analytics
7. ✅ Test on mobile devices
8. ✅ Share on social media

---

## Support

If you need help:
- GitHub Pages: https://docs.github.com/en/pages
- Netlify: https://docs.netlify.com
- Vercel: https://vercel.com/docs

Your website is ready to launch! 🚀
