# Shopify MCP Starter Kit — Manage Shopify with AI

> **This is a recipe repo.** The Synter MCP server itself lives at [Synter-Media-AI/mcp-server](https://github.com/Synter-Media-AI/mcp-server): create, launch, and optimize campaigns across 16 ad platforms, with one-click install in Cursor, Claude, ChatGPT, and VS Code. Issues, releases, and ⭐ go there.


[![MCP Compatible](https://img.shields.io/badge/MCP-compatible-blue)](https://modelcontextprotocol.io)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Platform: Shopify](https://img.shields.io/badge/Platform-Shopify-7AB55C)](https://www.shopify.com)

**Turn your Shopify store data into advertising intelligence.** Open this repo in Amp, Cursor, or VS Code and query Shopify orders, products, and customers with AI — generate product feeds for Google PMax, sync customer emails for remarketing, and identify your best-selling products for ad campaigns.

---

## Install

[![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/en/install-mcp?name=synter-ads&config=eyJ1cmwiOiJodHRwczovL21jcC5zeW50ZXJhaS5jb20ifQ==)
[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install_Synter-0098FF?logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=synter-ads&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.synterai.com%22%7D)

- **Cursor / VS Code:** click a button above, or open this repo — it ships `.cursor/mcp.json` and `.vscode/mcp.json`.
- **Claude Code:** this repo ships `.mcp.json`; or run:
  ```bash
  claude mcp add --transport http synter-ads https://mcp.synterai.com
  ```
- **Codex:**
  ```bash
  codex mcp add synter-ads --url https://mcp.synterai.com
  codex mcp login synter-ads
  ```
- **Claude Desktop:** copy `claude_desktop_config.json` into your Claude config directory (macOS: `~/Library/Application Support/Claude/`, Windows: `%APPDATA%\Claude\`) and replace the placeholder API key.

Your client opens Synter sign-in in the browser (OAuth). New here? Create an account at https://synterai.com/sign-up. Headless/CI fallback: send `X-Synter-Key` with a key from https://synterai.com/developer.

The MCP server itself: https://github.com/Synter-Media-AI/mcp-server

---

## Why Shopify + AI for Advertising?

Shopify powers 4.7 million online stores worldwide. Every order, customer, and product in your Shopify store is an advertising signal waiting to be used.

Your order data tells you which products sell best (feature them in ads), which customers are most valuable (build Lookalike audiences), and which products are frequently bought together (create bundle campaigns). Your product catalog feeds directly into Google Shopping and Meta Dynamic Product Ads.

The friction is in the data pipeline. Exporting Shopify data, formatting product feeds, mapping customer segments, and uploading audiences to each ad platform is manual and error-prone. An AI agent automates the entire pipeline.

**Best for:** Shopify store owners, ecommerce brands, dropshippers, anyone using Shopify who runs paid ads on Google, Meta, or TikTok.

---

## What You Can Do

| Capability | Example |
|-----------|---------|
| **Product Feed** | "Generate a Google Merchant Center product feed from my Shopify catalog" |
| **Best Sellers** | "What are my top 10 products by revenue this month?" |
| **Customer Segments** | "Find customers who've ordered 3+ times — they're my VIPs" |
| **Order Analysis** | "What's my average order value? Has it changed this quarter?" |
| **Inventory Alerts** | "Which products are low stock and currently being advertised?" |
| **Product Bundles** | "Which products are frequently purchased together?" |
| **Customer Sync** | "Sync my customer email list to Google Ads for Customer Match" |
| **Revenue Reports** | "Show me daily revenue for the last 30 days" |
| **Collection Performance** | "Which product collection drives the most revenue?" |
| **Refund Analysis** | "What's my return rate by product? Am I advertising products people return?" |

---

## Example Conversations

### 1. Product Feed for Google Performance Max

> **You:** I want to run Google Shopping ads. How do I get my products into Google?
>
> **Agent:** I'll generate a product feed from your Shopify catalog for Google Merchant Center. Let me pull your products...
>
> **Catalog summary:**
> - 247 active products across 12 collections
> - Average price: $42.50
> - 31 products are out of stock (I'll exclude these)
> - 216 products ready for the feed
>
> **Feed generation:**
> - Title: Optimized for search (brand + product name + key attribute)
> - Description: First 150 characters of your Shopify description
> - Price: Current Shopify price (auto-updates with sales)
> - Image: Primary product image URL
> - GTIN/MPN: Pulled from Shopify metafields where available
> - Availability: Only in-stock products
>
> **Performance Max recommendation:**
> Once the feed is in Merchant Center, I'll create a PMax campaign with:
> - Asset group featuring your top 5 best-sellers
> - Headlines and descriptions from your product pages
> - $50/day budget targeting the US
> - Maximize Conversions bidding (or Target ROAS after 30+ conversions)
>
> **Important:** Your product images need to be on a white or clean background for Google Shopping. Products with lifestyle images get lower approval rates. I see 18 products with lifestyle-only images — consider adding white-background variants.

### 2. Identifying Your Advertising Sweet Spot

> **You:** Which products should I advertise? I have 247 products and limited budget.
>
> **Agent:** Let me analyze your Shopify data to find the products most worth advertising...
>
> **Product analysis (last 90 days):**
>
> | Product | Revenue | Orders | Margin | Return Rate | Ad Verdict |
> |---|---|---|---|---|---|
> | Premium Serum | $18,400 | 312 | 72% | 3% | 🏆 Top pick |
> | Daily Moisturizer | $14,200 | 487 | 65% | 2% | 🏆 Top pick |
> | Travel Kit Bundle | $12,800 | 180 | 78% | 1% | 🏆 Top pick |
> | Face Mask (Value) | $8,900 | 890 | 25% | 8% | ⚠️ Low margin |
> | Luxury Eye Cream | $6,200 | 62 | 82% | 12% | ⚠️ High returns |
> | Sample Set | $3,100 | 620 | 15% | 1% | ❌ Loss leader |
>
> **Your advertising sweet spot:**
> - **Premium Serum:** High revenue, high margin (72%), low returns → your best ad product
> - **Daily Moisturizer:** Highest volume (487 orders), solid margin → volume driver
> - **Travel Kit Bundle:** Highest margin (78%), lowest returns → excellent for new customer acquisition
>
> **Avoid advertising:**
> - **Face Mask (Value):** 25% margin means you can't afford $5+ CPAs. Keep as an upsell, not an acquisition product.
> - **Sample Set:** 15% margin is a loss leader. Great for email capture, terrible as a paid ad product.
>
> **My recommendation:** Advertise the top 3 products. Use the Sample Set as a lead magnet in email popups (free, not paid).

### 3. Customer Segmentation for Ad Audiences

> **You:** Segment my Shopify customers for different ad campaigns.
>
> **Agent:** Pulling customer purchase data from Shopify...
>
> **Customer segments:**
>
> | Segment | Customers | Avg LTV | Ad Strategy |
> |---|---|---|---|
> | VIPs (top 10% by revenue) | 480 | $340 | Lookalike seed for Meta → find more like them |
> | Repeat Buyers (2+ orders) | 1,890 | $128 | Upsell/cross-sell → show new products |
> | One-Time Buyers | 8,200 | $48 | Retarget → bring back for 2nd purchase |
> | Cart Abandoners (last 30 days) | 1,240 | — | Retarget → recover lost sales |
> | Lapsed (no order in 6 months) | 3,100 | $72 | Win-back → "We miss you" + offer |
>
> **Recommended campaign structure:**
>
> 1. **Acquisition:** Meta Lookalike from 480 VIPs → cold audience → your bestsellers
> 2. **Reactivation:** Retarget 8,200 one-time buyers → "Your favorites are back in stock"
> 3. **Cart Recovery:** Retarget 1,240 abandoners → show the exact products they left behind
> 4. **Win-Back:** Retarget 3,100 lapsed → "15% off — we miss you"
> 5. **Upsell:** Target 1,890 repeat buyers → new product launches and bundles
>
> Budget allocation: Acquisition 50%, Reactivation 20%, Cart Recovery 15%, Win-Back 10%, Upsell 5%.

### 4. Frequently Bought Together Analysis

> **You:** Which products are bought together? I want to create bundle ads.
>
> **Agent:** Analyzing multi-item orders from Shopify...
>
> **Top product pairings (by co-purchase frequency):**
>
> | Product A | Product B | Co-Purchased | % of A's Orders |
> |---|---|---|---|
> | Daily Moisturizer | Premium Serum | 189 times | 39% |
> | Premium Serum | Eye Cream | 124 times | 40% |
> | Daily Moisturizer | SPF 50 | 98 times | 20% |
> | Cleanser | Toner | 87 times | 34% |
> | Travel Kit | Sample Set | 72 times | 40% |
>
> **Bundle ad opportunities:**
> 1. **"Complete Routine" Bundle:** Moisturizer + Serum + Eye Cream → 40% of serum buyers want all three
> 2. **"Daily Essentials" Bundle:** Moisturizer + SPF → natural pairing
> 3. **"Starter Set" Bundle:** Cleanser + Toner → entry point for new customers
>
> **Ad creative suggestion:** "Stop buying skincare one product at a time. Get the Complete Routine for $X (save 15%)" with a carousel showing the before/after routine.
>
> Want me to create product bundles in Shopify and generate ad creatives?

### 5. Inventory-Aware Advertising

> **You:** I'm running out of stock on some products. Should I adjust my ads?
>
> **Agent:** Let me check your inventory levels against your active ad campaigns...
>
> **⚠️ Stock alert — these advertised products are low:**
>
> | Product | Stock | Daily Sales | Days Until OOS | Currently Advertised? |
> |---|---|---|---|---|
> | Premium Serum (30ml) | 45 | 12/day | **3.7 days** | ✅ Yes — $30/day on Meta |
> | Travel Kit Bundle | 28 | 4/day | 7 days | ✅ Yes — $15/day on Google |
> | Daily Moisturizer | 890 | 16/day | 56 days | ✅ Yes — safe |
>
> **Immediate action needed:**
> 1. **Premium Serum:** Will sell out in 3.7 days. Options:
>    - Pause ads NOW to preserve stock for organic orders (recommended if restock is 2+ weeks away)
>    - Reduce ad budget by 50% to slow sales velocity
>    - Switch to "Notify Me" landing page when stock hits 10 units
>
> 2. **Travel Kit Bundle:** 7 days of stock. Less urgent but monitor daily.
>
> **The cost of running out:** If you advertise a product and it goes out of stock, you waste the ad click AND damage customer experience. The visitor sees "Sold Out" and may never return.
>
> Want me to pause the Premium Serum ads now?

---

## Shopify Tips for Ad Targeting

1. **Auto-generate product feeds for Google PMax.** Your Shopify catalog is already structured for product feeds. Export → upload to Merchant Center → create PMax campaign → start selling on Google Shopping.
2. **Sync customer emails monthly.** Upload your customer list to Meta, Google, and TikTok for Custom Audiences. Refresh monthly to add new customers and remove churned ones.
3. **Advertise high-margin products, not best-sellers.** A product selling 1,000 units at 15% margin can't sustain paid acquisition. Focus ad budget on products with 50%+ margins.
4. **Cart abandoner retargeting is non-negotiable.** 70% of carts are abandoned. Retargeting ads (showing the exact abandoned products) recover 10-15% of lost revenue.
5. **Check inventory before scaling ads.** Running out of stock on an advertised product wastes money and frustrates customers. Set up alerts when advertised products drop below 2 weeks of inventory.
6. **Frequently bought together = bundle ads.** Analyze co-purchase patterns and create bundle offers. Bundles increase AOV and make great ad creatives.
7. **VIP customers are your Lookalike gold.** Top 10% of customers by LTV make the best Lookalike audience seed. Better than "all customers" by 40-60%.

---

## FAQ

### Is there an MCP for Shopify?
Yes — this repo. It pre-configures the Synter MCP server for Shopify. Works with Amp, Cursor, VS Code, and Claude Desktop.

### Can I generate Google Shopping feeds from Shopify?
Yes. The agent exports your product catalog in the format required by Google Merchant Center, including titles, descriptions, prices, images, and availability.

### Can I sync Shopify customers to Meta?
Yes. The agent exports customer emails, hashes them, and uploads as Custom Audiences for retargeting and Lookalike creation.

### Does this replace Shopify's native ad integrations?
It complements them. Shopify's native Google/Meta channels are good for basic catalog sync, but the AI agent adds strategic intelligence — choosing which products to advertise, building customer segments, and coordinating cross-platform campaigns.

### Can the agent create Shopify products or discounts?
The agent focuses on reading store data for ad optimization. Product creation and discount management are handled through the Shopify admin.

---

## Related Repos

- [google-ads-agent](https://github.com/Synter-Media-AI/google-ads-agent) — Google Shopping & PMax
- [meta-ads-agent](https://github.com/Synter-Media-AI/meta-ads-agent) — Dynamic Product Ads
- [klaviyo-agent](https://github.com/Synter-Media-AI/klaviyo-agent) — Email/SMS marketing sync
- [tiktok-ads-agent](https://github.com/Synter-Media-AI/tiktok-ads-agent) — TikTok Shop integration
- [audience-sync-agent](https://github.com/Synter-Media-AI/audience-sync-agent) — Multi-platform audience sync
- [conversion-tracking-agent](https://github.com/Synter-Media-AI/conversion-tracking-agent) — Pixel verification

---

## License

MIT — see [LICENSE](LICENSE) for details.

Built by [Synter](https://synterai.com) · [Get API Key](https://synterai.com/developer) · [Documentation](https://synterai.com/docs)
