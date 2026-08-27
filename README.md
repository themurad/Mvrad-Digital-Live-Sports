<div align="center">

<img src="website/assets/logo.svg" width="76" alt="Mvrad Digital">

# Mvrad Digital Live Sports

**Stremio addon** — rəsmi olaraq pulsuz yayımlanan canlı idmanı bir yerə toplayır.
Azərbaycan dilində interfeys.

[![Quraşdır](https://img.shields.io/badge/⬇_STREMIO--DA_QURAŞDIR-A8E832?style=for-the-badge&logoColor=041209&labelColor=041209)](https://YOUR-ADDON-DOMAIN/)
&nbsp;
[![Sayt](https://img.shields.io/badge/Sayt-22D3EE?style=for-the-badge&labelColor=041209)](https://YOUR-ADDON-DOMAIN/)

![Node](https://img.shields.io/badge/Node-18%2B-3B82F6?style=flat-square&labelColor=0A1120)
![Stremio](https://img.shields.io/badge/Stremio-Addon_SDK-7C3AED?style=flat-square&labelColor=0A1120)
![License](https://img.shields.io/badge/License-MIT-A8E832?style=flat-square&labelColor=0A1120)

</div>

---

## Nədir bu?

Stremio üçün idman addon-u. Hüquq sahibinin **özünün pulsuz yaydığı** rəsmi
mənbələri Stremio-nun `Discover` bölməsində bir kataloqda toplayır — CBC Sport,
İdman TV, FIFA+, UEFA.tv, Red Bull TV.

İnterfeys və kataloq adları Azərbaycan dilindədir. Sayt AZ / EN / RU dəstəkləyir.

> **Qanunilik.** Bu addon heç bir yayımı saxlamır, kodlaşdırmır və yenidən
> yayımlamır. Ödənişli və ya eksklüziv hüquqla qorunan yayımlar (Çempionlar
> Liqası, La Liga, UFC, Formula 1 və s.) **daxil deyil və əlavə olunmayacaq.**

---

## Quruluş

```
.
├── addon/                  Node.js Stremio addon
│   ├── server.js           catalog / meta / stream handler-ləri
│   └── src/
│       ├── manifest.js     kataloq adları və kateqoriyalar
│       ├── sources.json    ← icazən olan mənbələri bura yaz
│       └── providers/      modul provayderlər
│           ├── index.js    registr + keş
│           ├── manual.js   sources.json oxuyur
│           └── redbull.js  canlı API nümunəsi
│
└── website/                statik sayt (Cloudflare Pages)
    ├── index.html
    ├── styles.css
    ├── i18n.js             AZ / EN / RU tərcümələr
    ├── app.js              ← ADDON_DOMAIN-i burada dəyiş
    └── assets/logo.svg
```

---

## Addon-u işə sal

Node.js 18+ lazımdır.

```bash
cd addon
cp .env.example .env
npm install
npm start
```

Manifest: `http://127.0.0.1:7000/manifest.json`

Yerli olaraq sınamaq üçün Stremio-da bu linki əlavə et:
`stremio://127.0.0.1:7000/manifest.json`

---

## Mənbə əlavə et

`addon/src/sources.json` faylını aç, siyahıya yeni sətir əlavə et:

```json
{
  "id": "kanal-adi",
  "name": "Kanal adı",
  "category": "futbol",
  "description": "Qısa təsvir",
  "country": "AZ",
  "language": "az",
  "url": "https://.../stream.m3u8",
  "externalUrl": false,
  "enabled": true
}
```

`category` bunlardan biri olmalıdır:
`futbol` · `basketbol` · `motorsport` · `doyus` · `ekstremal` · `arxiv`

`externalUrl: true` qoysan, Stremio linki brauzerdə açır (birbaşa oxutmur) —
rəsmi saytlara yönləndirmək üçün ən təhlükəsiz variant.

**Yalnız yaymağa icazən olan mənbələri əlavə et.**

---

## Saytı konfiqurasiya et

`website/app.js` faylının başındakı sətri dəyiş:

```js
const ADDON_DOMAIN = "sports.mvraddigital.com";   // protokolsuz, / olmadan
```

Quraşdırma düyməsi avtomatik bu linkə çevriləcək:
`stremio://sports.mvraddigital.com/manifest.json`

Stremio quraşdırılmayıbsa, düymə `web.stremio.com`-a keçir.

Bu README-dəki iki badge linkini də öz domeninlə əvəz et
(`YOUR-ADDON-DOMAIN` yazılan yerlər).

---

## Yayımlama

| Hissə | Harada |
|---|---|
| `website/` | Cloudflare Pages — build command yoxdur, output directory: `website` |
| `addon/` | Node işlədən hosting (Railway, Render, Fly.io, VPS) |

Addon domenini Cloudflare-in arxasına qoymaq tövsiyə olunur.

Cloudflare Pages üçün: repo-nu bağla, **Framework preset: None**,
**Build output directory: `website`**.

---

## Lisenziya

MIT — bax [LICENSE](LICENSE).

Bütün marka adları və yayım hüquqları öz sahiblərinə aiddir.
