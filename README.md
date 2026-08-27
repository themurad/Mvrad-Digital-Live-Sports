# Mvrad Digital Live Sports Stremio Addon

Sports-only Stremio addon foundation by **Mvrad Digital**.

## Included

- Stremio manifest
- Live sports catalog foundation
- Football / Basketball / Tennis / UFC-MMA / Formula 1 / Boxing categories
- Azerbaijani, English and Turkish localization files
- Provider abstraction for authorized stream sources
- Health endpoint
- Node.js + Express deployment foundation

## Important

This version intentionally contains demo events and an empty provider implementation.

Only add sports data and streams that you are authorized to access, use and redistribute.

## Run locally

Requires Node.js 18+.

```bash
npm install
npm start
```

Open:

`http://localhost:7000/manifest.json`

Health:

`http://localhost:7000/health`

## Next

1. Connect an authorized sports schedule/data API.
2. Normalize live events.
3. Add authorized stream providers.
4. Add caching and health checks.
5. Deploy to Cloudflare/VPS.
6. Build the Mvrad-branded install website.
