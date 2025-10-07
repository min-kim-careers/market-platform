# Market — Second-hand PC Parts Marketplace

A marketplace for buying and selling used PC components. Focuses on clear listings, image-first presentation, and fast discovery.

## Live / Source
- [pcmarket.app](https://pcmarket.app)

## Summary
Users list items with structured specs and images. Buyers search, filter by compatibility and condition, view images and specs, and contact sellers via real-time messaging. The project includes backend APIs, a web frontend, persistent storage, a cache layer, and a production-facing proxy/tunnel.

## Core flows
- Seller: create and manage listings, upload images, mark sold.  
- Buyer: search, filter by compatibility, view details, message seller.  
- Platform: moderate listings, manage image assets, and surface item metadata.

## Technical outline (stack)

- Frontend: Next.js (Node.js, pnpm)  
- Backend: FastAPI (Python, async)  
- Database: PostgreSQL  
- Cache: Redis  
- Real-time: WebSockets for chat/notifications  
- Proxy / tunnel: Nginx and Cloudflare tunnel  
- Auth / notifications: Firebase integrations  
- Asset storage: image asset management (filesystem / object store)  
- Dev tooling: pnpm, Python virtual environment, healthchecks and runtime config via env files
