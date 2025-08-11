# Stripe Donations (Vercel + Checkout)

Deploy a simple donation page that redirects to **Stripe Checkout** with a variable amount.

## Quick Deploy (Vercel)

1. Create a new project in Vercel and import this folder (Git or drag with the Vercel CLI).
2. In **Vercel → Settings → Environment Variables**, add:
   - `STRIPE_SECRET_KEY` = `sk_test_...` (use test first)
   - Optional: `SITE_NAME`, `CURRENCY` (`usd` default), `MIN_AMOUNT`, `MAX_AMOUNT`,
     `SUCCESS_URL`, `CANCEL_URL`
3. Deploy. Visit your site root to donate.

The browser posts to `/api/create-checkout-session`. The serverless function creates a Checkout Session and returns the redirect `url`.

## Local Dev

```bash
npm i -g vercel
npm i
vercel login
vercel dev
```

Then visit http://localhost:3000 and set a local env for `STRIPE_SECRET_KEY` (Vercel will prompt to link env).

## Notes

- Many network-branded gift/prepaid cards work like normal cards on Stripe, issuer permitting.
- Keep test mode until you’re fully satisfied.
