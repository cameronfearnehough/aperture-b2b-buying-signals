![Aperture — Global B2B Buying-Signal & Statutory Enrichment Suite](https://api.apify.com/v2/key-value-stores/j5l13XT1d0O0NQmTI/records/aperture-suite-banner.png)

![Strict Named-Contact $0.008](https://api.apify.com/v2/key-value-stores/j5l13XT1d0O0NQmTI/records/badge-strict-named-contact.svg) ![Zero-Proxy HTTP/2 <5s](https://api.apify.com/v2/key-value-stores/j5l13XT1d0O0NQmTI/records/badge-zero-proxy-http2.svg) ![LIMITED_PERMISSIONS • MCP Ready](https://api.apify.com/v2/key-value-stores/j5l13XT1d0O0NQmTI/records/badge-mcp-skyfire-ready.svg)

# Aperture — Global B2B Buying-Signal & Enrichment Suite

Monorepo for **[Aperture — Data Aggregation Solutions](https://apify.com/aperture)** on the Apify Store.

A unified portfolio of commercial B2B intent-signal scrapers and post-processing tools engineered for Sales-Ops, RevOps, and growth teams running outbound campaigns in Clay, n8n, Make, or custom CRMs across **8 countries: Germany (`DE`), Austria (`AT`), Belgium (`BE`), the Netherlands (`NL`), France (`FR`), the UK (`UK`), Australia (`AU`), and New Zealand (`NZ`)**. Every tool resolves the company's real website domain, crawls legal/contact pages (`/impressum`, `/mentions-legales`, `/kontakt`), and extracts verified decision-maker emails and direct phone numbers in one pass—cloud-native with zero cookies or browser login required.

---

## Quick Links: 1-Click n8n Workflows, Clay HTTP API Recipes & Claude Desktop MCP

Ready-to-import integration assets for zero-code and low-code outbound data pipelines:

* **[Global 4-Actor Fan-In n8n Workflow](./examples/n8n-global-4-actor-fan-in-to-clay.json)**: Scheduled multi-region pipeline running Stepstone DACH, Seek ANZ, France Multi-Signal, and EU/UK Procurement in parallel, streaming into the ICP Aggregator, and syncing to Clay.
* **[Stepstone DACH to Clay n8n Workflow](./examples/stepstone-dach-buying-signals-to-clay.json)**: Dedicated DACH buying signal scraper running on hourly/daily cron with automatic Clay webhook dispatch.
* **[Clay HTTP API Recipes & Webhook Guides](./examples/clay-http-api-recipes.md)**: Copy-paste cURL, HTTP API request bodies, and Clay action configurations for webhook-based automated enrichment.
* **[Claude Desktop & Cursor MCP Server Config](./examples/claude_desktop_config.json)**: One-click configuration to orchestrate all 6 Aperture Actors directly inside Claude Desktop, Cursor, or any MCP client.
* **[X (Twitter) Launch Samples & Verified Live Rows](./X_LAUNCH_SAMPLES.md)**: Real output payloads, screenshot-ready Markdown tables, and campaign launch templates across all 6 commercial Actors.

---

## Fair Pricing Guarantee: Only Pay for Named People

All Aperture Actors enforce a transparent, cost-protective Pay-Per-Event (PPE) pricing policy:

* **Regional Signal Scrapers (`$0.002` / `$0.008`)**:
  * **`$0.002` per company signal (`$2.00 / 1,000`) — `job-signal-scraped`:** Includes full company profile, resolved website domain, verified phone number, salary/contract details, and statutory role inbox if found.
  * **`$0.008` per named contact (`$8.00 / 1,000`) — `buying-signal-enriched`:** Charged strictly when a verified named decision-maker email (`firstname.lastname@company.com`, `email_verification_status: "ok"`) is delivered.
  * **Generic Inboxes Are Free (`role_fallback`):** Generic role inboxes (`info@`, `contact@`, `sales@`, `jobs@`) are provided at no extra charge (`email_verification_status: "role_fallback"`) and billed at the basic `$0.002` rate.
* **B2B Buying-Signal ICP Aggregator (`$0.003` / `$0.009`)**:
  * **`$0.003` per scored lead (`$3.00 / 1,000`) — `icp-lead-scored`:** Cross-dataset deduplication, 0–100 ICP score, 28 tech-stack tags, ready-to-send outreach hook, and free role fallback inboxes (`role_fallback`).
  * **`$0.009` per named contact (`$9.00 / 1,000`) — `icp-multi-signal-enriched`:** Charged only when the lead includes a verified named contact (`firstname.lastname@`, `email_verification_status: "ok"`).
  * **`$0.00` for Blacklisted Accounts:** Current customers, competitors, and agencies filtered via `blacklistDomains` are excluded before scoring and billing at zero cost.

---

## Live 6-Actor Suite

![Aperture Multi-Region Buying-Signal & ICP Aggregation Architecture](https://api.apify.com/v2/key-value-stores/j5l13XT1d0O0NQmTI/records/aperture-architecture.png)

| Actor | Geos | Signal & Enrichment | Primary Data Sources | Price (Basic / Named) |
| :--- | :---: | :--- | :--- | :--- |
| **[Stepstone DACH & NL](https://apify.com/aperture/stepstone-dach-buying-signal-scraper)** | `DE` `AT` `BE` `NL` | Hiring + `/impressum` emails | Stepstone Germany, Austria, Belgium & Netherlands + Impressum email discovery | `$0.002` / **`$0.008`** |
| **[Seek Australia & NZ](https://apify.com/aperture/seek-anz-buying-signal-scraper)** | `AU` `NZ` | Hiring + salary & emails | Seek Australia & New Zealand live job postings + corporate email discovery | `$0.002` / **`$0.008`** |
| **[France Multi-Signal](https://apify.com/aperture/france-buying-signal-scraper)** | `FR` | Hiring + VC funding + SIRET | France Travail job postings + Maddyness startup funding rounds + mentions-légales emails | `$0.002` / **`$0.008`** |
| **[EU & UK Procurement](https://apify.com/aperture/eu-uk-procurement-award-signal-scraper)** | `UK` `FR` `DE` `NL` `BE` `AT` | Public contract award winners | UK Find a Tender / Contracts Finder + France BOAMP + EU TED public contract awards | `$0.002` / **`$0.008`** |
| **[EU & UK Exec & Incorp](https://apify.com/aperture/eu-uk-executive-incorporation-signal-scraper)** | `FR` `UK` `DE` `AT` | New CEOs/MDs & incorporations | France BODACC & Recherche d'Entreprises + UK Companies House + GLEIF Level-1 v1 | `$0.002` / **`$0.008`** |
| **[B2B ICP Aggregator](https://apify.com/aperture/b2b-buying-signal-icp-aggregator)** | `All 8` | Multi-signal dedup & ICP score | Cross-dataset deduplicator, 28-tool tech scanner, 0–100 ICP scoring & outreach hooks | `$0.003` / **`$0.009`** |

---

## Sample Output Overview (What Lands in Your Clay Table)

| Company | Market | Signal / Role | Discovered Contact Email | Verification Status | PPE Event Triggered | Price Billed |
| :--- | :---: | :--- | :--- | :--- | :--- | :--- |
| **StackFuel GmbH** | `DE` | `Hiring Signal (ICP Score: 63)` | `malte.fenger@stackfuel.com` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **Pennylane SAS** | `FR` | `Multi-Signal: €40M Funding + Hiring (ICP Score: 100)` | `contact@pennylane.com` | `role_fallback` *(Free Bonus)* | `icp-lead-scored` | **$0.003** |
| **Hold Up SAS** | `FR` | `New Appointment: Président — Jean Dupont` | `jean.dupont@holdup-agency.fr` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **UD Trucks New Zealand** | `NZ` | `Hiring Signal (Transport / Fleet)` | `linda.woodham@udtrucks.co.nz` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **Kainos Software Ltd** | `UK` | `Multi-Signal: Public Tender + Cloud Hiring (ICP Score: 100)` | `brendan.mooney@kainos.com` | `ok` *(Named Person)* | `icp-multi-signal-enriched` | **$0.009** |
| **Somy Solutions** | `FR` | `Hiring Signal (B2B SaaS)` | `adeline.gautier@somy-solutions.fr` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |

---

<details>
<summary><strong>Developer Setup, Apify MCP Server & CLI Commands (Click to Expand)</strong></summary>

### Apify MCP Server Full-Suite Configuration

Configure Claude Desktop (`claude_desktop_config.json`) or Cursor (`mcp.json`) to invoke all Aperture Actors autonomously:

```json
{
  "mcpServers": {
    "apify": {
      "command": "npx",
      "args": [
        "-y",
        "@apify/actors-mcp-server",
        "--actors",
        "aperture/stepstone-dach-buying-signal-scraper,aperture/seek-anz-buying-signal-scraper,aperture/france-buying-signal-scraper,aperture/eu-uk-procurement-award-signal-scraper,aperture/eu-uk-executive-incorporation-signal-scraper,aperture/b2b-buying-signal-icp-aggregator"
      ],
      "env": {
        "APIFY_TOKEN": "YOUR_APIFY_TOKEN"
      }
    }
  }
}
```

### Local Development & Verification Commands

Run these commands inside any Actor directory:

```powershell
npm.cmd run lint
npm.cmd run build
npm.cmd test
apify.cmd validate-schema --user-agent apify-agent-skills/apify-actor-development
```

</details>
