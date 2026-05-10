# Course Strategy Context

Use this skill when working on anything related to Skanda's paid cohort course, the landing page, email copy, curriculum, or funnel strategy.

---

## Who Skanda Is

- Senior data scientist at Intuit Mailchimp, building GenAI content personalization for millions of users
- O'Reilly instructor: teaches live courses on **GenAI in Production** and **Context Engineering**
- Author of the O'Reilly book: *Retrieval Augmented Generation in Production with Haystack*
- Personal site: skandavivek.com (Jekyll/GitHub Pages, Minimal Mistakes theme)
- Business site: chaoscontrol.net (also GitHub Pages static site)
- Medium blog: ~30k monthly readers
- Mailchimp newsletter: ~300 subscribers (warm — signed up but never emailed)
- Substack: hundreds of subscribers, inconsistent posting history
- LinkedIn: active, engaged audience
- Twitter/X: exists but dormant (@skandavivek)

---

## The Course

### Positioning
**"Your LLM feature is live. Now make it actually work."**

Target: **Version B engineers** — not beginners. Engineers who have already shipped a GenAI feature and now own keeping it reliable. They have a system in production, they're responsible for it, and it's held together with duct tape.

This is a **paid cohort** — not free. Skanda collects signups via the landing page and sends enrolled students a payment link directly.

### Why This Over O'Reilly
O'Reilly courses are broad by design. This cohort is smaller (15–20 people max), more hands-on, sequenced around a broken system rather than concepts, and includes live back-and-forth that O'Reilly's format can't provide. It's a deeper extension, not a competitor. Skanda values his O'Reilly relationship — framing should always position this as complementary.

### Curriculum (4 weeks, ~2 hrs live/week)

**Week 1 — Diagnose**
Map LLM failure modes (hallucination, refusal, drift, latency). Build evals from real production traffic. Set a baseline before changing anything. Distinguish model problems from context problems.

**Week 2 — Context Engineering**
System prompt architecture that scales. Managing conversation state without ballooning costs. What belongs in context vs. what doesn't. The patterns that separate reliable apps from janky demos.

**Week 3 — Retrieval**
When RAG helps vs. hurts. Chunking, embedding, re-ranking decisions that matter in production with real messy data (not clean PDFs). Measuring retrieval quality end-to-end. Hybrid search.

**Week 4 — Production**
Guardrails, fallbacks, graceful degradation. Cost and latency monitoring that catches drift early. The operational playbook for keeping it working post-launch. When to retrain, fine-tune, or just fix the prompt.

### Pricing
- First cohort: ~$700/person
- Raise to ~$997 after testimonials
- Internal target: 8–10 students to start; 15–20 is the goal

### Format
- 4 live sessions, evenings or weekends
- Async Slack/Discord Q&A between sessions
- Session recordings included
- Pre-work question on signup: "describe your current GenAI system and the biggest thing that's broken"

---

## The Funnel

1. **Landing page** at `skandavivek.com/course/` — exists, built this session
   - Headline + 4-week curriculum cards + Mailchimp signup form
   - No price shown on page — Skanda sends payment link after signup
   - **Form must use a dedicated Mailchimp embed** that auto-tags signups as `cohort-waitlist` — NOT the general newsletter form. This is how course-intent signups are distinguished from regular subscribers. Steps: Mailchimp → Audience → Signup forms → Embedded forms → create new form → set auto-tag to `cohort-waitlist` → copy new `f_id` embed code → paste into `_pages/course.md`.
2. **Email to 300 Mailchimp subs** — announce waitlist, link to landing page (these 300 are untagged general subs; do not retag them unless they click through and sign up on the course page)
3. **One LinkedIn post** — short, one paragraph, link to landing page
4. **Wait 2 weeks** — reply personally to every interested person
5. **Decision gate**: 15+ `cohort-waitlist` tagged signups → send sales email with dates + payment link; 8–14 → run it anyway; under 8 → diagnose before canceling
6. **Payment**: Gumroad or Stripe — set up only when ready to sell, not before

### Mailchimp Tag Taxonomy
- `cohort-waitlist` — signed up via course landing page, high intent, expects a payment link
- (untagged) — general newsletter subscriber, signed up elsewhere, lower funnel stage
- Future tags as needed: `cohort-1-enrolled`, `cohort-1-alumni`, `newsletter-only`

---

## Constraints and Preferences

- Has a day job at Intuit — course runs on evenings/weekends, once a week live
- Does NOT want aggressive self-promotion — LinkedIn posts should feel natural, not spammy
- Wants to protect the O'Reilly relationship — never frame cohort as replacing or competing with O'Reilly
- Previously got blocked on newsletters (Substack stalled at ~100, gaps in posting) — the blocker was inconsistency + no distribution flywheel, not content quality
- Prefers shipping over perfecting infrastructure
- Claude can help draft emails, copy, and curriculum — but Skanda's voice must come through; AI-sounding content kills trust

---

## Key Decisions Already Made

- **Paid, not free** — Skanda sends a payment link to signups, not a free course
- **Cohort-first (A), then self-paced course (B)** — cohort validates curriculum and funds production of the async course
- **Consulting (C) is tabled** — right call, requires sales muscle that's a different effort
- **chaoscontrol.net / skandavivek.com** as the primary home, not Substack or Carrd
- **Version B audience** (engineers who shipped, not engineers who are starting)

---

## What Not To Do

- Don't call the course free anywhere
- Don't build payment infrastructure before validating demand
- Don't send multiple promotional emails — one email, one LinkedIn post, then wait
- Don't redesign the site or over-engineer the funnel before the first cohort fills
- Don't position this as competing with O'Reilly
