<div align="center">

# SOT Stockholm

**A digital flagship for a Stockholm-based fragrance house and lifestyle label exploring contemporary design, functional aesthetics, and thoughtful materiality.**

[VIEW SITE](https://sotstockholm.se/)

</div>

---

## About SOT

SOT is a Stockholm-based fragrance house and lifestyle label founded in 2023. Rooted in research and defined by shifting ideas, the brand explores the intersection of contemporary design, functional aesthetics, and thoughtful materiality.

Its collections extend beyond fragrance into objects, garments, printed matter, film, and collaborative projects. Each release is guided by restraint, curiosity, and a commitment to purposeful design.

## The digital experience

The website translates SOT's physical world—the atmosphere, ritual, and material character of the brand—into a slow and visually led digital experience.

- Responsive, mixed-media landing experience using photography and film
- Editorial project archive for campaigns, collaborations, and releases
- Individual project pages with image galleries, video, and keyboard navigation
- Brand story and direct contact information
- Newsletter signup in the footer and a consent-aware popup
- Cookie preference interface with necessary, performance, and marketing categories
- Responsive navigation and layouts across desktop and mobile
- Custom typography and a restrained monochrome visual system
- Product catalogue, product detail, cart, and checkout interfaces prepared for future releases

## Commerce status

The storefront is currently set to a closed state while retaining the underlying product, cart, and checkout interfaces in the codebase. The checkout is a front-end prototype and is not connected to Klarna, Swish, a card processor, inventory management, or order fulfilment.

This distinction is intentional: the repository contains the foundation for future commerce, but the current live experience is primarily a brand and project platform.

## Tech stack

| Area | Technology |
| --- | --- |
| Language | TypeScript |
| UI | React 19, React DOM |
| Build tooling | Vite 5, SWC |
| Routing | React Router 6 |
| State and data | React Context, TanStack Query |
| Components | Radix UI primitives, cmdk |
| Forms and validation | React Hook Form, Zod |
| Galleries and carousels | Embla Carousel |
| Styling | CSS Modules, global CSS, custom fonts |
| UI feedback and icons | Sonner, Lucide React |
| Forms and newsletter | Web3Forms |
| Analytics | Vercel Analytics |
| Server scaffolding | Hono on Node.js |
| Data scaffolding | Kysely, PostgreSQL via postgres.js |
| Deployment configuration | Vercel rewrites, static SPA fallback |

## Getting started

### Requirements

- Node.js 18–20
- npm 9 or later

### Installation

```bash
git clone https://github.com/adrianspata/sot-stockholm.git
cd sot-stockholm
npm install
```

Start the development server:

```bash
npm run dev
```

Vite will print the local development URL in the terminal.

## Available scripts

| Command | Description |
| --- | --- |
| `npm run dev` | Starts the Vite development server |
| `npm run build` | Creates an optimized production build in `dist/` |
| `npm run preview` | Serves the production build locally for preview |
| `npm run server` | Starts the Hono server scaffold; additional local server configuration is required |

## Project structure

```text
.
├── components/             # Shared UI, navigation, forms, cart and galleries
├── helpers/                # Currency, newsletter, theme and data helpers
├── pages/                  # Route-level pages and project/shop detail views
├── public/
│   ├── fonts/              # Local type assets
│   ├── images/             # Campaign, product and editorial imagery
│   └── videos/             # Brand and project films
├── styles/                 # Global styles and route/component CSS Modules
├── App.tsx                 # Routes, cart context and global application features
├── index.tsx               # React entry point
├── server.ts               # Hono server scaffold and static-file handler
├── vercel.json             # SPA rewrite configuration
└── vite.config.ts          # Vite and SWC configuration
```

## Routes

| Route | Purpose |
| --- | --- |
| `/` | Mixed-media landing page |
| `/about` | SOT's story and creative approach |
| `/projects` | Campaign and project archive |
| `/projects/:projectId` | Individual project story and media gallery |
| `/shop` | Store status or product catalogue |
| `/shop/product/:productId` | Product information and imagery |
| `/checkout` | Prototype checkout interface |
| `/contact` | Contact information |

## Forms and configuration

The current contact and newsletter flows submit directly to Web3Forms from the client. Their access key is currently present in the source code. Before reusing or extending the project, move the key into an environment variable and add abuse protection appropriate for a public form.

The repository also contains Hono, Kysely, and PostgreSQL scaffolding. That server-side path requires additional configuration and endpoint files and is not part of the default Vite development flow.

## Production

Create and preview a production build with:

```bash
npm run build
npm run preview
```

The generated site is written to `dist/`. The included Vercel and `_redirects` configurations provide the SPA fallback required for client-side routes.

## Status

SOT Stockholm is live and evolving. The website currently acts as the brand's digital home and project archive, with commerce infrastructure prepared for future releases.
