# AlertFlow — Design System & UI Specification (`ALERTFLOW_DESIGN.md`)

This document defines the visual language, color tokens, typography, floating UI card architecture, and Discord embed simulation guidelines for the **AlertFlow Bot** web platform. This design system adapts the **Soft SaaS / Layered Glass & Floating UI** paradigm (from `MUTMIZ_DESIGN.md`) while strictly aligning the color palette and branding to the official **AlertFlow Ribbon Logo & Banner** (`img_6dbaabd615b8.jpg` & `img_8a29a7a273fc.jpg`).

---

## 1. Aesthetic Direction & Brand Alignment

- **Style Paradigm**: Soft SaaS / Layered Glass & Floating Streamer UI (adapted from Mutmiz).
- **Visual Signature**:
  - Airy, ultra-clean canvas (`#F8FAFC` to `#F9F8FF`) with ambient violet/cyan mesh backdrops.
  - Luminous **Purple-to-Cyan Gradients** (`#7C3AED` → `#3B82F6` → `#06B6D4`) inspired directly by the ribbon "A" brand mark.
  - Glowing **Electric Cyan & Purple Pill Buttons** (`#06B6D4` to `#3B82F6` and `#8B5CF6`), replacing generic pink CTAs with high-velocity streaming accents.
  - Multi-layered floating white UI widgets (`rounded-2xl`, `rounded-[32px]`) casting soft, diffused purple-cyan tinted ambient shadows (`rgba(124, 58, 237, 0.12)`).
  - Signature diagonal top edge geometry via `.hero-slope-bg` clip-path (`polygon(0 18%, 100% 0, 100% 100%, 0 100%)`).
  - Tilted device & Discord embed breakouts (`-rotate-12 lg:-my-16`) demonstrating real-time mobile and desktop notifications.

---

## 2. Color Tokens (AlertFlow Logo Palette)

| Token Name | Hex / Gradient Value | Tailwind Class / Config | Usage |
| :--- | :--- | :--- | :--- |
| **Canvas Background** | `#F8FAFC` / `#F9F8FF` | `bg-canvas` (`#F8FAFC`) | Main page canvas |
| **Surface White** | `#FFFFFF` | `bg-white` | Floating UI cards, phone frame, simulator base |
| **Surface Soft Tint** | `#F1F5F9` / `#F5F3FF` | `bg-slate-100` / `bg-purple-50/60` | Device mockup inner screens & container backdrops |
| **Primary Violet** | `#7C3AED` | `text-[#7C3AED]` / `bg-[#7C3AED]` | Focal words in headlines, primary badges |
| **Electric Blue (Mid)** | `#3B82F6` | `text-[#3B82F6]` / `bg-[#3B82F6]` | Bridge gradient for text, active indicators |
| **Luminous Cyan (End)** | `#06B6D4` | `text-[#06B6D4]` / `bg-[#06B6D4]` | Luminous brand accent, live radar beacons, CTA glow |
| **Bell Sky Blue** | `#38BDF8` | `text-[#38BDF8]` / `bg-[#38BDF8]` | Inner notification bell icon, sound wave arcs |
| **Banner Brand Gradient**| `linear-gradient(90deg, #7C3AED 0%, #3B82F6 50%, #06B6D4 100%)` | `bg-gradient-to-r from-[#7C3AED] via-[#3B82F6] to-[#06B6D4]` | Sloped Hero banner & tilted-card CTA banner |
| **Cyan CTA Gradient** | `linear-gradient(90deg, #06B6D4 0%, #3B82F6 100%)` | `bg-gradient-to-r from-[#06B6D4] to-[#3B82F6]` | Primary pill buttons (`Undang ke Server`), telemetry badges |
| **Purple CTA Gradient** | `linear-gradient(90deg, #8B5CF6 0%, #6366F1 100%)` | `bg-gradient-to-r from-[#8B5CF6] to-[#6366F1]` | Secondary action pills & status buttons |
| **Text Navy (Primary)** | `#0F172A` / `#1E1B4B` | `text-slate-900` / `text-[#1E1B4B]` | Primary headlines, card titles, author attribution |
| **Text Slate (Muted)** | `#64748B` / `#94A3B8` | `text-slate-500` / `text-slate-400` | Body copy, streamer handles, timestamps, metadata |
| **Discord Blurple** | `#5865F2` | `bg-[#5865F2]` | Official Discord buttons, verified `APP` badges |
| **Live Stream Red** | `#EF4444` | `text-[#EF4444]` / `bg-[#EF4444]` | "LIVE NOW" indicators, YouTube live borders |
| **TikTok Magenta** | `#FE2C55` | `text-[#FE2C55]` | TikTok post badges & video cards |

---

## 3. Typography Stack

- **Primary Sans (`font-sans`)**: `'Plus Jakarta Sans', 'Inter', sans-serif` — modern geometric sans-serif with crisp `700` (Bold) and `800` (ExtraBold) weights for headings.
- **Numeric & Terminal Mono (`font-mono`)**: `'JetBrains Mono', monospace` — used for `/notif` commands, latency telemetry (`< 8s`), and time trackers.

| Element | Desktop Size | Mobile Size | Weight | Styling Notes |
| :--- | :--- | :--- | :--- | :--- |
| **Hero H1** | `48px` (`3rem`) | `36px` (`2.25rem`) | `800` (ExtraBold) | Dual-tone: `#1E1B4B` + Gradient Text (`#7C3AED` to `#06B6D4`) |
| **Section H2** | `32px` (`2rem`) | `24px` (`1.5rem`) | `800` (ExtraBold) | Navy with vibrant gradient focal words |
| **Stat Counter** | `36px` (`2.25rem`) | `30px` (`1.875rem`) | `800` (ExtraBold) | Violet-to-Cyan gradient text (`8+`, `500K+`) |
| **Card H3** | `15px–16px` | `14px` | `700–800` | Crisp `#1E1B4B` on light cards, white on gradient banners |
| **Body Copy** | `14px–15px` | `13px–14px` | `400–500` | `text-slate-500` on light, `text-cyan-100` on gradient banners |
| **Discord Chat Text** | `15px` (`0.9375rem`) | `14px` (`0.875rem`) | `400` (Regular) | Exact Discord desktop chat font |

---

## 4. Radii, Shadows & Geometric Clip Paths

| Token | CSS / Utility Definition | Application |
| :--- | :--- | :--- |
| **Banner Radius** | `rounded-[36px]` (`2.25rem`) | Sloped Hero gradient banner & Section 4 CTA banner |
| **Device Frame Radius** | `rounded-[38px]` (Hero) / `rounded-[32px]` (Tilted) | Smartphone & Discord UI mockups |
| **Floating UI Card Radius**| `rounded-2xl` (`1rem`) | `Radar Status`, `Watchlist`, `Live Ping` cards |
| **CTA Button Radius** | `rounded-full` | Cyan & Purple `Undang AlertFlow` pill buttons |
| **Shadow Card** | `0 14px 34px -8px rgba(30, 27, 75, 0.08)` | Floating white UI cards (`shadow-card border border-slate-100`) |
| **Shadow Soft** | `0 20px 50px -12px rgba(124, 58, 237, 0.14)`| Section containers (`shadow-soft`) |
| **Shadow Cyan Glow** | `0 10px 24px -4px rgba(6, 182, 212, 0.45)` | Cyan `Undang Bot` CTA buttons |
| **Shadow Purple Glow** | `0 20px 45px -10px rgba(124, 58, 237, 0.35)`| Gradient brand banners |
| **Hero Slope Clip Path** | `clip-path: polygon(0 18%, 100% 0, 100% 100%, 0 100%)` | Signature diagonal top edge on Hero banner |

---

## 5. Official OAuth2 Bot Invite Link

```text
https://discord.com/oauth2/authorize?client_id=1524069345502826696&permissions=275415026688&integration_type=0&scope=bot+applications.commands
```

---

## 6. Real Production Message Specifications (Discord Verbatim)

1. **🎬 Video TikTok Baru (@budimanletos)**:
   - Header: `Alert Flow` (hijau `#57F287`) + badge `APP` (centang aplikasi Discord).
   - Pesan: `@here 🎬 **Video TikTok Baru!** dari @budimanletos\n\n💬 *BUDIMAN SAAT INI MENJADI SALAH SATU PEGEDAR LEM DI PINGGIRAN KOTA ROXWOOD...*\n\nhttps://www.tiktok.com/@budimanletos/video/7697676392569359636`
   - Embed: Border kiri merah, label `TikTok • Budiman Letos`, thumbnail grafis *EVA INDOPRIDE CHIEF & GEMBONG LEM BUDIMAN KARTEL*.

2. **🔴 YouTube Live (@icventusmilkuat)**:
   - Pesan: `@here 🔴 **ic ventus milkuat** sedang LIVE di YouTube!`
   - Embed: Border merah YouTube, author `ic ventus milkuat (@icventusmilkuat)`, judul `🎬 tes #satumimpirp #indopride #flywheels`, link `▶️ Tonton Sekarang`, thumbnail 16:9 karakter GTA RP, footer `YouTube Live`.

3. **🔴 TikTok Live (@brenzgogogo)**:
   - Pesan: `@here 🔴 **brenzgogogo** sedang LIVE sekarang! Tonton di: https://www.tiktok.com/@brenzgogogo/live`
   - Card Preview: Provider `TikTok`, title `Mr.Brenz is LIVE | TikTok`.
