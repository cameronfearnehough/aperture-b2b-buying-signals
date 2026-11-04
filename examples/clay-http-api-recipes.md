# Aperture B2B Buying Signals — Clay HTTP API Integration Recipes

Drop real-time European, US, and APAC B2B buying signals—hiring intent, startup funding rounds, statutory contract awards, executive leadership appointments, and biotech clinical trials & R&D grants—directly into your **Clay tables**, **HeyReach campaigns**, or **Smartlead outbound sequences**. Runs in the cloud without requiring your LinkedIn cookies or browser login across **9 markets: the United States (`US`), Germany (`DE`), Austria (`AT`), Belgium (`BE`), the Netherlands (`NL`), France (`FR`), the United Kingdom (`UK`), Australia (`AU`), and New Zealand (`NZ`)**.

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

All Aperture Actors enforce a strict **Named-Contact Pay-Per-Event (PPE)** policy backed by an unbilled **$0.00 Pre-Fetch Exclusion Shield**:

1. **Signal Scrapers** (`stepstone-dach`, `seek-anz`, `france-buying-signal`, `eu-uk-procurement`, `eu-uk-executive`, `biotech-clinical-trial`):
   * **`$0.002` per signal (`$2.00 / 1,000`) — `job-signal-scraped` (Basic Tier):** Standard buying signal with company name, resolved corporate root domain, role/notice/trial title, seniority band, location, and canonical evidence URL.
   * **`$0.008` per named contact (`$8.00 / 1,000`) — `buying-signal-enriched` (Premium Tier):** Charged **strictly** when a verified decision-maker email (`firstname.lastname@company.com`) is discovered (`email_verification_status: "ok"`).
   * **Role Fallbacks Are Free Bonus Data:** If only a generic departmental address (`info@`, `contact@`, `hello@`, `jobs@`, `sales@`, `planning@`, `clinicaltrials@`, `grants@`) is found, it is retained in `contact_email` with `email_verification_status: "role_fallback"` and billed at the basic **`$0.002`** rate.
2. **5D ICP Aggregator** (`b2b-buying-signal-icp-aggregator`):
   * **`$0.003` per lead (`$3.00 / 1,000`) — `icp-lead-scored` (Basic Tier):** Scored account with multi-signal score (`0–100`), 28 detected tech stack tags, and personalized outreach hook.
   * **`$0.009` per lead (`$9.00 / 1,000`) — `icp-multi-signal-enriched` (Premium Tier):** Charged only when delivering a verified named decision-maker contact (`email_verification_status: "ok"`). Role fallbacks are billed at the basic **`$0.003`** rate.
3. **$0.00 Pre-Fetch Exclusion Shield & Cost Protection:**
   * Competitors, legacy partners, and current customers in `blacklistDomains` are dropped at **`$0.00`** before website crawling or scoring.
   * Unbilled pre-fetch exclusions (`excludeCompanyKeywords: ["staffing", "recruiting"]` and `excludeLocations: []`) drop non-ICP records at **`$0.00`** before any enrichment or PPE charging occurs.
   * On Biotech (`biotech-clinical-trial-buying-signal-scraper`), the hard pre-charge recency floor (`minSignalYear: 2025`) and `commercialSponsorsOnly: true` discard legacy 2017–2024 registry entries and non-commercial academic hospitals at **`$0.00`** before domain resolution.

### Dual-Store Volume Break-Even (`8,300 rows/mo`)

For teams evaluating volume economics:
* **Below `8,300 rows/month`**: The **Apify Store Pay-Per-Event (PPE)** model (`$0.002` basic / `$0.008` verified named contact) offers zero monthly subscription commitment—you only pay for exact leads emitted into your Clay table.
* **At or above `8,300 rows/month`**: Transitioning to **Bytewells (`bytewells.com`)** via **`$49/mo` Flat Rental** or **Transit-Capped Passes (`$3` / `$12` / `$29`)** provides unlimited runs with **`$0.00` per-event billing**, featuring native **HTTP 402 (`x402`) Agentic Auto-Buy** support for autonomous workflows.

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
    "excludeCompanyKeywords": ["staffing", "recruiting"],
    "excludeLocations": [],
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
    "excludeCompanyKeywords": ["staffing", "recruiting"],
    "excludeLocations": [],
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
    "excludeCompanyKeywords": ["staffing", "recruiting"],
    "excludeLocations": [],
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
    "excludeCompanyKeywords": ["staffing", "recruiting"],
    "excludeLocations": [],
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
    "excludeCompanyKeywords": ["staffing", "recruiting"],
    "excludeLocations": [],
    "maxItems": 5,
    "scraperMode": "enriched_with_email",
    "blacklistDomains": ["existing-customer.com"],
    "onlyNewSignals": true
  }
  ```
* **Supported Jurisdictions:** `"FR"`, `"UK"`, `"DE"`, `"AT"`

---

## 6. Biotech Clinical Trials & Non-Dilutive R&D Grants (`US`, `UK`, `DE`, `FR`, `NL`, `BE`, `AT`)

Extract live commercial life-sciences buying signals across US ClinicalTrials.gov API v2, EU EMA CTIS, EU CORDIS Horizon Europe, and US NIH RePORTER (SBIR/STTR commercial awards) with corporate Impressum and legal contact email resolution.

* **Endpoint:**
  ```http
  POST https://api.apify.com/v2/acts/aperture~biotech-clinical-trial-buying-signal-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN&maxTotalChargeUsd=0.25
  Content-Type: application/json
  ```
* **Request Body:**
  ```json
  {
    "signalSources": ["clinicaltrials_us", "eu_ctis", "eu_cordis", "nih_sbir"],
    "countries": ["US", "UK", "DE", "FR"],
    "keywords": ["oncology", "immunotherapy", "biomarker"],
    "phases": ["PHASE1", "PHASE2", "PHASE3"],
    "commercialSponsorsOnly": true,
    "postedWithinDays": 180,
    "minSignalYear": 2025,
    "excludeCompanyKeywords": ["university", "hospital"],
    "excludeLocations": [],
    "maxItems": 5,
    "scraperMode": "enriched_with_email",
    "onlyNewSignals": true
  }
  ```
* **$0.00 Pre-Charge Recency & Exclusion Guard:**
  Public clinical trial and grant portals contain vast backlogs of historical trials dating back decades. The Actor enforces `StudyFirstPostDate:desc` sorting and a hard pre-charge recency floor (`minSignalYear: 2025`). Any historical study or grant awarded prior to 2025 is eliminated at **`$0.00`** before corporate domain resolution, website crawling, or PPE event charging. In addition, `commercialSponsorsOnly: true` automatically purges non-commercial academic sponsors, universities, and hospitals at **`$0.00`**.
* **Supported Jurisdictions & Registries:**
  * `"US"`: ClinicalTrials.gov v2 & NIH RePORTER SBIR/STTR commercial awards
  * `"UK"`, `"DE"`, `"FR"`, `"NL"`, `"BE"`, `"AT"`: EU EMA CTIS (Clinical Trials Information System) & EU CORDIS Horizon Europe

---

## 7. Zero-Proxy B2B Buying-Signal 5D ICP Aggregator & Scorer

Merge, deduplicate, and score (`0–100`) leads across all upstream Aperture signal datasets (jobs, funding, contract awards, executive appointments, clinical trials, and research grants), detecting 28 tech-stack tags and generating personalized cold outreach hooks.

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
      "allowedGeos": ["US", "DE", "AT", "BE", "NL", "FR", "UK", "AU", "NZ"],
      "allowedSignalTypes": ["jobs", "funding", "contract_award", "executive_change", "clinical_trial", "research_grant", "multi_signal"],
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
      },
      {
        "company": "Systimmune Inc.",
        "domain": "systimmune.com",
        "role_title": "Clinical Trial Sponsor (PHASE1): Study Director Patrick Diaz",
        "geo": "US",
        "signal_type": "clinical_trial",
        "signal_date": "2026-10-28",
        "contact_email": "jimmy.zhao@systimmune.com",
        "email_verification_status": "ok"
      }
    ],
    "icpConfig": {
      "allowedGeos": ["US", "DE", "AT", "BE", "NL", "FR", "UK", "AU", "NZ"],
      "allowedSignalTypes": ["jobs", "funding", "contract_award", "executive_change", "clinical_trial", "research_grant", "multi_signal"],
      "minIcpScore": 50,
      "maxSignalAgeDays": 45
    },
    "maxItems": 5
  }
  ```
