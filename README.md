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
```

## Deploy on Cloudflare Pages

1. Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git → `fossil-bay-class-scenarios`.
2. Build settings: Framework preset **None**, build command empty, build output directory `/`.
3. Production branch: the branch holding this site.
4. Recommended: protect the site with Cloudflare Access (Zero Trust → Access → Applications) so only board members can open it.

Without Git: `npx wrangler pages deploy . --project-name fossil-bay-class-scenarios`.
