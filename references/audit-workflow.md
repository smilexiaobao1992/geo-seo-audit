# Audit Workflow

Use this workflow when the user asks for a full SEO/GEO diagnosis, competitor comparison, or recurring checklist.

## Evidence Collection

1. Normalize the target.
   - Convert bare domains to `https://domain`.
   - Keep the user-provided URL as evidence, but prefer the canonical URL observed from redirects, search results, or page metadata.

2. Fetch the homepage.
   - Capture status, final URL, title, meta description, canonical, robots meta, visible text, images/alt text, language, and obvious client-side rendering problems.
   - If the first fetch fails, try browser rendering or search-result snippets before declaring the homepage unreachable.
   - Cross-check with at least two access methods when possible, such as web open/search plus `curl`, browser rendering, or Node/Python HTTP. If only one tool fails, treat it as a tool/network limitation until another method confirms a real site defect.

3. Fetch discovery files.
   - Try direct public URLs: `/robots.txt`, `/sitemap.xml`, `/llms.txt`, `/llms-full.txt`.
   - If direct requests are blocked by the tool environment, search the exact full URL and open the result if found.
   - If sitemap is missing, search `site:domain` and sample indexed pages.
   - Treat "not found" and "not automatically verified" differently.

4. Check URL consistency.
   - For important pages, compare requested URL, final URL after redirects, canonical URL, sitemap URL, hreflang URL, and any `llms.txt` URL.
   - Flag mismatches such as `.html` vs no `.html`, trailing slash drift, HTTP/HTTPS drift, `www` vs apex drift, or canonical URLs that point to redirecting URLs.
   - Do not treat alternate language URLs as duplicates when hreflang is explicit and correct.

5. Sample internal pages.
   - Homepage.
   - About/company/contact page.
   - One or two product/service/category pages.
   - Blog, article, FAQ, or resource page if available.
   - Local business, ecommerce, or B2B pages relevant to the site type.

6. Search for old or orphaned paths.
   - Search `site:domain` and inspect unexpected URL families, especially after redesigns or platform migrations.
   - Look for old ecommerce paths such as `/product/`, `/product-category/`, `/shop/`, `/cart/`, `/tag/`, and `/wp-content/` when the current site appears to use a different structure.
   - Look for old template/provider domains, staging domains, outdated contact details, prices, year strings, or brand names in indexed snippets.
   - Recommend 301 redirects when there is a relevant replacement page; use 404/410 only when the old page has no valid replacement.

7. Check external trust.
   - Search brand name, legal/company name, domain, and product terms.
   - Look for third-party mentions: reviews, industry directories, trade associations, news, forums, partners, marketplaces, Google Business Profile, Trustpilot, LinkedIn, Crunchbase, app stores, or local directories.
   - Do not advise fake reviews, paid mentions, or low-quality directory spam.

## Tool Fallbacks

Use whatever is available:

- Web search/open tools for public pages and official documentation.
- `curl -I` and `curl -L` for status, redirects, headers, and public text files.
- Browser/Playwright for rendering, mobile layout, forms, screenshots, DOM, and accessibility tree checks.
- HTML parsers when raw source is available.

If a tool cannot access a URL because of sandbox, permissions, anti-bot, or network restrictions, say so. Do not convert a tooling limitation into a site defect unless normal users or crawlers are likely affected too.

When tools disagree, report the disagreement explicitly:

- Confirmed site issue: two or more independent access methods show the same failure.
- Tool/network limitation: one method fails but another fetches the page normally.
- Crawler-specific issue: browser/user fetch works but named crawler user agents fail or receive different robots/WAF treatment.

## Competitor Comparison

For each site, use the same sample depth and scoring rubric. Compare only evidence gathered with comparable methods.

Recommended output:

| Area | Client Site | Competitor | Gap |
|---|---:|---:|---|
| Crawl/index foundation | score | score | one-line explanation |
| SEO basics | score | score | one-line explanation |
| GEO content readiness | score | score | one-line explanation |
| Entity trust | score | score | one-line explanation |

End with the highest-leverage move, not a long generic checklist.
