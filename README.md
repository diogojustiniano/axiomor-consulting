# Axiomor Consulting Website

Premium data analytics and revenue operations consulting website.

## 🚀 Deploy to Vercel

### Option 1: Deploy via Vercel Dashboard (Easiest)

1. **Go to:** https://vercel.com
2. **Sign up/Login** with GitHub, GitLab, or Bitbucket
3. **Click:** "Add New..." → "Project"
4. **Import from Git:**
   - Push this folder to a GitHub repository
   - Select your repository in Vercel
   - Click "Deploy"
5. **Done!** Your site will be live at `https://your-project-name.vercel.app`

### Option 2: Deploy via Vercel CLI

```bash
# Install Vercel CLI
npm i -g vercel

# Navigate to project folder
cd axiomor-vercel

# Login to Vercel
vercel login

# Deploy
vercel

# For production deployment
vercel --prod
```

### Option 3: Drag & Drop (Fastest for Testing)

1. Go to https://vercel.com/new
2. Drag and drop this entire folder
3. Click "Deploy"

## 🌐 Custom Domain Setup

Once deployed, add your custom domain (axiomor.com):

1. **In Vercel Dashboard:**
   - Go to your project → Settings → Domains
   - Add domain: `axiomor.com` and `www.axiomor.com`

2. **In Your Domain Registrar (e.g., Namecheap, GoDaddy):**
   - Add Vercel's DNS records (Vercel will show you exactly what to add)
   - Typically:
     - A record: `76.76.21.21` (points to Vercel)
     - CNAME for www: `cname.vercel-dns.com`

3. **Wait 24-48 hours** for DNS propagation

## 📧 Email Setup (hello@axiomor.com)

After domain is configured:

1. **Set up email forwarding** in your domain registrar OR
2. **Use Google Workspace:**
   - Go to https://workspace.google.com
   - Sign up for Business Starter (~€5/user/month)
   - Verify domain ownership
   - Create hello@axiomor.com mailbox
   - Update MX records as instructed by Google

## 📁 Project Structure

```
axiomor-vercel/
├── index.html          # Main website file
├── vercel.json        # Vercel configuration
├── .gitignore         # Git ignore rules
└── README.md          # This file
```

## 🔧 Future Enhancements

### Contact Form Integration
The contact form currently doesn't send emails. To make it functional:

**Option 1: Formspree (Free tier available)**
```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

**Option 2: Netlify Forms (if you switch to Netlify)**
```html
<form netlify>
```

**Option 3: Custom Backend**
- Use Vercel Serverless Functions
- Integrate with SendGrid or AWS SES

### Analytics
Add to `<head>` in index.html:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>

<!-- or Plausible (privacy-friendly) -->
<script defer data-domain="axiomor.com" src="https://plausible.io/js/script.js"></script>
```

### SEO Improvements
- Add meta descriptions
- Add Open Graph tags for social sharing
- Create sitemap.xml
- Add robots.txt

## 📞 Support

For technical issues with Vercel:
- Documentation: https://vercel.com/docs
- Support: https://vercel.com/support

For website content updates:
- Edit `index.html` and redeploy

## 📝 License

© 2026 Axiomor Consulting. All rights reserved.
