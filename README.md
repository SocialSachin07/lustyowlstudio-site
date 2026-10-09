# Lusty Owl Studio landing page

Static one-page site that links to **https://lustyowlstudio.shop/**, with full Open Graph + X (Twitter) meta tags so shared links show a **large image preview card** on X, Facebook, WhatsApp and LinkedIn.

```
index.html          page + all meta tags
images/preview.jpg  1200x630 share image (also the hero)
```

## 1. Editing
- Public URL of this page: `https://lustyowlstudio-site.onrender.com` (canonical, og:url, og:image, og:image:secure_url, twitter:image). If you deploy elsewhere or add a custom domain, replace that base everywhere (image URLs **must stay absolute https**):
  `sed -i 's#https://lustyowlstudio-site.onrender.com#https://NEW-DOMAIN#g' index.html`
- CTA "Shop now" links to `https://lustyowlstudio.shop/`.
- Headline/title/og:title/twitter:title and the description (meta, og, twitter) should be kept in sync when edited.
- Optional: uncomment `twitter:site` and set your `@handle`.
- Replacing the image? Keep it 1200x630, JPG/PNG, < 1 MB. Rename the file (e.g. `preview-v2.jpg`) and update the tags to bust caches.

## 2. Deploy (free)
- **Render** (intended): New, Static Site, connect the `lustyowlstudio-site` GitHub repo, build command empty, publish directory `.`, service name `lustyowlstudio-site` (gives `lustyowlstudio-site.onrender.com`; if that name is taken, update the URLs above).
- Alternatives: Netlify Drop (https://app.netlify.com/drop), GitHub Pages (Settings, Pages, branch `main` / root), Vercel (`npx vercel`, preset "Other"). Update the base URL to match.

## 3. Verify the card
- Open https://lustyowlstudio-site.onrender.com/images/preview.jpg directly; it must load publicly.
- Checkers: https://www.opengraph.xyz, https://metatags.io, Facebook Sharing Debugger (https://developers.facebook.com/tools/debug/, "Scrape Again"), LinkedIn Post Inspector (https://www.linkedin.com/post-inspector/).
- **X**: the old Card Validator no longer shows previews. Paste the link into a new post (compose/draft, no need to publish) to see the card. X caches cards (~7 days); add `?v=2` or rename the image to refresh.
- **WhatsApp**: send the link to yourself; it caches too, so use `?v=2` when testing.
- Note: Render free static sites are fast, but the first crawler hit after a deploy can take a moment.
