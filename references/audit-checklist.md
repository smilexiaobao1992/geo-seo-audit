# SEO + GEO Audit Checklist

Use this checklist as evidence guidance, not as a rigid pass/fail script.

## Traditional SEO

### Crawl And Index

- HTTPS works and redirects are clean.
- `robots.txt` does not block important pages or all crawlers accidentally.
- Important pages do not use `noindex`.
- Snippet controls are not overly restrictive when AI/Search visibility is desired.
- Sitemap exists or the site has strong internal links that expose important pages.
- Canonical URLs are present and do not point to unrelated pages.
- Important pages return 200 status, not soft 404, redirect loops, or blocked responses.

Plain language: "Can search engines enter the site, find the important pages, and show useful previews?"

### Page Basics

- Title is specific, unique, and describes the page.
- Meta description is present and page-specific.
- Main content is visible as text, not only images or canvas.
- Headings and sections make the content easy to scan.
- Images have useful alt text when images carry meaning.
- URLs contain meaningful words where possible.
- The page is usable on mobile when observable.
- The site avoids intrusive popups that hide the main content.

Plain language: "Can a human and a search engine quickly understand what this page is about?"

### Structured Data

- Parse JSON-LD from raw HTML when available.
- Check that structured data matches visible content.
- For businesses, useful schema types may include `Organization`, `LocalBusiness`, `Product`, `FAQPage`, `Article`, `BreadcrumbList`, and `WebSite`, depending on the site.
- Structured data is an enhancement, not a substitute for visible, useful content.

Plain language: "Structured data is an ID card in the page source. It helps machines confirm what the page describes."

## GEO / AI Search Readiness

### Technical Access

- Important content is available in text form without requiring user interaction.
- Client-side JavaScript does not hide core claims, product details, prices, specs, addresses, or contact information from simple fetchers.
- AI search/indexing user agents are not unintentionally blocked in robots.txt or WAF/CDN rules.
- `llms.txt` presence can be noted, but absence is not a Google Search defect.

Plain language: "Can AI systems actually read the useful parts of the site?"

### Content That Can Be Cited

- Claims include concrete details: specs, materials, dates, certifications, capacity, process, locations, pricing ranges, or measured outcomes.
- Important factual claims cite reliable sources when appropriate.
- Pages include first-hand or expert experience: case studies, manufacturing process, test results, project photos, before/after data, customer scenarios.
- Content avoids empty claims such as "high quality", "best service", and "industry leading" without evidence.
- Pages are updated and show dates when freshness matters.
- FAQ/QA sections answer real buying questions, but do not exist only to stuff keywords.

Plain language: "AI systems prefer facts they can quote and verify, not slogans."

### Entity Trust

- Brand/company name is consistent across the site and third-party mentions.
- Contact details, business address, social profiles, certifications, and legal identifiers are visible where appropriate.
- Third-party mentions are real and relevant: reviews, news, partner pages, directories, associations, forums, marketplaces.
- Do not recommend buying fake mentions or reviews.

Plain language: "If the wider web confirms the company exists and does what it claims, AI systems have more reason to trust it."

## Scoring Guidance

Start from the rubric in `SKILL.md`, then adjust using business impact:

- Critical: robots blocks, noindex, inaccessible homepage, important content missing from fetched/rendered page, severe title/content mismatch.
- High: missing titles/descriptions across important pages, weak internal discovery, JS-only product content, no concrete evidence for major claims.
- Medium: thin alt text, missing sitemap on small but otherwise crawlable site, limited third-party mentions, weak FAQ coverage.
- Low: optional schema enhancements, `llms.txt` experiment, minor copy improvements.

Never score by checklist count alone. A single `Disallow: /` is more important than ten optional metadata issues.
