# 💰 Freelance Platform Fee Calculator

A comprehensive, production-ready tool that helps freelancers understand their real take-home pay after platform fees, payment gateway fees, and currency conversion fees.

## 🎯 Purpose

Freelancers on platforms like Upwork, Fiverr, and Freelancer.com often don't realize how much they actually take home after all deductions. This calculator provides complete transparency with:

- **Platform fees** (Upwork's sliding scale, Fiverr's 20%, etc.)
- **Payment gateway fees** (Payoneer, Wise, PayPal, etc.)
- **Currency conversion fees** (PKR, NGN, EGP, TRY, etc.)
- **Visual breakdown** of where every dollar goes

## 🌍 Target Audience

Freelancers in:
- 🇵🇰 Pakistan
- 🇳🇬 Nigeria
- 🇪🇬 Egypt
- 🇹🇷 Turkey
- And freelancers worldwide

## ✨ Features

### Platform Support
- **Upwork** - Sliding fee structure (20%/10%/5%)
- **Fiverr** - 20% flat fee
- **Freelancer.com** - 10% or $5 minimum
- **Toptal** - No freelancer fees!
- **PeoplePerHour** - 20% fee
- **Guru** - 5-9% depending on membership
- **99designs** - 15% platform fee

### Payment Gateways
- Payoneer (~2%)
- Wise/TransferWise (~1%)
- PayPal (~3%)
- Direct Bank Transfer (~1%)
- Cryptocurrency (~0.5-2%)

### Calculations
- Real-time fee calculations
- Multi-currency support (USD, EUR, GBP, CAD, AUD)
- Local currency conversion fees
- Visual progress bar breakdown
- Smart pro tips based on selections

### UI/UX
- Clean, modern design
- Mobile-responsive
- Single HTML file (no dependencies)
- Instant calculations
- Visual fee breakdown
- Shareable results

## 🚀 Deployment

### Option 1: Vercel (Recommended)

1. **Install Vercel CLI** (if not already installed):
   ```bash
   npm install -g vercel
   ```

2. **Deploy from project root**:
   ```bash
   cd /Users/seckincaglin/clawd/projects/freelance-fee-calculator
   vercel
   ```

3. **Follow prompts**:
   - Setup and deploy: Yes
   - Project name: `freelance-fee-calculator`
   - Directory: `./web`
   - Build command: (leave empty)
   - Output directory: (leave empty)

4. **Custom domain** (optional):
   ```bash
   vercel --prod
   vercel domains add calculator.cenoa.com
   ```

### Option 2: Netlify

1. Drag and drop the `web` folder to [Netlify Drop](https://app.netlify.com/drop)
2. Or connect your Git repository
3. Build settings: None needed (static HTML)
4. Publish directory: `web`

### Option 3: GitHub Pages

1. Push to GitHub repository
2. Go to Settings → Pages
3. Source: Deploy from branch
4. Branch: `main`, Folder: `/web`
5. Save and wait for deployment

### Option 4: Any Static Host

Simply upload the contents of the `/web` folder to:
- AWS S3 + CloudFront
- Google Cloud Storage
- Azure Static Web Apps
- Cloudflare Pages
- Or any web server

## 📁 Project Structure

```
freelance-fee-calculator/
├── web/
│   └── index.html          # Main calculator (single file, all-in-one)
├── README.md               # This file
└── vercel.json            # Vercel deployment config
```

## 🛠️ Technical Details

- **Framework**: Vanilla JavaScript (no dependencies)
- **Style**: Inline CSS (no external stylesheets)
- **Size**: ~27KB (single file)
- **Browser Support**: All modern browsers
- **Mobile**: Fully responsive
- **Performance**: Instant load, no external requests

## 🔗 Integration

The calculator includes a CTA linking to Cenoa's Payment Gateway Checker:
```
https://cenoa.com/tools/payment-gateway-checker
```

Update this link in `index.html` if the URL differs.

## 📊 Platform Fee Logic

### Upwork
```javascript
if (amount <= $500)       → 20%
if ($500 < amount <= $10K) → 10%
if (amount > $10K)        → 5%
```

### Fiverr
```javascript
Flat 20% on all earnings
```

### Freelancer.com
```javascript
Max(10%, $5 USD)
```

### Toptal
```javascript
$0 (client pays all fees)
```

## 🎨 Customization

### Colors
The gradient uses Cenoa's purple theme:
- Primary: `#667eea` to `#764ba2`
- Success: `#2ecc71`
- Warning: `#f39c12`
- Danger: `#e74c3c`

Update these in the `<style>` section to match your brand.

### Fee Data
Update platform fees in the `platforms` object:
```javascript
const platforms = {
    upwork: {
        name: 'Upwork',
        info: 'Fee structure description',
        calculate: (amount) => { /* calculation */ }
    }
}
```

### Payment Gateways
Add or modify gateways in the `gateways` object:
```javascript
const gateways = {
    payoneer: {
        name: 'Payoneer',
        fee: 0.02,
        info: 'Description'
    }
}
```

## 🧪 Testing Checklist

- [ ] Calculate with Upwork at different tiers ($400, $5000, $15000)
- [ ] Test all platforms
- [ ] Test all payment gateways
- [ ] Test currency conversions
- [ ] Mobile responsive check
- [ ] Cross-browser testing (Chrome, Firefox, Safari, Edge)
- [ ] Check pro tips display correctly
- [ ] Verify visual breakdown percentages
- [ ] Test form validation

## 📈 Future Enhancements

- [ ] Add more platforms (LinkedIn ProFinder, Contra, etc.)
- [ ] Historical fee tracking
- [ ] Compare multiple scenarios
- [ ] Export/share calculations
- [ ] Dark mode toggle
- [ ] Multi-language support (Turkish, Urdu, Arabic)
- [ ] Real-time currency conversion rates
- [ ] Save calculations to localStorage
- [ ] Print-friendly version

## 💡 Pro Tips Included

The calculator provides contextual tips like:
- "Build long-term Upwork clients to reduce fees to 5%"
- "Wise is cheaper than PayPal for withdrawals"
- "Toptal doesn't charge freelancers - great choice!"
- And more based on user selections

## 🤝 Contributing

To update fee structures or add new platforms:
1. Edit the `platforms` or `gateways` objects in `index.html`
2. Update the platform info text
3. Test calculations thoroughly
4. Deploy updates

## 📞 Support

For issues or questions:
- **Website**: https://cenoa.com
- **Tool URL**: (will be live after deployment)

## 📄 License

Built by Cenoa for the freelance community worldwide.

---

**Built with ❤️ by [Cenoa](https://cenoa.com)**  
*Helping freelancers understand their real earnings*
