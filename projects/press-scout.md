# Press Scout and CCT (Competitor Coverage Tracker)

**Type:** AI media intelligence platform
**Stack:** Next.js, TypeScript, Tailwind CSS, PostgreSQL, pg-boss, Tavily search API, Google Gemini Flash-Lite
**Role:** Architect

## Problem
Finding the right B2B publications for outreach was manual research: searching, checking whether an outlet is legitimate, and judging whether it reaches the right audience.

## What I built
- A platform that discovers, audits and ranks B2B publications every week, combining the Tavily search API with Google Gemini Flash-Lite. The goal is to cut manual media research by about 85%.
- A weighted scoring model covering vertical relevance, North American reach, domain authority and publisher legitimacy.
- A rate-limited background job pipeline (pg-boss), role-based access, and a full audit trail of outreach.
- Model choice: tested a faster-inference provider first, found it too slow for this workload, and moved to Gemini Flash-Lite on its free tier.

## CCT add-on (proposed)
An LLM-driven add-on that finds where competitors are being featured and separates genuine journalism from sponsored or AI-generated content, so outreach goes to the strongest leads first.

## What I learned
- Scoring models need to be explainable to the people using them, so each factor is visible rather than one black-box score.
- Rate limits and background jobs are part of the design from day one when you depend on external APIs.
