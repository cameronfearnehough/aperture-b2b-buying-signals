# Aperture B2B Buying Signals — Clay HTTP API Integration Recipes

Drop real-time European and APAC B2B buying signals—hiring intent, startup funding rounds, statutory contract awards, and executive leadership appointments—directly into your **Clay tables**, **HeyReach campaigns**, or **Smartlead outbound sequences**.

With Apify's synchronous **`run-sync-get-dataset-items`** endpoint, Clay triggers the Actor, waits for execution to complete, and returns the deduplicated dataset records directly into your table in a single request.

---

## Clay Setup Reference Table

To trigger any Aperture Actor directly from a Clay table column, create an **HTTP API (Action / Enrichment)** column with the following configuration:

| Setting | Value / Expression | Description |
| :--- | :--- | :--- |
| **Method** | `POST` | Executes the Actor run and returns output synchronously |
| **URL** | `https://api.apify.com/v2/acts/aperture~<actor-name>/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN&maxTotalChargeUsd=0.25` | Apify synchronous execution & dataset fetch endpoint |
| **Headers** | `Content-Type: application/json` | Standard JSON payload header |
| **Query Param: `token`** | `YOUR_APIFY_TOKEN` *(or `{{secrets.APIFY_API_TOKEN}}`)* | Your Apify Personal API Token (Apify Console > Settings > Integrations) |
| **Query Param: `maxTotalChargeUsd`** | `0.25` *(Default recommended ceiling)* | Optional safety ceiling. Apify automatically terminates the run before spending more than this amount |
| **Request Body** | See Actor JSON recipes below | Actor-specific filter parameters (`scraperMode: "enriched_with_email"`, `maxItems: 5`) |
| **Output Type** | JSON Array of Objects | Map returned objects into Clay table rows or enrichment cells |

---

## Fair Pricing Guarantee: Only Pay for Named People

All Aperture Actors enforce a strict **Named-Contact Pay-Per-Event (PPE)** policy:

1. **Signal Scrapers** (`stepstone-dach`, `seek-anz`, `france-buying-signal`, `eu-uk-procurement`, `eu-uk-executive`):
   * **`$0.002` per signal (`$2.00 / 1,000`) — `job-signal-scraped` (Basic Tier):** Standard buying signal with company name, resolved domain, role/notice title, seniority band, location, and evidence URL.
   * **`$0.008` per named contact (`$8.00 / 1,000`) — `buying-signal-enriched` (Premium Tier):** Charged **strictly** when a verified decision-maker email (`firstname.lastname@company.com`) is discovered (`email_verification_status: "ok"`).
   * **Role Fallbacks Are Free Bonus Data:** If only a generic departmental address (`info@`, `contact@`, `hello@`, `jobs@`, `sales@`, `planning@`) is found, it is retained in `contact_email` with `email_verification_status: "role_fallback"` and billed at the basic **`$0.002`** rate.
2. **ICP Aggregator** (`b2b-buying-signal-icp-aggregator`):
   * **`$0.003` per lead (`$3.00 / 1,000`) — `icp-lead-scored` (Basic Tier):** Scored account with multi-signal score (`0–100`), 28 detected tech stack tags, and personalized outreach hook.
   * **`$0.009` per lead (`$9.00 / 1,000`) — `icp-multi-signal-enriched` (Premium Tier):** Charged only when delivering a verified named decision-maker contact (`email_verification_status: "ok"`). Role fallbacks are billed at the basic **`$0.003`** rate.

### Clay Formula: Filter Verified Decision-Makers vs. Role Inboxes

Use this formula in a Clay Formula column to segment outbound sequences:

```javascript
// Check if lead has a verified named decision-maker vs. generic role fallback
if ([email_verification_status] === 'ok' && [contact_email]) {
  return 'VERIFIED_NAMED_CONTACT'; // Route to 1-to-1 Decision Maker Sequence
} else if ([email_verification_status] === 'role_fallback' && [contact_email]) {
  return 'ROLE_FALLBACK_INBOX';   // Route to Company General Inbound
} else {
  return 'NO_EMAIL';              // Trigger secondary waterfall
}
```

---

## 1. Stepstone DACH, Benelux & Netherlands Buying Signals

Extract active hiring intent across Germany (`DE`), Austria (`AT`), Belgium (`BE`), and the Netherlands (`NL`) with legal Impressum-enriched decision-maker emails.

* **Endpoint:**
  ```http
  POST https://api.apify.com/v2/acts/aperture~stepstone-dach-buying-signal-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN&maxTotalChargeUsd=0.25
  Content-Type: application/json
  ```
* **Request Body:**
  ```json
  {
    "keywords": ["Account Executive", "Head of Sales", "SDR", "RevOps"],
    "country": "DE",
    "location": "Berlin",
    "postedWithinDays": 7,
    "maxItems": 5,
    "scraperMode": "enriched_with_email",
    "seniorityFilter": ["mid", "senior", "manager", "director", "vp", "cxo"],
    "blacklistDomains": ["existing-customer.de"],
    "onlyNewSignals": true
  }
  ```
* **Supported Countries:** `"DE"` (stepstone.de), `"AT"` (stepstone.at), `"BE"` (stepstone.be), `"NL"` (stepstone.nl)

---

## 2. Seek Australia & New Zealand Buying Signals

Extract active hiring buying signals across Australia (`AU`) and New Zealand (`NZ`) with corporate contact page discovery.

* **Endpoint:**
  ```http
  POST https://api.apify.com/v2/acts/aperture~seek-anz-buying-signal-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN&maxTotalChargeUsd=0.25
  Content-Type: application/json
  ```
* **Request Body:**
  ```json
  {
    "keywords": ["Account Executive", "Business Development Manager", "SDR"],
    "country": "AU",
    "location": "Sydney",
    "postedWithinDays": 7,
    "maxItems": 5,
    "scraperMode": "enriched_with_email",
    "seniorityFilter": ["mid", "senior", "manager", "director", "vp", "cxo"],
    "blacklistDomains": ["existing-customer.com.au"],
    "onlyNewSignals": true
  }
  ```
* **Supported Countries:** `"AU"` (seek.com.au), `"NZ"` (seek.co.nz)

---

## 3. France Buying Signals (Jobs & Startup Funding)

Extract French hiring signals from France Travail (`france_travail_jobs`) and French tech fundraising announcements from Maddyness (`maddyness_funding`) with Mentions Légales email resolution.

* **Endpoint:**
  ```http
  POST https://api.apify.com/v2/acts/aperture~france-buying-signal-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN&maxTotalChargeUsd=0.25
  Content-Type: application/json
  ```
* **Request Body:**
  ```json
  {
    "signalSources": ["france_travail_jobs", "maddyness_funding"],
    "keywords": ["Business Developer", "Account Executive", "Commercial B2B"],
    "location": "Paris",
    "maxDaysSinceAnnouncement": 30,
    "maxItems": 5,
    "scraperMode": "enriched_with_email",
    "blacklistDomains": ["client-existant.fr"],
    "onlyNewSignals": true
  }
  ```
* **Supported Sources:** `"france_travail_jobs"`, `"maddyness_funding"`

---

## 4. EU & UK Public Procurement Contract Awards

Detect winning B2B public sector suppliers across the UK (Find a Tender / Contracts Finder), France (BOAMP), and the European Union (EU TED Search: Germany, Netherlands, Belgium, Austria) with statutory commercial email enrichment.

* **Endpoint:**
  ```http
  POST https://api.apify.com/v2/acts/aperture~eu-uk-procurement-award-signal-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN&maxTotalChargeUsd=0.25
  Content-Type: application/json
  ```
* **Request Body:**
  ```json
  {
    "countries": ["UK", "FR", "DE", "NL", "BE", "AT"],
    "keywords": ["Software", "Cloud", "Cyber", "Consulting"],
    "minContractValue": 100000,
    "postedWithinDays": 30,
    "maxItems": 5,
    "scraperMode": "enriched_with_email",
    "blacklistDomains": ["existing-partner.co.uk"],
    "onlyNewSignals": true
  }
  ```
* **Supported Jurisdictions:** `"UK"`, `"FR"`, `"DE"`, `"NL"`, `"BE"`, `"AT"`

---

## 5. EU & UK Executive Appointments & New Incorporations

Track executive leadership appointments (Managing Directors, Présidents, C-Level) and freshly incorporated corporate entities across France (BODACC), the UK (Companies House), Germany (Handelsregister), and Austria (Firmenbuch) without requiring LinkedIn cookies.

* **Endpoint:**
  ```http
  POST https://api.apify.com/v2/acts/aperture~eu-uk-executive-incorporation-signal-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN&maxTotalChargeUsd=0.25
  Content-Type: application/json
  ```
* **Request Body:**
  ```json
  {
    "countries": ["FR", "UK", "DE", "AT"],
    "signalCategories": ["executive_appointment", "new_incorporation"],
    "keywords": ["Software", "Technology", "Cloud", "Digital"],
    "postedWithinDays": 30,
    "maxItems": 5,
    "scraperMode": "enriched_with_email",
    "blacklistDomains": ["existing-customer.com"],
    "onlyNewSignals": true
  }
  ```
* **Supported Jurisdictions:** `"FR"`, `"UK"`, `"DE"`, `"AT"`

---

## 6. Zero-Proxy B2B Buying-Signal ICP Aggregator & Scorer

Merge, deduplicate, and score (`0–100`) leads across all upstream Aperture signal datasets, detecting 28 tech-stack tags and generating personalized cold outreach hooks.

### Option A: Aggregate Prior Apify Datasets
Feed dataset IDs generated by weekly scraper runs into the aggregator:

* **Endpoint:**
  ```http
  POST https://api.apify.com/v2/acts/aperture~b2b-buying-signal-icp-aggregator/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN&maxTotalChargeUsd=0.25
  Content-Type: application/json
  ```
* **Request Body:**
  ```json
  {
    "datasetIds": [
      "w6Qf9L8M2nOpQrStU",
      "z1X2c3V4b5N6m7K8j"
    ],
    "icpConfig": {
      "allowedGeos": ["DE", "AT", "BE", "NL", "FR", "UK", "AU", "NZ"],
      "allowedSignalTypes": ["jobs", "funding", "contract_award", "executive_change", "multi_signal"],
      "minIcpScore": 50,
      "maxSignalAgeDays": 45
    },
    "blacklistDomains": ["existing-customer.com", "competitor.com"],
    "maxItems": 5
  }
  ```

### Option B: Instant Trial with Sample / Inline Signals
Test scoring logic immediately in Clay without running upstream scrapers:

* **Endpoint:**
  ```http
  POST https://api.apify.com/v2/acts/aperture~b2b-buying-signal-icp-aggregator/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN&maxTotalChargeUsd=0.25
  Content-Type: application/json
  ```
* **Request Body:**
  ```json
  {
    "rawSignals": [
      {
        "company": "StackFuel GmbH",
        "domain": "stackfuel.com",
        "role_title": "Sales Development Representative (SDR) B2B",
        "geo": "DE",
        "signal_type": "jobs",
        "signal_date": "2026-10-28",
        "contact_email": "malte.fenger@stackfuel.com",
        "email_verification_status": "ok"
      }
    ],
    "icpConfig": {
      "allowedGeos": ["DE", "AT", "BE", "NL", "FR", "UK", "AU", "NZ"],
      "allowedSignalTypes": ["jobs", "funding", "contract_award", "executive_change", "multi_signal"],
      "minIcpScore": 50,
      "maxSignalAgeDays": 45
    },
    "maxItems": 5
  }
  ```
