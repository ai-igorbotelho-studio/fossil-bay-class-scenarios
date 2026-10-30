# Fossil Bay — 2027 classroom scenarios

A one-page planning tool for the Trust Board. It compares four ways to run the classroom in 2027:

1. 5 days a week, usual holidays
2. 4 days a week, usual holidays
3. 5 days a week, extended holidays
4. 4 days a week, extended holidays

Each scenario shows school days, fee income, running cost, the result at current enrolment and the children needed to break even. Every assumption is editable on the page (kept in the viewer's browser only).

Visual: Fossil Bay design system (Raleway, Fjalla One, blush and navy, watercolour discs, official logo).

**The cost figures are examples.** Only the enrolment (6), the fee ($13,100) and the ~11 break-even come from the 2027 appeal. Replace the `DEFAULTS` object in `index.html` with the GM's figures.

## Files

```
index.html     the page (CSS and JS inline; DEFAULTS near the top of the script)
assets/        logo and watercolour discs
_headers       security headers and noindex (Cloudflare Pages)
robots.txt     blocks indexing — this is an internal planning draft
sitemap.xml    the one URL
og-image.jpg   share preview (1200×630) for WhatsApp, Facebook, LinkedIn
og/            og.html (source of the share image) and render.mjs
```

## Share image and meta tags

`index.html` carries the description, canonical URL, Open Graph, Twitter card and JSON-LD tags, all pointing at `https://fossil-bay-class-scenarios.pages.dev`. If a custom domain is set, replace that URL in `index.html`, `robots.txt` and `sitemap.xml`.

The page is `noindex` while the costs are examples. To let search engines list it, set the robots meta to `index, follow`, remove `X-Robots-Tag` from `_headers` and change `robots.txt` to allow `/` with a `Sitemap:` line.

To regenerate the share image after editing `og/og.html`:

```
npm i -D playwright
node og/render.mjs
```

WhatsApp caches previews: after changing the image, rename it or add `?v=2` to the `og:image` URLs.

## Deploy on Cloudflare Pages

1. Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git → `fossil-bay-class-scenarios`.
2. Build settings: Framework preset **None**, build command empty, build output directory `/`.
3. Production branch: the branch holding this site.
4. Recommended: protect the site with Cloudflare Access (Zero Trust → Access → Applications) so only board members can open it.

Without Git: `npx wrangler pages deploy . --project-name fossil-bay-class-scenarios`.
