# PairUp

Mentor/student matching site (static HTML + Supabase).

- `main/`  public site (deploy as Cloudflare Pages project #1, output directory `main`)
- `admin/` private Data Hub (deploy as Cloudflare Pages project #2, output directory `admin`)
- `supabase/` database scripts (run `setup.sql`, then `setup-v2.sql` in the Supabase SQL Editor) and the Stripe webhook function

## Cloudflare Pages settings (both projects)
Framework preset: None. Build command: (empty). Build output directory: `main` or `admin`.

## After deploying
- Supabase → Authentication → URL Configuration: set Site URL to your main site address (email confirm links use it).
- Stripe: paste your Payment Link into `pay:""` at the top of `main/index.html`.
- Never commit secret keys (Stripe secret, Supabase service_role). The publishable key in the HTML is meant to be public; the database rules protect the data.
