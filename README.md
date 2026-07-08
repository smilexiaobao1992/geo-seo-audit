# GEO SEO Audit

Codex skill for auditing public websites across traditional SEO and GEO (Generative Engine Optimization / AI-search readiness).

Use it when you want Codex to inspect a website's crawlability, page metadata, sitemap/robots setup, AI crawler access, `llms.txt` posture, structured data, content credibility, and likelihood of being useful as a cited source in AI search experiences.

## What It Does

- Audits public websites from a URL or domain.
- Checks traditional SEO basics: HTTPS, titles, descriptions, canonical URLs, robots rules, sitemaps, structured data, visible content, image alt text, and internal discovery.
- Checks GEO readiness: AI crawler/retriever access, JavaScript rendering risk, citable factual content, third-party entity trust, and `llms.txt` posture.
- Keeps Google Search guidance separate from broader AI-search guidance. For example, the skill does not treat `llms.txt` as required for Google Search, and it does not treat `Google-Extended` as a Google Search visibility switch.
- Produces a business-friendly report with a grade, top fixes, evidence checked, and unverified items.

## Repository Layout

```text
.
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
└── references/
    ├── ai-crawlers.md
    ├── audit-checklist.md
    ├── audit-workflow.md
    └── report-template.md
```

`SKILL.md` contains the trigger description and core workflow. The `references/` files hold detailed checklists, crawler names, and report templates so the main skill stays compact.

## Install For Codex

Clone the repo into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
git clone git@github.com:smilexiaobao1992/geo-seo-audit.git ~/.codex/skills/geo-seo-audit
```

Restart Codex or reload skills if your Codex surface supports skill reloads.

## Example Prompts

```text
帮我审计一下 https://example.com 的 SEO 和 GEO
```

```text
这个网站能不能被 ChatGPT / Perplexity 引用？https://example.com
```

```text
对比一下我们网站 example.com 和竞品 competitor.com 的 SEO/GEO 差距
```

```text
检查 example.com 的 robots.txt、sitemap、llms.txt 和结构化数据有没有问题
```

## Expected Output

The skill asks Codex to gather public evidence itself, then produce:

- A polished health-report style summary with grade, score, risk level, and one-line diagnosis.
- A scorecard across crawl/index foundation, SEO basics, GEO content readiness, entity trust, and fix clarity.
- Top 2-3 priority fixes in a table with owner and business impact.
- Traditional SEO findings with status labels and recommended actions.
- GEO / AI-search findings with status labels and recommended actions.
- Optimization suggestions grouped by developer, content, and business/marketing owner.
- Evidence checked, including sampled pages and discovery files.
- Items that could not be automatically verified.

## Notes And Limitations

- The skill audits public evidence. It cannot see private Search Console, analytics, CMS settings, server logs, or authenticated pages unless the user provides access in the current environment.
- AI crawler names and policies change. `references/ai-crawlers.md` includes a current baseline and tells Codex to recheck official docs before making strict claims.
- Scores are communication aids, not guaranteed ranking predictions.
- Missing `llms.txt` is not treated as a Google Search defect.

## Validate

From any directory, run Codex's skill validator against this repo:

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py /path/to/geo-seo-audit
```

Expected result:

```text
Skill is valid!
```
