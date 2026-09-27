# Minimalist Hero Section

A clean, minimalist landing-page hero section for **"NotionPro"** — a demo storefront for premium Notion templates. Features a slim navbar with a CTA button and a conversion-focused hero block: radial-gradient backdrop, star-rated social proof with avatar cluster, serif headline, and CTA buttons. Ships with three hero variants to compare and reuse.

## Features

- **Minimalist hero layout** — centered headline, subcopy, dual CTA buttons, and a social-proof row (star rating + avatar stack + review count)
- **Three hero variants** — `hero7.tsx` (base), `hero7-base.tsx`, and `animated-hero7.tsx` (Framer Motion entrance animations); swap them in `app/page.tsx` to try different styles
- **Slim navbar** — logo + "Get Templates" CTA, ready to drop into any page
- **Framer Motion animations** — smooth entrance choreography on the animated variant
- **Radial gradient backdrop** — soft indigo-to-white wash drawn with pure CSS
- **Fully parameterized** — heading, description, button, and reviews are all props with sensible defaults, so the hero is reusable as a component
- **Dark mode theming** — `next-themes` provider with shadcn/ui token-based colors
- **Responsive** — stacks gracefully on mobile

## Tech Stack

- **Framework:** [Next.js 15](https://nextjs.org/) (App Router, static export via `output: "export"`)
- **Language:** TypeScript
- **Styling:** Tailwind CSS 4 + shadcn/ui + Radix UI primitives
- **Animation:** Framer Motion
- **Icons:** Lucide React
- **Theming:** next-themes

## Quick Start

### Prerequisites

- Node.js 18+ and npm/pnpm

### Install & Run

```bash
# install dependencies
pnpm install
# or: npm install

# start the dev server
pnpm dev
```

Open [http://localhost:3000/minimalist-hero-section](http://localhost:3000/minimalist-hero-section) in your browser.

### Build (static export)

```bash
pnpm build
```

This produces a fully static site in `out/`, ready to host anywhere (GitHub Pages, Cloudflare Pages, Netlify, Vercel).

## Project Structure

```
├── app/
│   ├── page.tsx          # Home page: navbar + hero composition
│   ├── layout.tsx        # Root layout, fonts, metadata, theme provider
│   └── globals.css       # Tailwind + theme tokens
├── components/
│   ├── hero7.tsx            # Hero variant: base (Framer Motion)
│   ├── hero7-base.tsx       # Hero variant: plain base
│   ├── animated-hero7.tsx   # Hero variant: animated
│   ├── navbar.tsx           # Slim navbar with CTA
│   ├── theme-provider.tsx
│   └── ui/               # shadcn/ui primitives (avatar, button, ...)
├── lib/
│   └── utils.ts          # clsx + tailwind-merge helper
├── next.config.mjs       # output: "export", images unoptimized
└── components.json       # shadcn/ui config
```

## Environment Variables

None. This is a pure UI demo — no backend, no API keys, no third-party services. The review avatars load from shadcnblocks' CDN placeholders; replace the `avatars` prop with your own images for production.

## Deployment Notes

- The site is a **static export** (`output: "export"` in `next.config.mjs`) — no server, no API routes, no server actions required.
- **GitHub Pages:** `basePath: "/minimalist-hero-section"` is set for the project-pages subpath (`https://girishlade111.github.io/minimalist-hero-section/`). **Remove `basePath` when deploying to a root domain or Vercel.**
- **Vercel:** deploy directly — no changes needed beyond removing `basePath` (originally generated on [v0.app](https://v0.app)).
- Images are marked `unoptimized: true` so `next/image` optimization is skipped during static export.

## Notes

- TypeScript and ESLint errors are ignored during builds (`ignoreBuildErrors` / `ignoreDuringBuilds`) — this matches the original v0.app project settings.
- The hero components are derived from shadcnblocks' "hero7" block; avatar images point at the shadcnblocks CDN as placeholders.

---

Built by Girish Lade — https://ladestack.in
