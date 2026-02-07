# 🧪 Testing Checklist

## Pre-Deployment Tests

### ✅ Calculation Accuracy

**Upwork Tests** (Sliding scale):
- [ ] $400 project → 20% fee = $80 → $320 after platform
- [ ] $500 project → 20% fee = $100 → $400 after platform
- [ ] $1000 project → $100 + 10% of $500 = $150 → $850 after platform
- [ ] $5000 project → $100 + 10% of $4500 = $550 → $4450 after platform
- [ ] $10,000 project → $100 + $950 = $1050 → $8950 after platform
- [ ] $15,000 project → $100 + $950 + 5% of $5000 = $1300 → $13,700 after platform

**Fiverr Tests** (Flat 20%):
- [ ] $100 project → 20% = $20 → $80 after platform
- [ ] $1000 project → 20% = $200 → $800 after platform

**Freelancer.com Tests** (10% or $5 min):
- [ ] $30 project → Max($3, $5) = $5 → $25 after platform
- [ ] $100 project → $10 → $90 after platform

**Toptal Tests** (No fee):
- [ ] Any amount → $0 fee → Full amount after platform

### ✅ Payment Gateway Fees

- [ ] Payoneer (2%): $1000 → $20 fee
- [ ] Wise (1%): $1000 → $10 fee
- [ ] PayPal (3% + $0.30): $1000 → $30.30 fee
- [ ] Bank Transfer (1%): $1000 → $10 fee
- [ ] Crypto (0.5%): $1000 → $5 fee

### ✅ Currency Conversion

- [ ] USD → USD: 0% conversion fee
- [ ] USD → PKR: 2% conversion fee
- [ ] USD → NGN: 2.5% conversion fee
- [ ] USD → EGP: 2% conversion fee
- [ ] USD → TRY: 1.5% conversion fee

### ✅ Visual Tests

- [ ] Progress bar shows correct percentages
- [ ] All segments visible and labeled
- [ ] Legend matches progress bar colors
- [ ] Mobile responsive (< 640px width)
- [ ] Tablet view (640-1024px)
- [ ] Desktop view (> 1024px)

### ✅ Form Validation

- [ ] Empty platform → error
- [ ] Empty amount → error
- [ ] Negative amount → error
- [ ] Zero amount → error
- [ ] Decimal amounts work (e.g., $99.99)
- [ ] Large amounts work (e.g., $50,000)

### ✅ User Experience

- [ ] Platform info shows on selection
- [ ] Real-time calculations after first submit
- [ ] Smooth scroll to results
- [ ] Results stay visible on re-calculation
- [ ] Pro tips change based on selections
- [ ] CTA link works

### ✅ Browser Compatibility

- [ ] Chrome/Chromium (latest)
- [ ] Firefox (latest)
- [ ] Safari (latest)
- [ ] Edge (latest)
- [ ] Mobile Safari (iOS)
- [ ] Mobile Chrome (Android)

### ✅ Performance

- [ ] Page loads < 1 second
- [ ] No console errors
- [ ] No network requests (all inline)
- [ ] Smooth animations
- [ ] No layout shifts

## Test Scenarios

### Scenario 1: Pakistani Upwork Freelancer
```
Platform: Upwork
Amount: $2000
Currency: USD
Gateway: Payoneer
Local: PKR

Expected:
- Platform fee: $100 + 10% of $1500 = $250 (12.5%)
- After platform: $1750
- Payoneer: $35 (2%)
- After gateway: $1715
- Conversion: $34.30 (2%)
- Final: $1680.70 (84% take-home)
```

### Scenario 2: Nigerian Fiverr Seller
```
Platform: Fiverr
Amount: $500
Currency: USD
Gateway: Wise
Local: NGN

Expected:
- Platform fee: $100 (20%)
- After platform: $400
- Wise: $4 (1%)
- After gateway: $396
- Conversion: $9.90 (2.5%)
- Final: $386.10 (77.2% take-home)
```

### Scenario 3: Turkish Toptal Developer
```
Platform: Toptal
Amount: $5000
Currency: USD
Gateway: Bank Transfer
Local: TRY

Expected:
- Platform fee: $0 (0%)
- After platform: $5000
- Bank: $50 (1%)
- After gateway: $4950
- Conversion: $74.25 (1.5%)
- Final: $4875.75 (97.5% take-home)
```

### Scenario 4: Egyptian Freelancer (Crypto Withdrawal)
```
Platform: Freelancer.com
Amount: $3000
Currency: USD
Gateway: Cryptocurrency
Local: USD (keeping USD)

Expected:
- Platform fee: $300 (10%)
- After platform: $2700
- Crypto: $13.50 (0.5%)
- After gateway: $2686.50
- Conversion: $0 (0%)
- Final: $2686.50 (89.6% take-home)
```

## Manual Testing Steps

1. **Open the calculator** (local or deployed)
2. **Fill the form** with test data
3. **Click Calculate**
4. **Verify**:
   - Original amount displayed correctly
   - Final take-home matches expected
   - Breakdown shows all fees
   - Percentages add up to 100%
   - Progress bar is accurate
   - Pro tip is relevant
5. **Change inputs** and verify real-time updates
6. **Try different platforms**
7. **Test on mobile device**

## Quick Smoke Test

```javascript
// Open browser console on the calculator page
// Run these checks:

// Test 1: Upwork $1000
// Platform: Upwork, Amount: 1000, Currency: USD, Gateway: Payoneer, Local: USD
// Expected final: ~$830 (17% total fees)

// Test 2: Toptal $5000
// Platform: Toptal, Amount: 5000, Currency: USD, Gateway: Wise, Local: USD
// Expected final: ~$4850 (3% total fees)

// Test 3: Fiverr $500
// Platform: Fiverr, Amount: 500, Currency: USD, Gateway: PayPal, Local: PKR
// Expected final: ~$375 (25% total fees)
```

## Automated Testing (Future)

Consider adding Jest/Vitest tests for:
```javascript
describe('Platform Fees', () => {
  test('Upwork sliding scale', () => {
    expect(calculateUpworkFee(400)).toBe(80);
    expect(calculateUpworkFee(1000)).toBe(150);
    expect(calculateUpworkFee(15000)).toBe(1300);
  });
});
```

## Regression Testing

After any update, re-run:
- [ ] All calculation tests
- [ ] Mobile responsive check
- [ ] Cross-browser check
- [ ] At least 3 full scenarios

## Issues to Watch For

Common bugs:
- ❌ Percentages don't add to 100% (rounding errors)
- ❌ Progress bar segments too small to see
- ❌ Conversion fee applied when currencies match
- ❌ Form validation not working
- ❌ Mobile layout breaking
- ❌ Pro tips not updating

## Sign-off

- [ ] All calculations verified
- [ ] Visual layout correct on all devices
- [ ] No console errors
- [ ] Performance acceptable
- [ ] Ready for production ✅

---

**Tested by**: _________  
**Date**: _________  
**Version**: 1.0.0  
**Status**: ⬜ Pass | ⬜ Fail | ⬜ Needs Review
