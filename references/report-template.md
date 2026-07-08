# Report Template

Use this shape for the final response. Keep it short enough for business users.

## Single-Site Report

```markdown
## <domain> SEO/GEO Audit

Overall: <A/B/C/D> (<score>/100)
Diagnosis: <one plain-language sentence>

### Priority Fixes
1. <fix> — <why it matters> — <owner: content/dev/business>
2. <fix> — <why it matters> — <owner>
3. <fix> — <why it matters> — <owner>

### Traditional SEO
| Item | Status | Plain-language finding |
|---|---|---|
| Crawl/index | Pass/Warn/Fail | ... |
| Titles/descriptions | Pass/Warn/Fail | ... |
| Sitemap/internal links | Pass/Warn/Fail | ... |
| Structured data | Pass/Warn/Fail/Unconfirmed | ... |

### GEO / AI Search
| Item | Status | Plain-language finding |
|---|---|---|
| AI crawler access | Pass/Warn/Fail/Unconfirmed | ... |
| JS/rendering risk | Pass/Warn/Fail | ... |
| Citable evidence | Pass/Warn/Fail | ... |
| Entity trust | Pass/Warn/Fail | ... |
| llms.txt | Info only | ... |

### Evidence Checked
- Pages sampled: <URLs>
- Files checked: robots.txt <status>, sitemap.xml <status>, llms.txt <status>
- Not automatically verified: <items>
```

## Competitor Report

```markdown
## SEO/GEO Comparison

| Area | Your Site | Competitor | Gap |
|---|---:|---:|---|
| Crawl/index foundation | <score> | <score> | <summary> |
| SEO basics | <score> | <score> | <summary> |
| GEO content readiness | <score> | <score> | <summary> |
| Entity trust | <score> | <score> | <summary> |

Biggest opportunity: <one action that gives the highest leverage>
```

## Tone Rules

- Explain technical terms the first time they appear.
- Use "confirmed", "not found", "blocked", and "not automatically verified" precisely.
- Do not bury the top fixes under a long checklist.
- Avoid fear-based language. Say what the issue affects and what to do next.
