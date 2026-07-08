# Report Template

Use this shape for the final response. Keep it short enough for business users while still feeling like a polished audit report.

## Formatting Rules

- Lead with the score, diagnosis, and top fixes before any checklist.
- Use status labels consistently: `PASS`, `WARN`, `FAIL`, `INFO`, `UNCONFIRMED`.
- Use compact tables for scanability.
- Use short score bars when helpful: `SEO basics       18/25  [#######---]`.
- Group optimization suggestions by owner so the user knows who should act.
- Avoid dense paragraphs. One finding should usually be one sentence.
- If the environment can render HTML/widgets, create a card-style visual report. If not, use the polished Markdown below.

## Single-Site Report

```markdown
# <domain> SEO/GEO Audit

Overall Grade: <A/B/C/D>  |  Score: <score>/100  |  Risk: <Low/Medium/High>

Diagnosis:
<one plain-language sentence that explains the biggest SEO/GEO constraint.>

## Scorecard

| Area | Score | Status | Plain-language meaning |
|---|---:|---|---|
| Crawl/index foundation | <n>/25 | PASS/WARN/FAIL | Can search engines and AI systems reach the important pages? |
| Page-level SEO basics | <n>/25 | PASS/WARN/FAIL | Do pages clearly explain what they are about? |
| GEO content readiness | <n>/30 | PASS/WARN/FAIL | Does the content contain facts AI systems can cite? |
| Entity and third-party trust | <n>/10 | PASS/WARN/FAIL | Does the wider web confirm the brand is real and credible? |
| Fix clarity and business impact | <n>/10 | PASS/WARN/FAIL | Are the next actions clear and worth doing first? |

## Priority Fixes

| Priority | Fix | Owner | Why it matters |
|---:|---|---|---|
| 1 | <highest-impact fix> | Developer/Content/Business | <plain-language impact> |
| 2 | <second fix> | Developer/Content/Business | <plain-language impact> |
| 3 | <third fix> | Developer/Content/Business | <plain-language impact> |

## Traditional SEO

| Item | Status | Finding | Recommended action |
|---|---|---|
| Crawl/index | PASS/WARN/FAIL | <finding> | <action> |
| Titles/descriptions | PASS/WARN/FAIL | <finding> | <action> |
| Sitemap/internal links | PASS/WARN/FAIL | <finding> | <action> |
| Structured data | PASS/WARN/FAIL/UNCONFIRMED | <finding> | <action> |

## GEO / AI Search

| Item | Status | Finding | Recommended action |
|---|---|---|
| AI crawler access | PASS/WARN/FAIL/UNCONFIRMED | <finding> | <action> |
| JS/rendering risk | PASS/WARN/FAIL | <finding> | <action> |
| Citable evidence | PASS/WARN/FAIL | <finding> | <action> |
| Entity trust | PASS/WARN/FAIL | <finding> | <action> |
| llms.txt | INFO | <finding> | <action> |

## Optimization Plan

### Developer
- <technical fix, expected impact, verification method>

### Content
- <content fix, expected impact, example of better wording/data>

### Business / Marketing
- <trust, third-party profile, reviews, case study, or entity consistency fix>

## Evidence Checked
- Pages sampled: <URLs>
- Files checked: robots.txt <status>, sitemap.xml <status>, llms.txt <status>
- Tool notes: <any fetch/browser/search disagreement worth mentioning>
- Not automatically verified: <items>

## Skill Self-Check
- <optional: one pattern this audit revealed that the skill should handle better next time, or "No skill gaps observed.">
```

## Competitor Report

```markdown
# SEO/GEO Comparison

| Area | Your Site | Competitor | Gap |
|---|---:|---:|---|
| Crawl/index foundation | <score> | <score> | <summary> |
| SEO basics | <score> | <score> | <summary> |
| GEO content readiness | <score> | <score> | <summary> |
| Entity trust | <score> | <score> | <summary> |

## Best Opportunity

<one action that gives the highest leverage, written in plain language>

## Action Plan

| Priority | Your move | Why it beats/keeps up with competitor |
|---:|---|---|
| 1 | <action> | <reason> |
| 2 | <action> | <reason> |
| 3 | <action> | <reason> |
```

## Tone Rules

- Explain technical terms the first time they appear.
- Use "confirmed", "not found", "blocked", and "not automatically verified" precisely.
- Keep tool failures separate from confirmed site defects.
- Do not bury the top fixes under a long checklist.
- Avoid fear-based language. Say what the issue affects and what to do next.
