<div align="center">

<img src="worker/assets/mvrad-logo.png" width="120" alt="Mvrad Digital">

# Mvrad Digital Live Sports

### 🇦🇿 Azərbaycan dili dəstəyi ilə müasir Stremio idman əlavəsi

[![Install in Stremio](https://img.shields.io/badge/⚡%20STREMIO--YA%20ƏLAVƏ%20ET-25D875?style=for-the-badge&logo=stremio&logoColor=07111F)](#quraşdırma)
[![Node](https://img.shields.io/badge/Node.js-18%2B-07111F?style=for-the-badge&logo=node.js&logoColor=25D875)](https://nodejs.org/)
[![Cloudflare](https://img.shields.io/badge/Cloudflare-Workers-07111F?style=for-the-badge&logo=cloudflare&logoColor=32D8FF)](https://workers.cloudflare.com/)

**Mvrad Digital Live Sports** — yalnız idmana fokuslanan, Azərbaycan dili ilə hazırlanmış Stremio addon layihəsidir.

</div>

---

## 🏆 Nədir?

Mvrad Digital Live Sports Stremio daxilində canlı idman məzmununu vahid interfeysdə təqdim etmək üçün hazırlanır.

**Kateqoriyalar**

| ⚽ Futbol | 🏀 Basketbol | 🎾 Tennis |
|---|---|---|
| 🥊 UFC / MMA | 🏎️ Formula 1 | 🥋 Boks |

### ✨ Xüsusiyyətlər

- 🇦🇿 Azərbaycan dili
- 🌍 Çoxdilli metadata üçün hazır arxitektura
- ⚡ Bir kliklə Stremio quraşdırması
- 🏟️ Yalnız idman məzmunu
- 🧩 Modul provider sistemi
- ☁️ Cloudflare Workers üçün hazır runtime
- 📱 Mobil uyğun Mvrad landing page
- 🌙 Premium dark-sports dizaynı
- 🔌 Gələcək provider-lərin əlavə edilməsi üçün təmiz API

---

## ⚡ Quraşdırma

> **Production URL deploy edildikdən sonra bu düymə birbaşa Stremio tətbiqini açır.**

### [⚡ STREMIO-YA ƏLAVƏ ET](#)

`stremio://YOUR-DEPLOYED-ADDON-DOMAIN/manifest.json`

Stremio addon quraşdırma keçidləri `stremio://.../manifest.json` formatından istifadə edir. citehttps://github.com/Stremio/stremio-addon-sdk/blob/master/docs/advanced.md

---

## 🎨 Mvrad Design System

**Visual direction**

```text
Background     #050B14
Panel          #0A1422
Deep Panel     #0D1B2B
Neon Green     #25D875
Emerald        #119B59
Cyan           #32D8FF
Blue           #168CFF
```

Dizayn məqsədi: **premium sports dashboard + modern streaming product**, böyük logo və həddindən artıq neon əvəzinə balanslaşdırılmış yaşıl/cyan işıqlandırma.

---

## 🧠 Arxitektura

```text
                    ┌─────────────────────┐
                    │   Mvrad Web Page    │
                    │  Install / Discover │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │       Stremio       │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   /manifest.json    │
                    └──────────┬──────────┘
                               │
                 ┌─────────────┴─────────────┐
                 ▼                           ▼
        ┌────────────────┐          ┌────────────────┐
        │ Sports Catalog │          │ Stream Resolver │
        └────────────────┘          └───────┬────────┘
                                            │
                                  ┌─────────┴─────────┐
                                  ▼                   ▼
                           Provider A            Provider B
                           (authorized)          (authorized)
```

Provider sistemi qəsdən modul saxlanılıb. Yalnız istifadə və yayım hüququ olan mənbələr əlavə edilməlidir.

---

## 📁 Repository

```text
mvrad-digital-live-sports-addon/
│
├── README.md
│
├── worker/
│   ├── src/
│   │   └── index.js
│   ├── assets/
│   │   └── mvrad-logo.png
│   ├── package.json
│   ├── wrangler.toml
│   └── .gitignore
│
└── website/
    └── README.md
```

---

## 🔐 Provider policy

Bu repository üçüncü tərəf saytlarından icazəsiz yayım linklərini çıxaran scraper/proxy daxil etmir.

Provider interface real, hüquqi olaraq istifadəsinə icazə verilən idman məlumatı və stream mənbələrini əlavə etməyə hazırdır.

---

<div align="center">

### Mvrad Digital
**Live Sports. One place.**

🇦🇿 Built with Azerbaijani-first UX.

</div>
