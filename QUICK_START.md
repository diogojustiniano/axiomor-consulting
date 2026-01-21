# 🚀 QUICK START - Deploy in 5 Minutes

## Fastest Way to Get Your Website Live

### 1️⃣ Go to Vercel
```
https://vercel.com/new
```

### 2️⃣ Sign Up
- Use email, GitHub, or GitLab
- Takes 30 seconds

### 3️⃣ Upload Files
- Drag the entire `axiomor-vercel` folder
- OR click "Browse" and select the folder

### 4️⃣ Click Deploy
- Wait ~30 seconds
- **Done!** Your site is live

### 5️⃣ Your Website URL
```
https://axiomor-website-XXXXX.vercel.app
```

---

## Next Steps (After Deploy)

### Add Custom Domain (axiomor.com)
1. Buy domain at Namecheap/GoDaddy/Ionos
2. In Vercel: Settings → Domains → Add `axiomor.com`
3. Update DNS records as shown by Vercel
4. Wait 24 hours for DNS propagation

### Setup Email (hello@axiomor.com)
**Option 1: Google Workspace** (€5.75/month)
- https://workspace.google.com
- Professional Gmail interface
- Best for business

**Option 2: Zoho Mail** (Free or €0.90/month)
- https://www.zoho.com/mail/
- Good free tier

### Make Contact Form Work
**Use Formspree** (Free tier available)
1. Go to https://formspree.io
2. Create form
3. Get your form ID
4. Update this line in index.html:
```html
<form action="https://formspree.io/f/YOUR_ID" method="POST">
```

### Add Analytics
**Google Analytics** (Free)
1. https://analytics.google.com
2. Create property for axiomor.com
3. Add tracking code to website

---

## Files You Need

All files are in the `axiomor-vercel` folder:

```
✅ index.html          - Your website
✅ vercel.json         - Configuration
✅ README.md           - Documentation
✅ DEPLOYMENT_GUIDE.md - Detailed instructions
✅ .gitignore          - Git configuration
```

---

## Support

- **Vercel Docs:** https://vercel.com/docs
- **Vercel Support:** https://vercel.com/support

**You've got this! 🚀**
