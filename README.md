# Sage on Cloudflare Pages (free)

Same site, with the card form inside your own checkout window. Server code runs as Cloudflare Pages Functions.

## Deploy (free)
1. Put the contents of this folder in a GitHub repo (index.html, functions/, README.md).
2. dash.cloudflare.com > Workers & Pages > Create > Pages > Connect to Git > pick the repo.
3. Build settings: Framework preset "None", build command empty, output directory "/" (or leave blank). Save and Deploy.
4. Project > Settings > Variables and Secrets > add (as Secrets): STRIPE_SECRET_KEY (sk_test_...), STRIPE_PUBLISHABLE_KEY (pk_test_...), SIGNING_SECRET (long random text).
5. Deployments > Retry / redeploy so the variables apply. Open your *.pages.dev address and test with card 4242 4242 4242 4242.

## Going live
Replace the two Stripe keys with the live ones (sk_live_ / pk_live_) and redeploy.

## Change prices
Edit PLANS in functions/_lib/util.js (amounts in cents).
