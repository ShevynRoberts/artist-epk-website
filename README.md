# Shevyn Roberts — Official EPK

A premium, booking-ready Electronic Press Kit website for Shevyn Roberts —
award-winning singer, songwriter, actress, and six-time National Solo Dance
Champion.

Built with **Next.js 14 (App Router)**, **TypeScript**, and **Tailwind CSS**.
Designed for booking agents, managers, labels, press, and award submissions.

---

## Quick start

```bash
npm install
npm run dev          # http://localhost:3000
npm run build        # production build
npm start            # serve the build locally
```

Requires Node.js **18.18+** (Node 20 LTS recommended).

---

## Project structure

```
app/
  layout.tsx         # fonts, SEO metadata, JSON-LD schema, OpenGraph
  page.tsx           # composes all sections in order
  globals.css        # design tokens + Tailwind layers
  sitemap.ts         # auto-generated /sitemap.xml
  robots.ts          # auto-generated /robots.txt
components/
  Nav.tsx Hero.tsx About.tsx Music.tsx Videos.tsx
  Gallery.tsx Press.tsx Highlights.tsx Contact.tsx Footer.tsx
  ui/                # Button, SectionHeader
lib/
  content.ts         # SINGLE SOURCE OF TRUTH for all copy and links
public/
  images/            # release artwork (ships with site)
  press-photos/      # drop editorial press photos here
  logo.jpg           # Shevyn Roberts brush-script logo
  EPK updated 2.pdf  # press kit PDF (replace with a new file to update)
```

---

## Editing content (no developer required)

**Almost all copy lives in `lib/content.ts`.** Open it, edit, save, redeploy.

| Want to change…                         | Where to edit                                       |
| --------------------------------------- | --------------------------------------------------- |
| Booking / press email                   | `lib/content.ts` → `SITE.bookingEmail`, `pressEmail`|
| Short bio / full bio                    | `lib/content.ts` → `BIO.short`, `BIO.full[]`        |
| Awards list                             | `lib/content.ts` → `AWARDS[]`                       |
| Press quotes                            | `lib/content.ts` → `PRESS_QUOTES[]`                 |
| Career highlights                       | `lib/content.ts` → `HIGHLIGHTS[]`                   |
| Spotify / Apple Music links and embeds  | `lib/content.ts` → `SOCIAL`, `STREAMING`            |
| Instagram / Facebook / TikTok links     | `lib/content.ts` → `SOCIAL`                         |
| Hero photo                              | `components/Hero.tsx` (replace `/images/...` src)   |
| Gallery photos                          | `components/Gallery.tsx` → `TILES` array            |
| YouTube official video                  | `components/Videos.tsx` (search "TODO")             |

### Adding press photos

See `public/press-photos/README.md`. Drop files in that folder, then add
entries to the `TILES` array in `components/Gallery.tsx`.

---

## Deployment — Vercel (recommended)

1. Create a GitHub repo and push this project.
2. Go to [vercel.com/new](https://vercel.com/new) and import the repo.
3. Framework preset auto-detects **Next.js**. Click **Deploy**. Done.
4. Vercel issues a free `*.vercel.app` URL immediately and an SSL certificate.

Alternative: Netlify works equally well. Use the build command `next build`
