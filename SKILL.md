---
name: geo-seo-audit
description: Audit public websites for traditional SEO and GEO (Generative Engine Optimization / AI-search readiness). Use when the user gives a website URL or domain and asks for an SEO audit, GEO audit, website diagnosis, AI-friendly check, ChatGPT/Perplexity/AI Overview citation readiness, robots.txt/llms.txt/sitemap/structured-data review, competitor comparison, or recurring website health checklist. Also trigger for vague URL-only requests such as "帮我看看这个网站怎么样" or "这个网站SEO怎么样". The skill gathers public evidence itself and should not ask the user to paste robots.txt, sitemap, page source, or screenshots unless authenticated/private access is required.
---

# GEO + SEO Audit

Run a practical website audit for non-technical business owners. Cover two surfaces:

1. Traditional SEO: can search engines crawl, understand, index, and present the site?
2. GEO: can AI search and answer engines discover, trust, and cite the site's content?

The user usually wants a clear diagnosis and a prioritized action list, not a technical lecture. Gather evidence yourself, explain jargon in plain language, and separate confirmed findings from items that could not be automatically verified.

## Workflow

### 1. Normalize Scope

- Treat a bare domain as the homepage. Prefer `https://` when probing.
- If the user provides multiple URLs, audit the primary site first and use the others as competitors or page samples.
- Do not ask for source code, robots.txt, sitemap, or screenshots before trying to fetch public evidence.
- If a site requires login, blocks all automated access, or is not public, state that limitation and continue with whatever can be verified.

### 2. Gather Evidence

Use the best tools available in the current Codex environment:

- Web search/open tools, browser tools, `curl`, Playwright, or other HTTP/browser utilities may all be valid.
- Fetch the homepage first, then attempt direct requests for `/robots.txt`, `/sitemap.xml`, `/llms.txt`, and `/llms-full.txt`.
- If direct URL fetches are blocked by the environment, search the exact URL string, then open the returned result.
- Sample 3-6 internal pages when possible: homepage, about/company page, one or two product/service pages, blog/news/FAQ pages if present.
- Search the brand/company name and domain for independent third-party mentions, reviews, associations, articles, directory entries, or forums.
- Record evidence as confirmed, not found, blocked, or not automatically verifiable. Do not infer file contents from absence.

Read the detailed process in [references/audit-workflow.md](references/audit-workflow.md) when running a full audit or competitor comparison.

### 3. Check SEO And GEO

Use the checklist in [references/audit-checklist.md](references/audit-checklist.md). Prioritize:

- Crawlability and indexability: HTTPS, robots.txt, noindex/snippet controls, sitemap, internal links.
- Page basics: title, meta description, canonical, headings/structure, visible text, image alt text, mobile/page experience signals when observable.
- Structured data: parse JSON-LD when raw HTML is available; otherwise mark as not automatically verified.
- JavaScript rendering risk: identify whether core content appears in fetched HTML/text or only after client-side rendering.
- AI crawler and retriever access: check relevant robots.txt tokens and any visible WAF/CDN blocking behavior.
- AI-citable content quality: specific claims, data, citations, expert/first-hand experience, update dates, author/company credibility, and non-commodity content.
- Entity trust: consistency of company name, address/contact details, social profiles, review sites, industry directories, press, and third-party references.

For AI crawler names and current caveats, read [references/ai-crawlers.md](references/ai-crawlers.md). These identifiers change over time, so verify official docs before making strict claims.

### 4. Score And Prioritize

Use a 100-point score as a communication aid, not as fake precision:

- Crawl/index foundation: 25
- Page-level SEO basics: 25
- GEO content and citation readiness: 30
- Entity and third-party trust: 10
- Fix clarity and business impact: 10

Assign A/B/C/D only after the evidence is reviewed:

- A: 85-100, strong foundation with minor improvements.
- B: 70-84, usable but missing important growth signals.
- C: 50-69, discoverability or content credibility issues need work.
- D: below 50, crawl/index/content trust problems likely block performance.

Do not over-penalize items that cannot be verified automatically. Put them in an "unconfirmed" section and explain what a developer or site owner can check.

### 5. Output

Prefer a concise visual or card-style report when the environment provides a UI/rendering tool. If not, output structured Markdown that is easy to scan.

The final answer should include:

- Overall grade and one-sentence diagnosis.
- Top 2-3 fixes in priority order.
- SEO findings grouped as pass/warn/fail.
- GEO/AI-search findings grouped as pass/warn/fail.
- Plain-language explanation for technical terms.
- Evidence notes: sampled URLs, files checked, and items not automatically verified.
- If comparing competitors, use a side-by-side score table and call out the highest-leverage gap.

Use [references/report-template.md](references/report-template.md) for the recommended report shape.

## Guardrails

- Do not invent data, crawl results, rankings, Search Console metrics, traffic, or crawler behavior.
- Do not present `llms.txt` as required for Google Search or Google AI Overviews/AI Mode. It may be a low-cost experiment for some non-Google systems, but Google Search does not use it as special markup.
- Do not recommend keyword stuffing, fake mentions, bought reviews, duplicate doorway pages, or AI-only rewrites.
- Do not claim that `Google-Extended` controls Google Search visibility. Treat it as a Google AI product data-use control, separate from Google Search inclusion and ranking.
- Do not turn every missing advanced feature into a blocker. For small business sites, distinguish must-fix crawl/index problems from optional polish.
- When sources conflict or a current official doc cannot be checked, state the uncertainty and avoid absolute advice.
