# GrooveNET site

The standalone marketing website for [GrooveNET](https://github.com/Public-Vinyl-Radio/groovenet), the open-source, self-hosted vinyl collection management system maintained by [Public Vinyl Radio](https://publicvinylradio.com).

Production URL: https://groovenet.publicvinylradio.com

This repository is intentionally separate from the GrooveNET application. The application repository remains the source of truth for technical documentation and releases.

## Local development

Requirements: Node.js 22+ and npm.

```bash
npm install
npm run dev
```

Run validation and create the deployable static output:

```bash
npm run check
npm run build
```

Astro writes the static production site to `dist/`.

## Project structure

```
src/
  components/     Shared site components and architecture diagram
  layouts/        Base layout, global styling, SEO metadata
  pages/          Astro routes: /, /about, /docs
public/           Favicon, social image, and the verified GrooveNET demo asset
netlify.toml      Netlify build configuration and security headers
```

Most page copy lives directly in the route files. Shared navigation and footer material lives in `src/components`; global metadata and styles are in `src/layouts/BaseLayout.astro`. When GrooveNET capabilities change, update the relevant page copy against the main [GrooveNET README](https://github.com/Public-Vinyl-Radio/groovenet#readme).

## Netlify deployment

1. In Netlify, import `Public-Vinyl-Radio/groovenet-site`.
2. Netlify reads `netlify.toml`: build command is `npm run build`, publish directory is `dist`.
3. Deploy the default branch.
4. Add `groovenet.publicvinylradio.com` as the site’s custom domain in Netlify.
5. At the DNS provider for `publicvinylradio.com`, create the DNS record Netlify provides for that hostname (normally a CNAME to the Netlify site hostname; use Netlify’s exact instruction if it differs).
6. Wait for DNS propagation and let Netlify provision HTTPS. Confirm that the canonical URL and sitemap load at the production domain.

No DNS credentials or DNS-provider assumptions are stored in this repository.

## Links

- [GrooveNET application](https://github.com/Public-Vinyl-Radio/groovenet)
- [GrooveNET releases](https://github.com/Public-Vinyl-Radio/groovenet/releases)
- [GrooveNET issues](https://github.com/Public-Vinyl-Radio/groovenet/issues)
- [Public Vinyl Radio](https://publicvinylradio.com)
