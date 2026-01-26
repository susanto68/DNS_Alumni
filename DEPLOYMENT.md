# Deployment Guide

## ✅ GitHub Status
Your code has been successfully pushed to: **https://github.com/susanto68/DNS_Alumni.git**

## 🚀 Deploy to Vercel

### Method 1: Via Vercel Dashboard (Recommended)

1. **Go to Vercel**
   - Visit: https://vercel.com
   - Sign in with your GitHub account (or create an account)

2. **Import Your Repository**
   - Click "Add New..." → "Project"
   - Find and select: `susanto68/DNS_Alumni`
   - Click "Import"

3. **Configure Project**
   - **Framework Preset:** Other (or leave as default)
   - **Root Directory:** `./` (default)
   - **Build Command:** Leave empty (static site)
   - **Output Directory:** Leave empty
   - Click "Deploy"

4. **Wait for Deployment**
   - Vercel will automatically deploy your site
   - You'll get a URL like: `dns-alumni.vercel.app`

5. **Custom Domain (Optional)**
   - Go to Project Settings → Domains
   - Add your custom domain if needed

### Method 2: Via Vercel CLI

1. **Install Vercel CLI**
   ```bash
   npm install -g vercel
   ```

2. **Login to Vercel**
   ```bash
   vercel login
   ```

3. **Deploy**
   ```bash
   cd "c:\Users\susan\Desktop\DNS Alumni"
   vercel
   ```

4. **Follow the prompts**
   - Link to existing project or create new
   - Confirm settings
   - Deploy!

## 📝 Important Notes

### Files Required in Root Directory:
- ✅ `index.html` - Main page
- ✅ `style.css` - Stylesheet
- ✅ `QR_Code.jpeg` - Payment QR code
- ✅ All image files (logo.png, alumni1-8.jpeg, susanto.jpg, etc.)

### After Deployment:
1. **Test the website** - Make sure all images load correctly
2. **Test the QR code** - Verify it's clickable and opens UPI payment
3. **Update Google Form** - Don't forget to:
   - Create your Google Form
   - Get the POST URL
   - Replace `PASTE_GOOGLE_FORM_POST_URL_HERE` in index.html
   - Update all entry IDs (entry.1111111111, etc.)

### Environment Variables (if needed):
- Currently none required for this static site

## 🔄 Updating the Site

After making changes:
```bash
cd "c:\Users\susan\Desktop\DNS Alumni"
git add .
git commit -m "Your commit message"
git push origin main
```

Vercel will automatically redeploy if you've connected it to GitHub!

## 📞 Support

- Vercel Docs: https://vercel.com/docs
- GitHub Repo: https://github.com/susanto68/DNS_Alumni
