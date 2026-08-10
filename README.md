# Japan Used Instrument Market — Cross-Shop Price Comparison

**Compare used guitar & instrument prices across Japan's largest used-instrument marketplaces in a single dataset.**

Scrapes listings from **Digimart (デジマート)** — Japan's largest used-instrument marketplace (2,000+ shops) — and **Ishibashi Music U-BOX (イシバシ楽器)** — one of Japan's biggest music store chains (12 stores, 7,000+ used items in stock). Each item is tagged with its `source` and `shop` so you can compare prices for the same model across shops.

## Why this is useful

- **Cross-shop price comparison** — the same guitar/amp often differs by 10-30% between shops
- **Resale arbitrage** — find underpriced gear at one shop, sell at another
- **Price monitoring** — track market moves for your gear before buying/selling
- **Full market scan** — one run covers electric/acoustic guitars, basses, effects, amps, drums, keyboards, and more

## Input

| Field | Type | Default | Description |
|---|---|---|---|
| `searchKeyword` | string | `Fender` | Keyword filter (empty = full market scan) |
| `maxItems` | integer | 100 | Max items to collect |
| `maxPages` | integer | 2 | Max pages per source |
| `sources` | string | `digimart,ishibashi` | Comma-separated source list |

## Output fields

| Field | Description |
|---|---|
| `productId` | Product ID at source shop |
| `title` | Product title |
| `price` | Price in JPY |
| `brand` | Brand |
| `shop` | Source shop name |
| `category` | Category label |
| `condition` | Condition (新品/中古/ビンテージ) |
| `source` | `digimart` or `ishibashi` |
| `imageUrl` | Product image URL |
| `productUrl` | Product page URL |
| `scrapedAt` | Scrape timestamp |

## Pricing

Pay per event — $0.00005/run + **$0.002/item**.

## Data source notes

- **Digimart**: server-side rendered search pages with embedded dataLayer JSON (item_id, brand, category, price, stock). 174k+ items for guitar alone.
- **Ishibashi Music U-BOX**: server-side rendered search (`store.ishibashi.co.jp/search`), 2,379+ used electric guitars, 7,000+ used items total.

Both sources are public web data; only factual product information (name, price, brand, stock status) is collected.
