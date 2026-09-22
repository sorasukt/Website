# sorasukt.com Website

Source repository for the sorasukt.com static website and its migration from GitHub Pages to Cloudflare Pages.

## Cloudflare Pages settings

| Setting | Value |
| --- | --- |
| Production branch | `main` |
| Framework preset | None |
| Build command | Leave blank |
| Build output directory | `.` |
| Root directory | `/` |

A `wrangler.jsonc` file is included for local preview and optional Wrangler deployments.

## Local preview

```bash
npx wrangler pages dev .
```

## Migration source

The current site is hosted from [sorasukt/sorasukt.github.io](https://github.com/sorasukt/sorasukt.github.io). Keep that repository and the existing GitHub Pages deployment active until this repository has been deployed, checked on the `*.pages.dev` preview URL, and the custom domain has been verified.

See [MIGRATION.md](MIGRATION.md) for the cutover checklist.
