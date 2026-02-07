# 🚀 Quick Deployment Guide

## Fastest Way to Deploy (2 minutes)

### 1. Vercel CLI (Recommended)

```bash
# Navigate to project
cd /Users/seckincaglin/clawd/projects/freelance-fee-calculator

# Deploy (one command!)
npx vercel --prod

# Follow prompts:
# - Set up and deploy? Y
# - Scope: Your account
# - Link to existing project? N
# - Project name: freelance-fee-calculator
# - Directory: ./ (press enter)
# - Override settings? N

# Done! You'll get a live URL instantly
```

### 2. Vercel Dashboard (No CLI)

1. Go to https://vercel.com/new
2. Import Git repository OR drag `web` folder
3. Project name: `freelance-fee-calculator`
4. Root directory: `./` (or `web` if uploading just that folder)
5. Framework: Other
6. Click "Deploy"
7. ✅ Live in 30 seconds!

### 3. Custom Domain

```bash
# After deployment
vercel domains add calculator.cenoa.com
vercel alias [deployment-url] calculator.cenoa.com
```

Or in Vercel Dashboard:
1. Project Settings → Domains
2. Add `calculator.cenoa.com`
3. Configure DNS (Vercel provides instructions)

## Alternative Hosts

### Netlify Drop
1. Go to https://app.netlify.com/drop
2. Drag the `web` folder
3. ✅ Instant deploy!

### Cloudflare Pages
```bash
npx wrangler pages publish web --project-name=freelance-calculator
```

### GitHub Pages
```bash
# Create repo
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/cenoa/freelance-calculator.git
git push -u origin main

# Enable Pages: Settings → Pages → Source: main → /web
```

## Testing Locally

```bash
# Simple Python server
cd web
python3 -m http.server 8000

# Or Node.js
npx serve web

# Or PHP
php -S localhost:8000 -t web

# Open: http://localhost:8000
```

## Environment Checklist

- [ ] Index.html is in `/web` folder
- [ ] No external dependencies (all inline)
- [ ] Update CTA link to actual payment gateway checker URL
- [ ] Test on mobile
- [ ] Verify all calculations
- [ ] Check SEO meta tags
- [ ] Test sharing (social media previews)

## Post-Deployment

1. **Test the calculator**:
   - Upwork with $400 (20% fee)
   - Upwork with $5000 (blended fee)
   - Upwork with $15000 (lowest tier)
   - Fiverr with any amount (flat 20%)
   - Toptal with any amount (0% fee)

2. **Share the link**:
   - Twitter/X
   - LinkedIn
   - Facebook groups for freelancers
   - Reddit (r/freelance, r/Upwork)
   - Freelancer forums

3. **Monitor**:
   - Vercel Analytics (free tier)
   - Google Search Console
   - User feedback

## Quick Updates

Need to update fees or add platforms?

```bash
# Edit the file
nano web/index.html

# Or use your editor
code web/index.html

# Deploy update
vercel --prod

# Done! Live in seconds.
```

## Troubleshooting

**Build fails?**
- Ensure `vercel.json` is in project root
- Check that `web/index.html` exists
- Try: `vercel --debug`

**Wrong directory deployed?**
- Update `vercel.json` routes
- Or manually set root directory in dashboard

**Styles not loading?**
- All styles are inline, shouldn't happen
- Check console for errors
- Clear cache and hard refresh (Cmd+Shift+R)

**Calculations wrong?**
- Verify logic in `platforms` object
- Check browser console for errors
- Test with known values

## Performance

Current performance (expected):
- **Load time**: < 500ms
- **File size**: 27KB
- **Lighthouse score**: 95+
- **Mobile ready**: Yes

No optimization needed - it's already fast!

## Cost

**Vercel Free Tier**:
- ✅ Unlimited deployments
- ✅ 100GB bandwidth/month
- ✅ SSL included
- ✅ More than enough for this tool

Expected monthly cost: **$0** 🎉

---

Need help? Check README.md or reach out to the Cenoa team.
