# Pointing jurees.com to this portfolio site — checklist

**Status: ready to execute. Do NOT run these steps until the owner says so.**
Nothing here has been changed yet: the domain still points to the Shopify
store, which closes on **23 November 2026**. Complete the switch before
that date.

## Known facts

- Domain: `jurees.com`, registered at **Namecheap**, expires **23 July
  2027**. No transfer is needed — only DNS records change.
- This site is published from the GitHub repository
  `baderelmiftah99-source.github.io` (GitHub Pages).
- The store's catalogue on this page was captured from the public store
  before closure; product photos are served from Shopify's CDN — download
  and self-host them before the switch if the CDN copies disappear after
  closure (check one product image after the store closes).

## Steps

1. **GitHub Pages custom domain**
   - In the repository: Settings → Pages → Custom domain → enter
     `jurees.com` and save (this adds a `CNAME` file to the repo).
   - Wait for the HTTPS certificate to be issued, then tick
     **Enforce HTTPS**.

2. **Namecheap DNS for jurees.com** (Advanced DNS)
   - Delete Shopify's records:
     - `A` record, host `@`, pointing to Shopify (`23.227.38.65`).
     - `CNAME` record, host `www`, pointing to `shops.myshopify.com`.
   - Add GitHub Pages records:
     - `A` `@` → `185.199.108.153`
     - `A` `@` → `185.199.109.153`
     - `A` `@` → `185.199.110.153`
     - `A` `@` → `185.199.111.153`
     - (optional IPv6) `AAAA` `@` → `2606:50c0:8000::153`,
       `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`
     - `CNAME` `www` → `baderelmiftah99-source.github.io`
   - Leave every other record untouched (anything not listed above is not
     Shopify's and may belong to email or verification services).

3. **Verify**
   - Wait for DNS propagation (usually minutes, up to a few hours).
   - Open `https://jurees.com` and `https://www.jurees.com` — the portfolio
     must load with a valid HTTPS padlock.
   - Check the collection section: all 19 products visible with photos.

4. **After the switch**
   - The sample-store link used in outreach and profiles stays
     `https://www.jurees.com` — nothing else needs updating.
   - The Shopify store closes on its own on 23 November 2026; no payment
     and no further action there.
