# AI Crawlers And Retriever Tokens

Last reviewed for this skill: 2026-07-08. These names and policies change. When an audit depends on a specific crawler, verify the current official documentation before making a strict recommendation.

## Current High-Signal Tokens

| Provider | Token | Typical purpose | Notes |
|---|---|---|---|
| OpenAI | `OAI-SearchBot` | Search/indexing for ChatGPT search experiences | High priority for AI-search discoverability. |
| OpenAI | `ChatGPT-User` | User-initiated retrieval | Blocking can stop ChatGPT from opening a page when a user asks. |
| OpenAI | `GPTBot` | Model training data collection | Training control, not the same as search citation access. |
| Google | `Googlebot` | Google Search crawling | Controls Google Search, including Search AI features that rely on Search indexing. |
| Google | `Google-Extended` | Data-use control for some Gemini/Vertex AI uses | Does not control Google Search inclusion or ranking. Do not present it as an AI Overview visibility switch. |
| Perplexity | `PerplexityBot` | Perplexity crawling/indexing | Perplexity recommends allowing it for search visibility. |
| Perplexity | `Perplexity-User` | User-triggered retrieval | Check current docs; behavior may evolve. |
| Anthropic | `ClaudeBot` | Model training data collection | Training control. |
| Anthropic | `Claude-User` | User-triggered retrieval | Blocking can reduce user-directed web search visibility. |
| Anthropic | `Claude-SearchBot` | Search indexing | More relevant than `ClaudeBot` for Claude search visibility. |
| Common Crawl | `CCBot` | Public web crawl dataset | Often used in AI training pipelines, but not a live citation engine by itself. |
| ByteDance | `Bytespider` | ByteDance crawler | Relevance depends on target market and products. |
| Amazon | `Amazonbot` | Amazon AI/shopping crawler | Relevance depends on ecommerce/shopping context. |

## How To Interpret robots.txt

- A `User-agent: *` block can affect AI crawlers unless a more specific block overrides it.
- Specific allow/disallow rules matter more than token presence.
- Distinguish crawler types:
  - Search/index bots affect whether a system can discover and cite pages.
  - User-triggered fetchers affect whether an assistant can retrieve a page in response to a user.
  - Training bots affect model training permissions, not necessarily live answer visibility.
- WAF/CDN bot rules can block AI systems even when robots.txt allows them. If the site returns 403/429/challenges to common fetchers, report that separately.

## Official Documentation To Recheck

- OpenAI crawlers: `https://developers.openai.com/api/docs/bots`
- Google crawlers: `https://developers.google.com/crawling/docs/crawlers-fetchers/google-common-crawlers`
- Google Search AI features: `https://developers.google.com/search/docs/appearance/ai-features`
- Google generative AI optimization guide: `https://developers.google.com/search/docs/fundamentals/ai-optimization-guide`
- Anthropic crawlers: `https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler`
- Perplexity crawlers: `https://docs.perplexity.ai/docs/resources/perplexity-crawlers`

## Reporting Language

Use careful language:

- Good: "`OAI-SearchBot` appears blocked in robots.txt, which can reduce ChatGPT search discovery."
- Good: "`Google-Extended` is blocked. This controls some Google AI product data use, but Google says it does not affect Google Search inclusion or ranking."
- Bad: "No `llms.txt`, so ChatGPT cannot cite the site."
- Bad: "Blocking `Google-Extended` removes the site from Google AI Overviews."
