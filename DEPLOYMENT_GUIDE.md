# 🚀 AXIOMOR WEBSITE - VERCEL DEPLOYMENT GUIDE

## Quick Start (5 Minutes to Live Website)

### METHOD 1: GitHub + Vercel (Recommended) ⭐

#### Step 1: Create GitHub Repository
1. Go to https://github.com/new
2. Repository name: `axiomor-website`
3. Description: "Axiomor Consulting official website"
4. Set to **Public** (or Private if you prefer)
5. Click "Create repository"

#### Step 2: Upload Files to GitHub
You have the `axiomor-vercel` folder with these files:
- `index.html` (your website)
- `vercel.json` (configuration)
- `.gitignore`
- `README.md`

**Option A - Using GitHub Web Interface:**
1. In your new repository, click "uploading an existing file"
2. Drag all files from the `axiomor-vercel` folder
3. Commit message: "Initial website deployment"
4. Click "Commit changes"

**Option B - Using Git (if you have it installed):**
```bash
cd axiomor-vercel
git init
git add .
git commit -m "Initial website deployment"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/axiomor-website.git
git push -u origin main
```

#### Step 3: Deploy to Vercel
1. Go to https://vercel.com/signup
2. Click "Continue with GitHub"
3. Authorize Vercel to access GitHub
4. Click "Import Project"
5. Select `axiomor-website` repository
6. Click "Deploy"
7. **Done!** Your site is live at `https://axiomor-website.vercel.app`

---

### METHOD 2: Direct Upload (Fastest - 2 Minutes) ⚡

#### Steps:
1. Go to https://vercel.com/new
2. Sign up/Login (use email, GitHub, or GitLab)
3. Click "Browse" or drag the entire `axiomor-vercel` folder
4. Click "Deploy"
5. **Done!** Your site is live instantly

**Note:** This method doesn't use Git, so future updates require re-uploading.

---

### METHOD 3: Vercel CLI (For Developers) 💻

#### Prerequisites:
- Node.js installed on your computer

#### Steps:
```bash
# 1. Install Vercel CLI globally
npm i -g vercel

# 2. Navigate to your project
cd axiomor-vercel

# 3. Login to Vercel
vercel login

# 4. Deploy (follow prompts)
vercel

# 5. Deploy to production
vercel --prod
```

---

## 🌐 CUSTOM DOMAIN SETUP (axiomor.com)

### Step 1: Buy Domain
If you haven't already:
- **Namecheap:** https://www.namecheap.com (~$10/year)
- **GoDaddy:** https://www.godaddy.com
- **Google Domains:** https://domains.google
- **Ionos:** https://www.ionos.com (popular in Spain)

### Step 2: Add Domain to Vercel
1. In Vercel Dashboard → Your Project → Settings → Domains
2. Click "Add"
3. Enter: `axiomor.com`
4. Click "Add"
5. Enter: `www.axiomor.com`
6. Click "Add"

### Step 3: Configure DNS at Domain Registrar

Vercel will show you exactly what DNS records to add. Typically:

**For root domain (axiomor.com):**
- Type: `A`
- Name: `@` (or leave blank)
- Value: `76.76.21.21`
- TTL: Automatic or 3600

**For www subdomain:**
- Type: `CNAME`
- Name: `www`
- Value: `cname.vercel-dns.com`
- TTL: Automatic or 3600

**Example in Namecheap:**
1. Sign in to Namecheap
2. Domain List → Manage → Advanced DNS
3. Add New Record:
   - A Record: Host `@`, Value `76.76.21.21`
   - CNAME Record: Host `www`, Value `cname.vercel-dns.com`
4. Save

**Wait 24-48 hours** for DNS propagation (usually faster, ~1-4 hours)

---

## 📧 EMAIL SETUP (hello@axiomor.com)

### Option 1: Google Workspace (Recommended) ⭐
**Cost:** €5.75/user/month

#### Steps:
1. Go to https://workspace.google.com
2. Click "Get Started"
3. Enter business name: "Axiomor Consulting"
4. Number of employees: "Just you" or "2-9"
5. Country: Spain
6. Enter your current email for setup
7. Domain: "Yes, I have one I can use"
8. Enter: `axiomor.com`
9. Follow verification steps (add TXT record to DNS)
10. Create email: `hello@axiomor.com`
11. Add MX records to your domain's DNS (Google provides exact values)

**Benefits:**
- Professional Gmail interface
- 30GB storage per user
- Google Drive, Calendar, Meet included
- Mobile apps

### Option 2: Zoho Mail (Free tier available)
**Cost:** Free for 1 user (5GB) or €0.90/user/month

#### Steps:
1. Go to https://www.zoho.com/mail/
2. Sign up for free
3. Add domain: `axiomor.com`
4. Verify ownership (TXT record)
5. Create email: `hello@axiomor.com`
6. Configure MX records

### Option 3: Email Forwarding (Budget option)
**Cost:** Usually free with domain purchase

#### Steps:
1. In your domain registrar (Namecheap, etc.)
2. Go to Email Forwarding settings
3. Forward `hello@axiomor.com` → your personal Gmail
4. **Downside:** Can't send FROM hello@axiomor.com (only receive)

---

## 🎨 OPTIONAL ENHANCEMENTS

### 1. Working Contact Form

The form currently doesn't send emails. Here's how to fix it:

#### Formspree (Easiest - Free tier available)
1. Go to https://formspree.io
2. Sign up (free)
3. Create new form
4. Get your form endpoint: `https://formspree.io/f/YOUR_ID`
5. Update in `index.html`:
```html
<form action="https://formspree.io/f/YOUR_ID" method="POST">
```

#### Web3Forms (Alternative - Free)
1. Go to https://web3forms.com
2. Enter email: hello@axiomor.com
3. Get access key
4. Update form in `index.html`:
```html
<form action="https://api.web3forms.com/submit" method="POST">
    <input type="hidden" name="access_key" value="YOUR_ACCESS_KEY">
    <!-- rest of form -->
</form>
```

### 2. Analytics (Track Visitors)

#### Google Analytics (Free)
1. Go to https://analytics.google.com
2. Create account
3. Add property: axiomor.com
4. Get tracking ID: `G-XXXXXXXXXX`
5. Add to `<head>` in index.html:
```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

#### Plausible (Privacy-friendly alternative)
**Cost:** €9/month (simpler, GDPR-compliant)
1. Go to https://plausible.io
2. Sign up
3. Add domain: axiomor.com
4. Add to `<head>` in index.html:
```html
<script defer data-domain="axiomor.com" src="https://plausible.io/js/script.js"></script>
```

### 3. SEO Improvements

Add to `<head>` in index.html:
```html
<!-- Meta Description -->
<meta name="description" content="Axiomor Consulting provides expert data analytics and revenue operations consulting for Series A and B companies. Transform data into revenue with our proven RevOps strategies.">

<!-- Open Graph (for social sharing) -->
<meta property="og:title" content="Axiomor | Data Analytics & Revenue Operations Excellence">
<meta property="og:description" content="Expert data analytics and revenue operations consulting for growth-stage companies.">
<meta property="og:type" content="website">
<meta property="og:url" content="https://axiomor.com">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Axiomor Consulting">
<meta name="twitter:description" content="Transform data into revenue with expert RevOps consulting.">
```

---

## 📊 VERCEL DASHBOARD OVERVIEW

After deployment, your dashboard shows:

### Deployments Tab
- Every deployment (production + preview)
- Build logs
- Deploy history

### Analytics Tab (Free tier included)
- Pageviews
- Top pages
- Visitors by country
- Devices used

### Settings Tab
Important settings:
- **Domains:** Add custom domain
- **Environment Variables:** If you add backend functionality
- **General:** Project name, framework preset

---

## 🔄 UPDATING YOUR WEBSITE

### If using GitHub (Method 1):
1. Edit `index.html` in your repository
2. Commit changes
3. Vercel automatically rebuilds and deploys
4. Live in ~30 seconds

### If using Direct Upload (Method 2):
1. Edit `index.html` locally
2. Go to https://vercel.com/new
3. Re-upload the folder
4. Deploys instantly

### If using CLI (Method 3):
```bash
# Make your changes to index.html
# Then redeploy:
vercel --prod
```

---

## ⚡ TROUBLESHOOTING

### Website not loading?
- Check deployment status in Vercel dashboard
- Look at build logs for errors
- Verify index.html is in root directory

### Custom domain not working?
- DNS propagation can take 24-48 hours
- Use https://dnschecker.org to verify DNS records
- Make sure you added BOTH A record and CNAME

### Contact form not working?
- Default form doesn't work (just shows data)
- Integrate Formspree or Web3Forms (see above)

### Email not receiving?
- Check MX records are configured correctly
- Use Google's MX record checker
- Allow 24 hours for email DNS propagation

---

## ✅ PRE-LAUNCH CHECKLIST

Before you go live:

### Technical
- [ ] Website deployed to Vercel
- [ ] Custom domain configured (axiomor.com)
- [ ] Email setup (hello@axiomor.com)
- [ ] Contact form working (Formspree/Web3Forms)
- [ ] Analytics installed (Google Analytics or Plausible)
- [ ] Test on mobile devices
- [ ] Test on different browsers (Chrome, Safari, Firefox)

### Content
- [ ] All text proofread
- [ ] Links work (Services, Contact, etc.)
- [ ] Email address is correct
- [ ] Phone number (if you add one)
- [ ] Location is correct (Madrid, Spain)

### Legal (for Spain)
- [ ] Política de Privacidad (Privacy Policy)
- [ ] Aviso Legal (Legal Notice)
- [ ] Política de Cookies (Cookie Policy)
- [ ] Terms of Service

**Note:** You'll need to add these legal pages for GDPR compliance. You can generate them at https://www.iubenda.com or consult a lawyer.

---

## 🎉 YOU'RE READY!

After completing this guide:
- ✅ Website live on Vercel
- ✅ Custom domain configured
- ✅ Professional email setup
- ✅ Contact form working
- ✅ Analytics tracking visitors

**Your Axiomor Consulting website is ready for launch!**

Questions? Check:
- Vercel Docs: https://vercel.com/docs
- Vercel Support: https://vercel.com/support

Good luck with your launch! 🚀
