# Mvrad Digital Live Sports Stremio Addon

A sports-focused Stremio addon and Azerbaijani-first installation website for Mvrad Digital.

## Architecture

```text
mvrad-digital-live-sports-addon/
├── addon/       # Node.js Stremio addon
└── website/     # Static landing/install page
```

The website creates a one-click Stremio installation URL:

`stremio://YOUR-ADDON-DOMAIN/manifest.json`

## Run the addon

Requirements: Node.js 18+

```bash
cd addon
npm install
npm start
```

The default manifest is:

`http://localhost:7000/manifest.json`

## Configure the website

Open `website/app.js` and change:

```js
const ADDON_URL = "https://YOUR-ADDON-DOMAIN";
```

The install button will then point to:

`stremio://YOUR-ADDON-DOMAIN/manifest.json`

## Deployment

Recommended production setup:

- Host the Node.js addon on a Node-compatible service/VPS.
- Host the static website on Cloudflare Pages.
- Put the addon domain behind Cloudflare when appropriate.

Cloudflare Pages is ideal for the static website; the addon server itself needs a runtime capable of running the Node.js application.

## Stream providers

The repository intentionally contains no third-party unauthorized stream scraper or redistribution logic. Add only data/streams you are authorized to access and redistribute.

Provider modules use a normalized interface so additional authorized providers can be added later.
