# Cloudflare Pages migration checklist

## 1. Copy and verify the site

- Copy the current production files from `sorasukt/sorasukt.github.io`.
- Preserve paths, filename casing, `404.html`, `robots.txt`, and `sitemap.xml`.
- Review the existing `CNAME` file; Cloudflare Pages manages the custom domain in its dashboard.
- Confirm that browser-side API URLs, authentication callbacks, payment redirects, and absolute links still point to the intended services.
- Do not copy secrets, local environment files, or generated dependency folders.

## 2. Connect Cloudflare Pages

1. Open Cloudflare Dashboard → Workers & Pages → Create application → Pages → Connect to Git.
2. Select `sorasukt/Website`.
3. Set the production branch to `main`.
4. Use no framework preset and no build command.
5. Set the build output directory to `.`.
6. Deploy first to the generated `*.pages.dev` address.

## 3. Test before changing DNS

- Home page and custom 404 page.
- Navigation, images, fonts, and downloads.
- Mobile layout and accessibility.
- `/support`, `/donate`, `/privacy`, `/terms`, and other public routes.
- External APIs, checkout, login/logout, and callback URLs.
- Security headers and redirects.
- `robots.txt` and `sitemap.xml`.

## 4. Cut over the domain

- Add `sorasukt.com` as a custom domain in Cloudflare Pages.
- Follow the DNS instructions shown by Cloudflare.
- Update allowlists and callback URLs that depend on the production origin.
- Verify HTTPS and both apex/www behavior.
- Keep the old GitHub Pages deployment available during monitoring.

## 5. After cutover

- Monitor browser errors, redirects, authentication, API requests, and payment flows.
- Only retire the old deployment after the Cloudflare Pages site is stable.
