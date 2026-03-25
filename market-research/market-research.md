---
name: market-research
description: Perform comprehensive market research, competitor analysis, and communication angle discovery for any product, service, or business idea. Use this skill when the user asks for market research, competitive analysis, competitor benchmarking, market sizing, target audience profiling, communication strategies, marketing angles, positioning analysis, or any combination of these. Triggers on requests like "analyze the market for X", "find competitors for X", "research marketing angles", "do a competitive analysis", or "help me understand the market".
---

# Market Research Skill

Perform a structured, multi-phase research process and compile all findings into a single comprehensive output file.

## Workflow

### Phase 1: Briefing

Before starting research, clarify with the user:

1. **Product/Service/Idea** - What exactly is being researched?
2. **Geographic market** - Local, national, international? Which countries?
3. **Target audience** (if known) - Who is the intended customer?
4. **Budget range** (if relevant) - Helps contextualize competitor tiers
5. **Output language** - What language for the final report?

If the user has already provided sufficient context, skip redundant questions and proceed.

### Phase 2: Market Research

Use WebSearch extensively. Investigate:

- **Market size and trends** - TAM, SAM, SOM estimates; growth rate; key trends
- **Industry dynamics** - Major players, market structure, entry barriers, regulations
- **Target segments** - Demographics, psychographics, behaviors, pain points, unmet needs
- **Demand signals** - Search volume trends, social media sentiment, forum discussions, review patterns

Search queries to run (adapt to the specific market):
- `[industry] market size [year] [geography]`
- `[industry] trends [year]`
- `[industry] target audience demographics`
- `[product type] consumer behavior trends`
- `[industry] challenges problems [year]`

### Phase 3: Competitor Research

Identify and analyze **at least 8-12 competitors** across three tiers:

- **Direct competitors** (same product/service, same audience)
- **Indirect competitors** (different product, same need)
- **Aspirational/adjacent** (larger players or adjacent markets worth monitoring)

For each competitor, research:

| Dimension | Details to gather |
|---|---|
| Company overview | Name, website, founding year, location, size |
| Product/Service | Core offering, pricing model, key features |
| Positioning | Tagline, value proposition, brand tone |
| Channels | Website, social media, ads, content marketing, PR |
| Strengths | What they do well, unique advantages |
| Weaknesses | Gaps, complaints, negative reviews, missing features |
| Audience | Who they target, how they segment |

Search queries to run:
- `[product type] best [year]`
- `[product type] alternatives`
- `[product type] vs`
- `[competitor name] reviews`
- `[competitor name] pricing`
- `site:reddit.com [product type] recommendations`
- `site:trustpilot.com [competitor name]` or similar review sites

### Phase 4: Communication Angles

Based on market and competitor findings, identify **at least 5-8 communication angles**. For each angle provide:

1. **Angle name** - Short label (e.g., "The Affordable Expert")
2. **Core message** - One sentence that captures the angle
3. **Target emotion** - What feeling it triggers (trust, urgency, aspiration, relief, etc.)
4. **Supporting evidence** - Market data or competitor gap that validates this angle
5. **Channel fit** - Where this angle works best (social, email, landing page, ads, PR)
6. **Example headline** - A concrete headline or tagline using this angle

Angle discovery approach:
- Identify gaps in competitor messaging
- Find underserved pain points from review analysis
- Spot emerging trends competitors haven't addressed
- Look for emotional triggers in the audience's language
- Analyze what messaging resonates in adjacent markets

### Phase 5: Compile the Report

Write the complete report to a Markdown file in the user's working directory. Use the filename pattern: `market-research-[topic].md`

## Report Structure

```markdown
# Market Research Report: [Topic]
**Date:** [date]
**Market:** [geography]

---

## Executive Summary
[3-5 bullet points with the most critical findings]

## 1. Market Overview
### 1.1 Market Size & Growth
### 1.2 Key Trends
### 1.3 Industry Dynamics & Barriers

## 2. Target Audience
### 2.1 Primary Segments
### 2.2 Pain Points & Unmet Needs
### 2.3 Behavioral Insights

## 3. Competitive Landscape
### 3.1 Competitor Map (overview table)
### 3.2 Direct Competitors (detailed profiles)
### 3.3 Indirect Competitors (detailed profiles)
### 3.4 Key Takeaways & Gaps

## 4. Communication Angles
### 4.1 Angle Overview (summary table)
### 4.2 Detailed Angle Profiles
### 4.3 Recommended Priority Angles

## 5. Strategic Recommendations
[Actionable next steps based on all findings]

## Sources
[List all URLs and sources used]
```

## Guidelines

- Cite sources with URLs wherever possible
- Use tables for competitor comparisons — they are easier to scan
- Prefer recent data (current year or last 12 months)
- Flag when data is estimated vs. confirmed
- If a market is too niche for public data, state this explicitly and provide proxy estimates
- Write in a professional but accessible tone
- The report should be thorough: aim for 2000-4000 words minimum
