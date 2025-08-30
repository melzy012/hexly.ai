# PulseScout

PulseScout is a Telegram-first SaaS platform that helps Shopify and dropshipping stores discover winning products and automate customer engagement — all in one place.

> 🚀 **Find trending products before they saturate the market and automate customer chat, directly from Telegram.**

---

## Features

- **AI-Powered Product Discovery:** Scans 1,000+ stores/ads daily to surface top-performing products.
- **Telegram Bot Interface:** Get instant product recommendations and competitor alerts.
- **Customer Chat Automation:** Answer FAQs and engage customers 24/7.
- **Web Dashboard:** View trending products, manage subscriptions, track performance.
- **Payment Integration:** Lemon Squeezy (international) & Paystack (South Africa).
- **Free-Tier Operable:** Built for Cloudflare Pages/Workers, Supabase, GitHub Actions, Upstash Redis (optional).

---

## Tech Stack

| Layer                  | Technology               | Role                                         |
|------------------------|-------------------------|----------------------------------------------|
| Frontend & Dashboard   | Cloudflare Pages + React| Landing page + client dashboard              |
| API & Webhooks         | Cloudflare Workers      | Telegram bot, payment webhooks, dashboard API|
| Database & Auth        | Supabase                | Users, subscriptions, products, events       |
| Scraping & Automation  | GitHub Actions          | Daily product discovery tasks                |
| Queue / Cache          | Upstash Redis (optional)| Heavy task queuing / caching                 |
| Bot Interface          | Telegram Bot API        | User interactions                            |
| Payments               | Lemon Squeezy/Paystack  | Checkout & activation                        |

---

## Getting Started

1. **Clone the repo**
   ```bash
   git clone https://github.com/melzy012/Hexly.AI.git
   cd Hexly.AI
   ```

2. **Configure environment variables**
   - Copy `.env.example` to `.env` in each service directory and fill in your keys.

3. **Deploy Frontend**
   - `cd frontend && npm install && npm run build`
   - Deploy to Cloudflare Pages or your custom domain.

4. **Deploy Worker**
   - `cd worker`
   - Use [Wrangler](https://developers.cloudflare.com/workers/wrangler/) for deployment.

5. **Supabase Setup**
   - Create a Supabase project and update your `.env` files.

6. **API Keys**
   - Lemon Squeezy, Paystack, Telegram Bot, Supabase, Upstash Redis (optional)—add these to `.env`.

7. **GitHub Actions**
   - The `scraper/` directory includes a workflow for daily product discovery.

---

## API Keys

All sensitive keys are managed via `.env` files. See `.env.example` for reference.

---

## Custom Domain

- You can set up your custom domain via Cloudflare Pages dashboard.

---

## Development Workflow

- API and webhooks are handled by Cloudflare Worker.
- Frontend (React) connects to Worker API and Supabase.
- Payments are integrated with Lemon Squeezy and Paystack.
- Data flows into Supabase for users, products, and events.
- (Optional) Heavy tasks use Upstash Redis for queuing.

---

## Contributing

Pull requests and issues welcome! See docs for architecture and integration notes.

---

## License

MIT