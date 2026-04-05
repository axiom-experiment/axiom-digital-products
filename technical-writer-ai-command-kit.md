# Technical Writer's AI Command Kit
## 55 Expert Prompts for Documentation Professionals

**Product ID:** PROD-006
**Price:** $14.99
**Format:** Markdown + JSON
**Category:** Technical Writing & Documentation
**Target Audience:** Technical writers, developer advocates, documentation engineers, API writers, DevRel professionals

---

## Why This Pack Exists

Good documentation is a force multiplier for every product. Bad documentation is a silent customer churn machine.

But documentation is also relentless work: API references, onboarding guides, tutorials, changelogs, error messages, style guides, release notes, migration paths. The writing itself is the smallest part — the structure, the research, the iteration cycles, the consistency across thousands of pages are where documentation teams burn time.

These 55 prompts are distilled from professional technical writing practice. They don't produce placeholder content — they produce *structure, critique, and drafts that professionals can actually build on*. Each prompt includes a specific role priming instruction, a clear task definition, and quality criteria that match real documentation standards.

---

## SECTION 1: API Reference Documentation (10 Prompts)

**1. API Endpoint Documentation Generator**
```
You are a senior technical writer with 10 years of experience writing API reference documentation for developer platforms (Stripe, Twilio, Vercel level quality).

Document the following API endpoint completely:

Endpoint: [METHOD] [URL]
Purpose: [what this endpoint does]
Auth required: [yes/no, type]
Request body schema: [JSON schema or describe fields]
Response schema: [JSON schema or describe fields]
Error codes: [list of possible error codes and meanings]

Produce:
1. A one-paragraph description of what this endpoint does and when to use it
2. A complete parameters table (name | type | required | description | example)
3. A request example with real-looking sample data (not foo/bar placeholders)
4. A success response example (formatted JSON)
5. An error response example (formatted JSON)
6. A "Common mistakes" section with the top 3 errors developers make with this endpoint

Format as production-ready Markdown suitable for a docs site.
```

**2. Authentication Flow Documentation**
```
You are a developer advocate writing authentication documentation for developers who are integrating an API for the first time. Your goal is zero support tickets from auth-related confusion.

Write a complete authentication guide for the following:

Auth type: [API key / OAuth 2.0 / JWT / other]
Flow description: [describe the auth flow in plain English]
Headers required: [what headers the developer must send]
Token format: [what does the token look like?]
Expiry: [does the token expire? how to refresh?]

Produce:
1. A plain-English explanation of how auth works (1 paragraph, no jargon)
2. Step-by-step authentication walkthrough with numbered steps
3. Code examples in: JavaScript (fetch), Python (requests), and cURL
4. A "Troubleshooting auth errors" section covering: 401, 403, token expiry, invalid format
5. Security best practices section (what NOT to do — e.g., don't put tokens in URLs)

Write for a developer who is competent but has never used this API before.
```

**3. Rate Limiting Documentation**
```
You are a technical writer documenting API rate limits. Developers hate surprises. Your job is to eliminate all rate-limit-related surprises before they happen in production.

Write complete rate limiting documentation for:

Rate limit: [X requests per Y time window]
Rate limit scope: [per API key / per IP / per user / per endpoint]
Rate limit headers: [what headers does the API return?]
Retry behavior: [does the API return a Retry-After header?]
Burst behavior: [any burst allowances?]
Different limits by tier: [if applicable]

Produce:
1. Clear explanation of how rate limits work in this API
2. A table showing limits by tier/scope if applicable
3. How to monitor your current rate limit status (with header examples)
4. A production-ready retry-with-backoff code example in JavaScript
5. "Rate limit best practices" section (caching strategies, request batching, etc.)
6. FAQ section for the top 5 questions developers ask about rate limits
```

**4. Webhook Documentation Writer**
```
You are a senior technical writer. Webhooks are notoriously tricky to document well — developers fail to implement them correctly 40% of the time due to poor documentation.

Write complete webhook documentation for:

Event types: [list of webhook events, e.g., payment.succeeded, user.created]
Payload structure: [describe the webhook payload schema]
Signature verification: [how to verify the webhook signature]
Delivery guarantees: [at-least-once? exactly-once? retry policy?]
HTTPS requirement: [yes/no]

Produce:
1. Introduction explaining when webhooks fire and why developers use them vs polling
2. Complete event catalog table (event name | when it fires | payload summary)
3. Full payload example for the most common event (realistic JSON)
4. Signature verification implementation in JavaScript and Python
5. Retry behavior explanation with a failure/retry timeline diagram (ASCII)
6. Testing webhooks locally section (recommend ngrok or similar approach)
7. "Webhook security checklist" — 6 security requirements before going to production
```

**5. SDK Method Documentation Template**
```
You are documenting a software SDK method. Your documentation must be precise enough that a developer can use this method correctly without reading the source code.

Method details:
Name: [method name]
SDK: [language — JavaScript/Python/Go/etc.]
Module: [which module/class this belongs to]
Description: [what this method does]
Parameters: [list name, type, required/optional, description]
Returns: [what type does this return?]
Throws/Errors: [what errors can this raise?]
Async: [yes/no]

Produce:
1. Method signature (properly formatted for the language)
2. Parameter table with types, required status, defaults, and descriptions
3. Return value documentation with type and structure
4. 3 usage examples ordered from simplest to most complex
5. Error handling example showing how to catch/handle the documented errors
6. "Notes" section with gotchas, edge cases, and performance considerations
```

**6. Data Model / Schema Documentation**
```
You are a technical writer documenting a data model for a developer reference guide. Developers will rely on this documentation when writing code that handles this data — accuracy is critical.

Document this data model:
Object name: [e.g., User, Order, Transaction]
Context: [what is this object? when does it appear in API responses?]
Fields: [list all fields with name, type, nullable status, description]
Relationships: [does this object contain nested objects? reference other objects by ID?]
Timestamps: [which fields are timestamps? what format/timezone?]
Computed fields: [any fields derived from others?]

Produce:
1. One-paragraph description of what this object represents in the system
2. Complete field reference table (field | type | nullable | description | example value)
3. A full example JSON object with realistic, non-placeholder values
4. Relationship diagram in ASCII showing connections to other objects
5. Notes on immutable fields, system-generated fields, and write-protected fields
6. Common patterns for working with this object (3 practical code snippets)
```

**7. Error Code Reference Documentation**
```
You are a technical writer creating an error code reference. This is the documentation developers will have open in another tab when something goes wrong at 2am. Make it useful under pressure.

Error catalog:
[List your error codes, e.g.:
ERR_001: Authentication failed
ERR_002: Resource not found
ERR_003: Rate limit exceeded]

For each error code, produce:
1. Error code and name
2. HTTP status code (if applicable)
3. Plain English description: what this error means
4. Common causes: the top 3 reasons this error occurs
5. Resolution steps: numbered list of what to do to fix it
6. Example API response showing this error (formatted JSON)
7. Prevention: how to avoid this error in the first place

Format as a scannable reference table at the top (code | status | short description), then detailed entries below.
```

**8. Pagination Documentation**
```
You are documenting how pagination works in a developer API. Pagination is one of the top sources of developer confusion. Your goal: zero ambiguity.

Pagination type: [cursor / offset / page-number / link-header]
Max page size: [X items per page]
Default page size: [Y items]
Pagination parameters: [describe the parameters]
Response metadata: [what pagination data is in the response?]
Total count behavior: [is total count returned? always? optionally?]

Produce:
1. Clear explanation of the pagination model and why this approach was chosen
2. Complete parameter reference table with defaults and limits
3. A first-page request example and response (with realistic JSON)
4. A subsequent page request example showing how to use the cursor/next page token
5. How to fetch ALL records in a loop — complete code example in JavaScript
6. Edge cases: what happens on the last page, what happens with zero results, empty pages
7. Performance tips: when to use small vs large page sizes
```

**9. Changelog Entry Writer**
```
You are a technical writer translating internal engineering notes into a developer-facing changelog. Changelogs are a trust signal — good ones make developers feel safe upgrading. Bad ones cause production incidents from unexpected breaking changes.

Engineering notes: [paste raw engineering notes, commit messages, or PR descriptions]
Version: [X.Y.Z]
Release type: [major / minor / patch]
Release date: [YYYY-MM-DD]
Breaking changes: [yes/no — if yes, describe]

Produce a developer-facing changelog entry with:
1. Version number and date as heading
2. Breaking changes section (if any) — formatted prominently with ⚠️ warning
3. New features — what was added and why it's useful
4. Improvements — what got better
5. Bug fixes — what was broken and is now fixed (no internal ticket numbers)
6. Deprecations (if any) — what is deprecated, what to use instead, timeline for removal
7. Migration guide (for breaking changes only) — numbered steps to upgrade

Write for the developer who skims changelogs looking for "does this break my code."
```

**10. API Quickstart Guide**
```
You are writing a quickstart guide. This is the most important document in your API documentation — it's what a developer reads in the first 10 minutes of evaluating your product. Your success metric: the developer makes their first successful API call in under 5 minutes.

API name: [name]
Core use case: [what is the #1 thing developers use this API for?]
Auth method: [how do developers authenticate?]
Simplest possible call: [describe the simplest meaningful API call]
Languages to cover: [e.g., JavaScript, Python, cURL]

Produce:
1. Headline: "Make your first [API name] API call in 5 minutes"
2. Prerequisites section (2-3 items max — anything more is friction)
3. Step 1: Get your API key (with screenshot callout placeholder)
4. Step 2: Install the SDK or set up headers
5. Step 3: Make the first call — complete working code in each specified language
6. Step 4: Understand the response — annotated JSON breakdown
7. "What's next" section — 3 links to the next natural documentation pages
8. Troubleshooting section — the top 3 errors a developer sees in the first 5 minutes

Every code example must be complete and runnable. No ellipsis (...), no "add your code here." If a developer copy-pastes this, it must work.
```

---

## SECTION 2: Tutorial & How-To Writing (10 Prompts)

**11. Tutorial Structure Architect**
```
You are a curriculum designer for developer education. You've written tutorials for Stripe, AWS, and Vercel. Your tutorials are known for being completed (not abandoned) because of their precise pacing and clear outcomes.

Tutorial brief:
Topic: [what is this tutorial about?]
Audience: [who is this for? what do they already know?]
Goal: [what can the reader DO after completing this tutorial?]
Estimated time: [X minutes]
Technology stack: [what technologies are involved?]

Design a complete tutorial outline with:
1. A one-paragraph learning objective statement (what the reader will build/achieve)
2. Prerequisites section (be specific — "basic JavaScript" is useless; "you know how to write async/await" is useful)
3. Full outline with section headings and a sentence describing what each section covers
4. Key code checkpoint moments (where to include "your code should look like this now" verification steps)
5. A "What you built" summary for the conclusion
6. Suggested follow-up tutorials (3 next steps)
7. Estimated reading time per section

The outline should feel like a journey with a clear destination, not a reference document.
```

**12. "Explain Like I'm a Senior Dev" Rewriter**
```
You are a technical editor. The text below was written for a general audience but the target readers are senior software engineers. Senior devs are impatient with over-explanation, hate condescension, and respond well to precision, nuance, and honest trade-off analysis.

Original text: [paste the text to be rewritten]

Rewrite the text for senior software engineers:
1. Remove any over-explanation of basics (they know what a JSON object is)
2. Add technical precision where it's vague
3. Surface the trade-offs and edge cases — senior devs want the honest picture
4. Replace hedging language ("might", "could be used to") with direct statements
5. Preserve all factual content — only change tone, depth, and framing
6. Target: the senior dev reads this and says "yes, this is accurate and complete"
```

**13. Conceptual Explanation Writer**
```
You are a technical writer who specializes in explaining abstract concepts. Your mental model: every concept has a 3-layer explanation — the analogy (for intuition), the mechanism (for understanding), and the implication (for application).

Concept to explain: [e.g., "how OAuth 2.0 works", "what event-driven architecture is", "why database indexing matters"]
Audience: [what level of technical knowledge do they have?]
Context: [where will this explanation appear — quickstart? reference docs? onboarding?]

Produce a 3-layer explanation:

Layer 1 — The Analogy (2-3 sentences): Use a real-world comparison that creates intuition without technical jargon. The analogy should be accurate, not just vaguely similar.

Layer 2 — The Mechanism (3-4 paragraphs): How it actually works. Use technical terms but define them. Include a simplified diagram in ASCII if helpful.

Layer 3 — The Implication (1-2 paragraphs): Why this matters for the reader's work. What decisions does understanding this concept enable? What mistakes does it prevent?

End with a "Key takeaway" — one sentence that the reader should remember a week later.
```

**14. Step-by-Step Guide Writer**
```
You are a technical writer creating a procedural guide. Your rules: one action per step, every step has a clear expected outcome, no step is ambiguous.

Task to document: [describe the task the reader needs to accomplish]
Environment: [OS, tools, versions]
Starting state: [what does the reader's environment look like before they start?]
End state: [what does the environment look like when they're done?]

Write a step-by-step guide:
1. Title: "How to [accomplish the task]"
2. Prerequisites: explicit list (no implied prerequisites)
3. Time estimate: X minutes
4. Numbered steps — each step contains:
   - The action (imperative verb: "click", "run", "paste", "navigate to")
   - The command or code (if applicable, in a code block)
   - The expected output or result (so the reader knows the step worked)
5. After the final step: verification section — how does the reader confirm everything worked?
6. Troubleshooting: the top 3 places where this procedure goes wrong and how to recover

Format every command in a code block. Use screenshots callouts [Screenshot: X] for UI steps.
```

**15. Comparison/Decision Guide Writer**
```
You are a technical writer creating a decision guide to help developers choose between options. Good decision guides are honest about trade-offs and provide a clear recommendation for the most common cases, while being fair to alternatives.

Options to compare: [list 2-4 options, e.g., "REST vs GraphQL vs gRPC"]
Decision context: [what decision is the reader making? what are they trying to build?]
Reader profile: [who is asking this question? what do they care about?]

Write a comparison guide:
1. Introduction — frame the decision: when does this choice matter? (1 paragraph)
2. A comparison table with rows for key criteria (performance, complexity, ecosystem, use cases, learning curve) and a column per option
3. For each option, a 2-paragraph description: strengths first, then honest weaknesses
4. The "when to choose X" section — a bullet list of the specific conditions that make each option the right choice
5. A recommendation section: "For most teams building [X], we recommend [Y] because..."
6. "What we didn't cover" — 2-3 factors outside the scope of this guide that might change the recommendation
```

**16. Migration Guide Writer**
```
You are a technical writer creating a migration guide. Migrations are high-stakes documentation — developers follow these step-by-step while their production system is in a state of change. Errors in this documentation cause outages.

Migration context:
From: [version/system/approach being migrated from]
To: [version/system/approach being migrated to]
Breaking changes: [list the breaking changes developers will encounter]
Migration complexity: [simple / moderate / complex]
Downtime expected: [yes/no]

Produce a production-grade migration guide:
1. Migration overview — what's changing and why (1 paragraph)
2. ⚠️ Breaking changes — a clearly formatted table of every breaking change, old behavior, new behavior, and required action
3. Prerequisites — what must be true before starting (versions, backups, etc.)
4. Migration steps — numbered, one action per step, with before/after code examples for every breaking change
5. Verification steps — how to confirm the migration succeeded
6. Rollback procedure — how to undo the migration if something goes wrong
7. Common issues — the top 5 migration failures and their resolutions

Every code example must show BOTH the old code and the new replacement. No "update your code to use the new API" — show exactly what changes.
```

**17. Onboarding Documentation Sequence**
```
You are a technical writer designing a documentation onboarding sequence. The goal: a new user of your product goes from "signed up" to "first value delivered" in the minimum possible time.

Product: [what does this product do?]
Core value moment: [what is the "aha moment" — the first time the user sees real value?]
User's starting knowledge: [what do they know? what don't they know?]
Typical first-use path: [describe what a new user typically does first]

Design a 5-document onboarding sequence:
1. Document 1: "Getting Started" — covering account setup, first login, environment setup. Target: 3 minutes to complete.
2. Document 2: "Your First [Core Use Case]" — the quickstart that delivers the first value moment. Target: 5 minutes.
3. Document 3: "Key Concepts" — the 5-7 concepts the user needs to understand to use the product confidently.
4. Document 4: "Common Workflows" — 3-5 documented patterns for the most frequent use cases.
5. Document 5: "Next Steps" — personalized paths based on use case (developer / admin / power user).

For each document: title, purpose (1 sentence), what the user can do after reading it, estimated read time, and 5-bullet content outline.
```

**18. Troubleshooting Guide Writer**
```
You are writing a troubleshooting guide. This documentation will be read by frustrated people at bad times. Your job: get them unstuck as fast as possible.

Product/feature: [what is the user having trouble with?]
Top 5 issues: [list the most common problems users encounter]
Available diagnostic information: [what logs, error codes, or outputs can the user check?]

For each issue, produce a troubleshooting entry:

## [Symptom in plain English — e.g., "API returns 401 errors after token refresh"]

**What this means:** [plain English explanation of what's happening]

**Quick diagnostic:** [the first thing to check — one step]

**Causes:**
1. [Most common cause] — [how to identify it] → [how to fix it]
2. [Second cause] — [how to identify it] → [how to fix it]
3. [Third cause] — [how to identify it] → [how to fix it]

**If none of the above:** [escalation path — what information to collect before contacting support]

Format each entry identically so frustrated users can scan and pattern-match to their problem quickly.
```

**19. Feature Announcement / Release Notes Writer**
```
You are writing feature announcement copy that will appear in release notes, in-app notifications, and documentation. Developers read release notes during upgrades — they're looking for "what broke" and "what's new that I should use." Win on both.

Feature/release: [describe what's new]
Who benefits: [which users does this affect?]
Migration required: [yes/no]
Old behavior (if changed): [what did this do before?]
New behavior: [what does it do now?]

Write three versions:
1. Release notes entry (50-100 words) — neutral technical tone, factual, includes code example if behavior changed
2. In-app announcement (25 words max) — what it is + one clear benefit, present tense
3. Documentation callout box (75 words) — for embedding in existing docs pages, "As of v[X.Y], you can now..."

For any breaking change or behavior modification, ensure all three versions include a migration note or link.
```

**20. "Why Does This Exist?" Conceptual Intro Writer**
```
You are writing the introduction to a documentation section. Too many docs jump straight to instructions without explaining why the reader should care. You fix this.

Documentation section: [what topic does this section cover?]
Problem being solved: [what pain does this feature/concept address?]
Reader profile: [who is reading this?]

Write a 3-paragraph "why this exists" introduction:
Paragraph 1 — The Problem: Describe the situation the reader is likely in when they need this feature. Make them feel understood. No marketing language.
Paragraph 2 — The Solution: Explain what this feature/concept does and how it solves the problem. Be concrete. Avoid superlatives.
Paragraph 3 — What to expect: Tell the reader what they'll understand or be able to do after reading this section. Set accurate expectations — no over-promising.

This intro should make the reader feel: "yes, I'm in the right place, let's go."
```

---

## SECTION 3: Documentation Architecture & Strategy (8 Prompts)

**21. Documentation Site Architecture Planner**
```
You are a documentation architect. You've designed the information architecture for developer documentation used by hundreds of thousands of developers. Your framework: every doc site has a left-nav that tells the complete story of the product before a single word is read.

Product: [describe the product]
User types: [who uses this product? e.g., developers, admins, end users]
Core workflows: [what are the top 5 things users do with this product?]

Design a complete documentation site architecture:
1. Top-level navigation structure (max 6 sections) with one-sentence purpose per section
2. For each section: 5-8 document titles and the primary question each document answers
3. Recommended landing page structure for each top-level section
4. Cross-linking strategy: which sections should reference each other and when
5. What belongs in the API reference vs the conceptual guides vs the tutorials (decision framework)
6. Documents to prioritize for initial launch vs documents that can wait for V2

Output as a structured outline that a documentation team could use as a working document for a 3-month documentation project.
```

**22. Doc Audit & Gap Analysis**
```
You are a documentation auditor. You've been hired to audit a documentation site and produce an actionable gap analysis report.

Current documentation inventory: [paste a list of current doc pages/URLs or describe what exists]
Product features: [list the main features of the product]
Known user pain points: [what questions does support receive most often?]

Produce a documentation gap analysis:
1. Coverage matrix: for each major feature, rate current documentation as: Complete / Partial / Missing
2. Critical gaps: documentation that is Missing for high-usage features (prioritized list)
3. Quality gaps: documentation that exists but is insufficient (list with specific issues: too brief, no examples, outdated, missing error coverage, etc.)
4. Structural issues: navigation problems, missing index pages, broken journeys
5. Quick wins: gaps that can be filled in under 1 hour (low complexity, high impact)
6. Long-term projects: gaps that require significant effort (estimate hours per item)
7. Recommended priority order for addressing gaps (impact × effort matrix)
```

**23. Documentation Style Guide Creator**
```
You are a senior technical writer creating a documentation style guide for a team of writers. The goal: documentation that looks and reads like it was written by one person, regardless of who wrote each page.

Company/product: [name]
Tone: [formal/conversational/technical]
Audience technical level: [beginner / intermediate / advanced developers]
Existing inconsistencies to resolve: [list specific style questions your team argues about]

Create a practical documentation style guide covering:
1. Voice and Tone — 5 concrete do/don't examples with rewritten samples
2. Terminology — 10-item glossary of terms used consistently (the "right" way to say things)
3. Formatting rules — headers (capitalize how?), code blocks (when?), bold/italic (when?), bullet lists vs numbered lists
4. Sentence construction — active voice rules, max sentence length, how to handle second person
5. Code examples — language, variable naming conventions, comment style, error handling inclusion
6. Screenshots — when required, caption format, alt text requirements
7. Links — internal vs external link style, when to link vs when to inline-explain
8. Update protocol — how to mark outdated content, version tagging, deprecation notices
```

**24. Docs-as-Code Workflow Designer**
```
You are a DevOps engineer and technical writer hybrid. You're designing a docs-as-code workflow for a team that wants documentation to be reviewed, versioned, and deployed like software.

Team size: [X writers + Y developers]
Current docs platform: [where docs live today]
Version control: [GitHub / GitLab / Bitbucket]
Target platform: [Mintlify / Docusaurus / GitBook / other]
Deployment target: [docs.company.com or similar]

Design a complete docs-as-code workflow:
1. Repository structure — how to organize docs alongside code
2. Branch strategy — main, drafts, version branches
3. Pull request template for documentation changes (what reviewers must check)
4. CI/CD pipeline design — lint, spell check, broken link check, build, deploy steps
5. Writer-developer collaboration protocol — who reviews what, how to handle technical reviews
6. Versioning strategy — how to maintain docs for multiple product versions simultaneously
7. Automated checks to add (vale linter rules, link checker, heading hierarchy validator)
8. Tooling recommendations with rationale (spell checker, grammar linter, diagram tool, screenshot tool)
```

**25. Content Reuse Strategy**
```
You are a content strategist for developer documentation. Content reuse reduces maintenance burden and ensures consistency — but done wrong, it creates fragile documentation that breaks silently.

Current situation: [describe what content exists and what's duplicated or inconsistent]
Documentation platform: [what tool are you using?]
Scale: [how many pages, how many products/versions?]

Design a content reuse strategy:
1. Identify reuse candidates — what types of content should be written once and reused? (authentication steps, error code tables, prerequisites blocks, legal disclaimers)
2. Decide what should NOT be reused — content that seems similar but has meaningful differences per context
3. Implementation approach for your platform — how to implement snippets/includes/partials
4. Governance model — who owns shared content? how is it updated? who is notified when shared content changes?
5. Anti-patterns to avoid — the 3 most common content reuse mistakes and how to prevent them
6. Migration plan — how to consolidate existing duplicated content without breaking links or search
```

**26. Developer-Facing Release Announcement**
```
You are a developer advocate writing a release announcement. This announcement will be posted to: the company blog, Hacker News, and the developer newsletter. Each audience is different.

Release summary: [describe what was released]
Key technical changes: [list the important technical details]
Benefits: [what problems does this release solve?]
Breaking changes: [none / describe]
Migration required: [yes/no]

Write three versions of this announcement:

Version 1 — Company blog post (400-600 words): Technical but accessible. Lead with the developer benefit, follow with implementation details, end with call to action. Include code examples.

Version 2 — Hacker News comment (150-200 words): Dense, no fluff. Assume a skeptical audience of senior engineers. Address the "why did you build it this way" question preemptively. Link to the GitHub and docs.

Version 3 — Newsletter entry (100-150 words): Conversational. Start with what changed, explain why it matters in one sentence, provide one concrete example, link to full docs.

Each version should be copy-paste ready.
```

**27. Documentation Metrics Framework**
```
You are a documentation program manager. You've been asked to propose a measurement framework for your documentation team. The challenge: documentation quality is notoriously hard to quantify, but "we can't measure it" is not acceptable when asking for headcount.

Documentation goals: [what is the documentation trying to achieve? e.g., reduce support tickets, increase product adoption, improve developer experience]
Available data sources: [what analytics do you have access to? e.g., page views, search queries, support tickets, user feedback]

Design a documentation metrics framework:
1. The 3 metrics that matter most — and why these above others
2. How to collect each metric (tools, setup, frequency)
3. Baseline-setting approach — how to establish a starting point
4. Leading indicators vs lagging indicators — which metrics predict problems vs confirm them
5. Documentation health score — a simple formula combining your top 3 metrics into one number (0-100)
6. Quarterly reporting template — what to include in a docs health report to leadership
7. Red flags — which metric values should trigger immediate documentation review
8. Anti-metrics to avoid — data that feels meaningful but leads to bad decisions (e.g., raw page views)
```

**28. Error Message Writing Guide**
```
You are a UX writer specializing in error messages. Error messages are the last line of defense between a frustrated user and a support ticket. Most error messages are written by engineers and are optimized for logging, not human understanding.

Product/system: [describe the product]
Error context: [where do these errors appear — terminal output / API response / UI / email / all of the above?]
Top errors to document: [list 5-10 common error scenarios]

For each error, write a production-quality error message following this framework:

**What happened:** [one sentence, plain English, past tense — what just failed]
**Why it happened:** [one sentence — the most likely reason]
**What to do:** [imperative — 1-3 numbered steps to resolve]
**Where to get help:** [link to relevant documentation or support]

Then write a short guide for your engineering team on error message best practices:
1. The 4 components every error message must have
2. Words and phrases to ban from error messages (and what to use instead)
3. How to write error messages for errors that aren't the user's fault
4. Localization considerations
5. 5 before/after rewrites of bad error messages
```

---

## SECTION 4: Internal Documentation & Knowledge Management (7 Prompts)

**29. Runbook / SOP Writer**
```
You are a senior SRE writing a runbook for an on-call engineer. This document will be read at 3am by someone who has just been paged. They are not fully awake. Every second of ambiguity costs real money and user trust.

Runbook topic: [what operational task or incident scenario does this cover?]
Audience: [who will run this? what do they know?]
Systems involved: [what systems/tools are needed?]
Prerequisites: [what access/permissions are needed?]

Write a production-grade runbook:
1. Title and one-sentence purpose
2. Prerequisites: access required, tools needed (with links), estimated time
3. When to use this runbook: specific triggering conditions (not "when something seems wrong")
4. Step-by-step procedure — numbered, one action per step, commands in code blocks, expected output after each step
5. Verification: how to confirm the task completed successfully
6. Escalation: when and how to escalate (with specific conditions, not "if unsure")
7. Rollback: how to undo this procedure if it makes things worse
8. Notes/gotchas: the 3 things that regularly trip people up with this procedure

This runbook should be executable by someone who has never done this specific task before but knows the systems.
```

**30. RFC / Design Document Template**
```
You are a staff engineer writing a Request for Comments (RFC) for a technical change. Good RFCs drive alignment, surface problems early, and create a permanent record of why decisions were made.

Change proposal: [describe the proposed technical change]
Problem being solved: [what problem or need drives this change?]
Scope: [what systems are affected?]
Decision deadline: [when does this need to be decided?]

Write a complete RFC following this structure:
1. Summary (3-5 sentences): What is being proposed and why, in plain English
2. Motivation: The specific problem or opportunity that drives this proposal. Quantify the impact if possible.
3. Detailed design: Technical specification of the proposed change. Include: architecture changes, API changes, data model changes, interface changes.
4. Alternatives considered: At least 2 alternatives that were evaluated, with a brief explanation of why they were rejected
5. Drawbacks: Honest assessment of the downsides and risks of the proposed approach
6. Unresolved questions: The top 3 questions that need answers before this can be approved
7. Implementation plan: Phases, timeline, rollout strategy
8. Success metrics: How will we know this worked? What do we measure?
```

**31. Postmortem / Incident Report Writer**
```
You are an SRE writing a blameless postmortem. The goal of a blameless postmortem is to understand the system failure deeply enough to prevent recurrence — not to assign fault. The best postmortems make everyone smarter.

Incident details:
What happened: [describe the incident]
Duration: [start time → end time]
Impact: [who was affected? what couldn't they do? quantify if possible]
Timeline: [key events with timestamps]
Root cause (preliminary): [your current best understanding]

Write a blameless postmortem:
1. Incident summary (3-4 sentences) — what happened, when, impact, resolution
2. Timeline — detailed chronological events with UTC timestamps
3. Contributing factors — the 3-5 system conditions that enabled this incident (NOT "the engineer who...")
4. Five Whys analysis — drilling to root cause by asking "why" at each level
5. Impact assessment — quantified user impact, revenue impact if applicable, SLO impact
6. What went well — actions taken during the incident that worked
7. What could be improved — specific gaps in process, tooling, or runbooks
8. Action items — table with: action | owner | due date | priority
9. Timeline of action item completion — follow-up date to review progress

Tone: factual, analytical, forward-looking. Zero blame language.
```

**32. Architecture Decision Record (ADR) Writer**
```
You are a staff software engineer writing an Architecture Decision Record. ADRs are permanent records of architectural decisions — they tell future engineers "why did we do it this way" and prevent the same debate from happening again in 18 months.

Decision context:
Decision: [what architectural choice was made?]
Date: [when was this decided?]
Status: [Proposed / Accepted / Deprecated / Superseded]
Deciders: [who made this decision?]
Context: [describe the situation that required this decision]

Write a complete ADR:
1. Title: "ADR-[number]: [short decision title]"
2. Status: [status with date]
3. Context: The situation that forced a decision. Describe constraints, requirements, and the problem space. Be specific about what was known at the time of the decision.
4. Decision: The chosen approach, stated plainly: "We will..."
5. Consequences — positive: what becomes easier or better
6. Consequences — negative: what becomes harder or worse (be honest)
7. Alternatives considered: 2-3 alternatives with a sentence on why each was rejected
8. Related decisions: ADRs this decision depends on or is superseded by

This ADR should make sense to an engineer reading it 3 years from now who has no other context.
```

**33. Team Onboarding Guide Writer**
```
You are writing an engineering team onboarding guide for a new hire's first week. The goal: the new engineer makes a meaningful contribution within 5 days and feels genuinely welcomed, not overwhelmed.

Team context:
Team: [what does this team build?]
Stack: [what technologies do they use?]
Key systems: [what are the 5 most important systems to understand?]
First task: [what is a typical first good-first-issue for new engineers?]

Write a 5-day onboarding plan:

Day 1 — Setup & Orientation (reading time: 30 min)
- Environment setup guide (with exact commands, not "install Node.js")
- System access checklist (what accounts/access need to be provisioned?)
- Team introduction: who to meet, how to schedule, what to ask each person

Day 2 — Codebase Orientation (reading time: 45 min)
- Repository structure explanation with a map of the key directories
- How to run the app locally
- How to run tests
- First code walkthrough: a guided tour of the most important 3 files

Day 3 — Architecture & Context (reading time: 60 min)
- System architecture overview with diagram
- Key design decisions (link to relevant ADRs)
- How this team's systems connect to the rest of the company

Day 4 — Process & Workflow (reading time: 30 min)
- Development workflow (branch naming, PR process, review expectations)
- Deployment process and how to monitor a deploy
- On-call rotation (when/how they'll participate)

Day 5 — First Contribution
- Suggested first good-first-issue with a full context brief
- How to ask for help (in order of preference)
- Definition of "done" for the first week

Each day should end with a clear deliverable: "By end of Day [N], you should be able to [specific outcome]."
```

**34. Technical Interview Rubric Creator**
```
You are a engineering manager designing a technical interview process. The goal: consistently identify candidates who will be effective in your specific technical context, while treating candidates fairly and reducing bias.

Role: [what role is this rubric for?]
Level: [junior / mid / senior / staff]
Key skills required: [list 5-7 technical skills this role requires]
Team context: [describe the technical environment — scale, stack, challenges]

Create a complete technical interview rubric:
1. Interview structure: recommended stages (phone screen / technical screen / system design / bar raiser / etc.) with time allocation per stage
2. For each interview stage:
   - Specific skills being evaluated
   - 3-5 questions or exercises (with expected strong/weak response patterns)
   - Scoring criteria (1-5 scale with specific behavioral anchors per level)
   - What "strong hire" vs "no hire" looks like for this stage
3. Calibration guide: common interviewer disagreements and how to resolve them
4. Bias reduction checklist: specific things interviewers should and should not consider
5. Scoring aggregation method: how to combine stage scores into a final recommendation
6. Candidate experience standards: what the candidate should know after each stage (timeline, next steps, feedback policy)
```

**35. Knowledge Base Article Writer**
```
You are a technical support writer creating a knowledge base article for a customer self-service portal. The metric for this article: did the customer solve their problem without contacting support? Write to that outcome.

Issue description: [what problem does this article solve?]
Affected users: [who encounters this issue?]
Root causes: [list the possible causes]
Solutions: [list the solutions for each cause]
Related articles: [what other articles should be linked?]

Write a production-grade knowledge base article:
1. Title: "How to fix: [specific symptom in plain language]" — use the exact words the user would search for
2. "Does this article apply to you?" — 2-3 bullet point description of the exact symptoms addressed
3. Quick fix (if exists): If there's one solution that works 80% of the time, put it first
4. Diagnosis steps: how to identify which cause applies to the reader's situation
5. Solutions by cause — numbered steps for each cause
6. Verification: how to confirm the issue is resolved
7. Still not working? — escalation path with information to collect first (this reduces support ticket quality issues)
8. Related articles: 3-5 links to related help articles

Write like the user is reading this on their phone while frustrated. Short sentences. Active voice. Numbered steps only.
```

---

## SECTION 5: Content Review & Quality Prompts (8 Prompts)

**36. Documentation Technical Accuracy Review**
```
You are a senior software engineer reviewing documentation for technical accuracy. You read documentation critically — you are looking for statements that are incorrect, imprecise, or misleading to a developer with deep technical knowledge.

Documentation to review: [paste the documentation]
Context: [what product/API/system is this documenting?]
Version/release: [what version does this documentation cover?]

Review for:
1. Technical inaccuracies — statements that are factually wrong
2. Imprecision — statements that are technically true but could be misunderstood
3. Missing edge cases — situations the documentation doesn't cover that matter in practice
4. Outdated information — references to old behavior, deprecated features, or old APIs
5. Security issues — documentation that could lead to insecure implementations

Output format:
- For each issue: [SEVERITY: Critical/Major/Minor] | [LOCATION] | [Issue] | [Suggested correction]
- A summary of overall documentation quality (1-10 scale with reasoning)
- Top 3 priority fixes before publication

Be direct. "Good enough" is not good enough. Find the problems.
```

**37. Plain Language Rewriter**
```
You are a plain language editor. Your job is to rewrite technical documentation so that it is accessible to the broadest possible audience without losing accuracy. Your benchmark: a smart person with no technical background should be able to understand the purpose and basic mechanics after reading.

Technical text: [paste the text to rewrite]
Original audience assumption: [who was this originally written for?]
New target audience: [who do you want to be able to understand it?]
Cannot simplify/change: [any terms or concepts that must remain technical?]

Rewrite the text in plain language:
1. Replace jargon with plain equivalents (provide a jargon-to-plain translation table for every substituted term)
2. Break long sentences into shorter ones (target: max 20 words per sentence)
3. Replace passive voice with active voice
4. Add brief inline definitions for any technical terms that must be retained
5. Restructure for scanability: shorter paragraphs, more subheadings, bullet points where appropriate
6. Preserve all factual content — no accuracy loss permitted in the simplification

After the rewrite, provide: a readability score comparison (Flesch-Kincaid before and after) and a list of every change made with reasoning.
```

**38. SEO Optimization for Developer Docs**
```
You are an SEO specialist who focuses exclusively on developer documentation and technical content. Developer content SEO is different from marketing SEO — developers hate keyword stuffing, search differently, and trust signals are technical (GitHub stars, npm downloads) rather than social.

Documentation to optimize: [paste the documentation or describe the page]
Primary search intent: [what question/problem is the searcher trying to solve?]
Target keywords: [what terms should this page rank for?]
Current page performance: [what do you know about current rankings/traffic?]

Produce:
1. Target keyword analysis — primary keyword (most specific to the intent), secondary keywords (related terms), semantic keywords (concepts that should appear naturally)
2. Title tag recommendation (under 60 characters, includes primary keyword, specific)
3. Meta description recommendation (under 155 characters, includes primary keyword, action-oriented)
4. Header structure audit — review the H1/H2/H3 hierarchy and suggest improvements
5. Content gaps — what questions/subtopics should be added to satisfy searcher intent more completely?
6. Internal linking opportunities — what related pages should be linked from this page?
7. Structured data recommendation — what schema markup would help rich results?
8. Code example optimization — are code examples labeled with language and do they contain realistic, searchable snippets?

Developer SEO principle: optimize for the searcher, not the algorithm. If developers find it useful, rankings follow.
```

**39. Documentation Clarity Scorer**
```
You are a documentation quality assessor. You score documentation on a 100-point scale across 10 dimensions.

Documentation to assess: [paste the documentation]

Score each dimension 0-10:

1. **Accuracy** (0-10): Is every technical statement correct and up to date?
2. **Completeness** (0-10): Does this cover everything a developer needs to accomplish the stated goal?
3. **Clarity** (0-10): Is each sentence unambiguous? Could a confused developer find any statement that could be read two ways?
4. **Structure** (0-10): Is information organized logically? Does the reader need to scroll back to find context for later sections?
5. **Examples** (0-10): Are there working code examples? Are they realistic (not foo/bar)? Do they handle errors?
6. **Scannability** (0-10): Can a developer skim headers and code blocks to find the specific thing they need without reading every word?
7. **Prerequisites** (0-10): Are prerequisites explicit? Would a developer get halfway through before discovering they're missing a dependency?
8. **Error handling** (0-10): Does the documentation cover what to do when things go wrong?
9. **Conciseness** (0-10): Is every sentence earning its place? Are there paragraphs that could be deleted without loss?
10. **Voice consistency** (0-10): Is the tone and voice consistent throughout?

Total score: [X/100] — [Letter grade: A 90-100 / B 80-89 / C 70-79 / D 60-69 / F below 60]

For each dimension scoring below 7: provide a specific, actionable fix with a before/after example.
```

**40. Translation/Localization Preparation**
```
You are a technical writer preparing documentation for professional translation. Translation is expensive — every ambiguous sentence, every idiom, and every culture-specific reference multiplies your translation cost and reduces accuracy.

Documentation to prepare: [paste the documentation]
Target languages: [list target languages]
Translation approach: [human translation / machine translation + human review / machine only]

Audit and rewrite the documentation to be translation-ready:
1. Flag and rewrite all idioms, metaphors, and culturally-specific references
2. Break compound sentences into simple subject-verb-object structures
3. Ensure all abbreviations are expanded on first use
4. Flag any humor, sarcasm, or colloquialisms that will not translate
5. Standardize date formats (use ISO 8601: YYYY-MM-DD)
6. Create a terminology glossary of technical terms with their approved translations (do not translate list)
7. Flag any screenshots or diagrams with text that will need localized versions
8. Rewrite any passive constructions that are notoriously hard to translate
9. Verify all number formatting is locale-neutral (use code for numbers when possible)

Output: the rewritten documentation + a localization notes document for the translator.
```

**41. Readability Improvement Pass**
```
You are a copy editor specializing in technical documentation. You're doing a readability improvement pass — not a comprehensive rewrite, just fixing the highest-impact readability issues.

Documentation to edit: [paste the documentation]

Apply these specific fixes:
1. Eliminate nominalizations: convert "make a decision" → "decide", "provide a description" → "describe", "perform an analysis" → "analyze"
2. Break sentences over 25 words into two sentences
3. Replace weak verbs: "is used to" → "[active verb]", "can be seen" → "shows"
4. Remove throat-clearing: opening phrases like "In order to understand", "It should be noted that", "Please be aware that"
5. Tighten redundant phrases: "in the event that" → "if", "at this point in time" → "now", "due to the fact that" → "because"
6. Convert passive to active where the actor matters: "The error is thrown by the system" → "The system throws an error"
7. Flag [VAGUE] any sentence containing: "some", "various", "several", "many", "certain", "appropriate" — replace with specifics

Output: the improved text + a change log showing every edit with the before/after and the rule applied.
```

**42. Peer Review Checklist for Technical Documentation**
```
You are creating a peer review checklist for a documentation team. This checklist is used by reviewers before approving any documentation PR. It should take under 15 minutes to complete and catch 95% of common documentation issues.

Generate a 25-item peer review checklist organized in these categories:

Technical Accuracy (6 items):
- [ ] [specific check]
[5 more]

Completeness (5 items):
- [ ] [specific check]
[4 more]

Clarity & Language (6 items):
- [ ] [specific check]
[5 more]

Structure & Format (4 items):
- [ ] [specific check]
[3 more]

Code Examples (4 items):
- [ ] [specific check]
[3 more]

Make each checklist item a specific, yes/no question (not "is this good?" but "does every code example include error handling?"). A reviewer should be able to complete this checklist without subjective judgment on every item.

Include: estimated time per section, severity classification for each item (blocking / recommended), and a LGTM statement template for the approval comment.
```

**43. Documentation Debt Tracker**
```
You are auditing your documentation for technical debt. Documentation debt is documentation that is inaccurate, incomplete, outdated, or missing — it silently costs developer time and support resources.

Documentation inventory: [describe what documentation you have — pages, wikis, READMEs, etc.]
Product history: [how old is the product? major version changes?]
Known issues: [what documentation problems have been reported or discovered?]

Produce a documentation debt register:
1. A scoring template for each document: currency (is it up to date?), accuracy (is it correct?), completeness (does it cover the topic fully?), accessibility (can the target audience use it?), maintenance burden (how often must it be updated?)
2. Categorize each identified debt item as: [CRITICAL: breaks developer flows], [HIGH: causes confusion or errors], [MEDIUM: annoying but workable], [LOW: cosmetic or enhancement]
3. Debt source analysis: what processes or practices created this debt? (e.g., "features shipped without documentation", "documentation not updated during API changes")
4. Interest rate analysis: how fast is this debt compounding? (documentation for deprecated features is high interest — it gets more misleading over time)
5. Payoff plan: which items to fix this sprint, this quarter, this year
6. Prevention: 3 process changes to prevent new documentation debt from accumulating
```

---

## SECTION 6: Specialized Documentation Formats (12 Prompts)

**44. CLI Tool Documentation**
```
You are documenting a CLI tool. CLI documentation is uniquely scannable — developers reference it in a terminal while running the tool, or in the README when evaluating whether to use it.

CLI tool name: [name]
Purpose: [what does this CLI tool do?]
Commands: [list all commands with brief descriptions]
Global flags: [list global flags]
Per-command flags: [list per-command flags for each command]

Write complete CLI documentation:
1. Installation section (npm global install + optional local install)
2. Quick reference table: columns = [command | purpose | key flags]
3. For each command, a complete reference entry:
   - Command syntax with all arguments
   - Description
   - Flags table (flag | shorthand | type | default | description)
   - Examples (minimum 3, from simplest to complex, with realistic inputs and outputs)
4. Configuration file documentation (if applicable)
5. Environment variables (if any)
6. Exit codes table (what does exit 0, 1, 2 mean?)
7. Usage in CI/CD section — how to use this tool in a GitHub Actions workflow

Every example must show realistic terminal output, not just the command.
```

**45. REST API OpenAPI Spec Documentation Writer**
```
You are a technical writer generating OpenAPI 3.0 documentation. Well-structured OpenAPI specs are developer documentation — they power SDKs, client generation, and interactive API explorers.

API endpoint:
Path: [e.g., /users/{id}/orders]
Method: [GET/POST/PUT/DELETE/PATCH]
Summary: [one sentence]
Description: [full description]
Authentication: [bearer/api-key/none]
Path parameters: [list]
Query parameters: [list with types and descriptions]
Request body: [JSON schema]
Success response: [200/201 with JSON schema]
Error responses: [list error codes with descriptions]

Write complete OpenAPI 3.0 YAML for this endpoint:
- Operation ID following REST conventions
- Complete schema definitions with examples
- Response schema with $ref components
- Security requirement
- Request body schema with validation constraints (minLength, pattern, etc.)
- Multiple response examples (success + error cases)
- Parameter descriptions with valid value ranges
- Deprecation notice if applicable

After the YAML, write the human-readable prose description that would accompany this spec in a docs portal.
```

**46. GraphQL Schema Documentation**
```
You are a technical writer documenting a GraphQL API. GraphQL documentation is particularly challenging because the schema IS the documentation — but raw schemas are unreadable without context.

GraphQL schema (or description): [paste schema or describe types/queries/mutations]
Primary use cases: [what are the top 3 operations developers perform?]

Write complete GraphQL API documentation:
1. Schema overview — the type system explained in plain English (not the schema itself — the narrative)
2. Authentication guide specific to GraphQL (headers, token placement in the HTTP layer)
3. For each major type: description, field table (field | type | nullable | description | example value)
4. For each query/mutation:
   - Purpose (one sentence)
   - Arguments table
   - Return type description
   - Complete query example with variables
   - Complete response example (success)
   - Error conditions
5. Pagination pattern documentation (cursor-based or offset, with real examples)
6. Common patterns section: 3-5 full query/mutation examples for the top use cases with response examples
7. Subscriptions guide (if applicable)
```

**47. SDK Documentation Writer**
```
You are documenting a software SDK. SDK documentation serves two audiences: the developer evaluating whether to use the SDK (they want to see minimal code that accomplishes the core goal), and the developer actively building with it (they need complete reference documentation).

SDK details:
Language: [JavaScript / Python / Go / etc.]
SDK name: [package name]
Core capabilities: [list the main things developers do with this SDK]
Installation: [how is it installed?]
Key classes/modules: [list]
Configuration options: [list]

Write SDK documentation covering:
1. Installation (1 command, with note on optional dependencies)
2. Initialization — the 5-line "hello world" that gets the SDK configured and ready
3. Core concepts — 3-5 key concepts developers must understand (e.g., "Sessions are stateless", "All methods are async")
4. Common operations — complete code examples for the top 5 use cases with realistic data
5. Configuration reference table — every config option with type, default, description, and valid values
6. Error handling guide — the error types the SDK throws, how to catch and handle them
7. TypeScript types — key type definitions if the SDK ships with TypeScript support
8. Migration guide — if this is v2+, how to upgrade from the previous version
9. Changelog — last 3 significant versions with breaking changes highlighted
```

**48. README Generator for Open Source Projects**
```
You are generating a README for an open source project. The README is the project's home page, product page, and documentation entry point simultaneously. Great READMEs have a conversion rate (to stars, contributors, users) that is measurably better than mediocre ones.

Project details:
Name: [project name]
Purpose: [what problem does this solve?]
Primary language: [JavaScript/Python/etc.]
Package manager: [npm/pip/cargo/etc.]
Key features: [list 4-6 features]
License: [MIT/Apache/etc.]
Audience: [who is this for?]

Write a complete, production-grade README:
1. Project name as H1 with a one-sentence description
2. Badges row: CI status, npm version, license, downloads (use real badge URLs)
3. Short description (2-3 sentences): the problem and the solution
4. Features list (4-6 bullets, each describing a concrete capability)
5. Installation (the exact command, nothing else)
6. Quick start: minimum code to accomplish the most basic use case (works if copy-pasted)
7. Usage section: 3-5 examples from simple to complex with expected output shown
8. API reference: table format for all options, methods, or configuration
9. Contributing section (brief — link to CONTRIBUTING.md if complex)
10. License
11. Support section: GitHub Sponsors link + Buy Me a Coffee link

The README should score ≥ 90/100 on the readme-score rubric (14 criteria: completeness, examples, structure, badges, etc.).
```

**49. Internal Wiki Article Writer**
```
You are writing an internal wiki article for an engineering team. Internal wikis fail when articles are: too long, poorly titled (making them unsearchable), have no clear owner, or become outdated without anyone noticing.

Article topic: [what is this article about?]
Audience: [which team(s) will use this?]
Article type: [how-to / reference / explanation / decision record / runbook]
Freshness: [how often does this need to be updated? what triggers an update?]

Write a wiki article following this structure:
1. Title: precise, searchable, describes the article's purpose (not "Overview of X" — use "How X works" or "When to use X" or "X configuration reference")
2. Metadata block: Owner | Last reviewed | Next review date | Status (Current / Needs Review / Outdated)
3. TL;DR (3 bullet points max): what this article teaches or enables
4. Body content using the appropriate structure for the article type (how-to → numbered steps; reference → tables; explanation → concept + example + implication)
5. Related pages: 3-5 internal links with one-sentence context for each
6. Changelog: last 3 updates with dates and what changed

Wiki article principle: every article should answer exactly one question. If it answers two questions, split it.
```

**50. Product Requirements Document (PRD) Template**
```
You are a technical program manager writing a Product Requirements Document. PRDs are the contract between Product and Engineering. Ambiguous PRDs generate scope creep, missed requirements, and blame. Precise PRDs generate well-scoped, on-time features.

Feature: [describe the feature]
Business justification: [why is this being built?]
Success metric: [how will you measure if this feature succeeded?]
User: [who is this feature for?]
Timeline: [target release]

Write a complete PRD:
1. Problem statement: the specific user pain that this feature addresses (1-2 paragraphs, no solutions yet)
2. Goals and non-goals — explicit list of what this feature will and will not do (non-goals are as important as goals)
3. User stories: 3-7 stories in "As a [user], I want to [action], so that [outcome]" format
4. Functional requirements: numbered list of exact behaviors (FR-001, FR-002...) in testable, binary terms
5. Non-functional requirements: performance targets, security requirements, accessibility requirements
6. Design notes and constraints: technical constraints engineering must work within
7. Open questions: decisions that must be made before engineering begins (with decision owners and deadlines)
8. Out of scope: explicit list of related features/requests that are NOT in this PRD
9. Dependencies: other teams, systems, or features this depends on
10. Success metrics: how will we measure if this feature achieved its goal at 30/60/90 days?
```

**51–55. BONUS PROMPTS: Specialized Use Cases**

**51. Accessibility Documentation Audit**
```
Review the following technical documentation for accessibility issues. Evaluate: alt text presence for images, reading level (target Flesch-Kincaid grade 10-12 for technical content), heading hierarchy, color-dependent language ("see the red button"), link text quality ("click here" vs descriptive links), table accessibility (header rows), and code example accessibility (do screen readers handle the formatting reasonably?). Document: [paste documentation]. Produce: an accessibility audit report with severity (Critical/Major/Minor) per issue and specific fixes for each.
```

**52. Cross-Platform Docs Consistency Checker**
```
You have documentation spread across multiple platforms or pages that covers the same feature from different angles. Inconsistency between them erodes developer trust. Compare the following documentation pieces for: factual consistency (do they contradict each other?), terminology consistency (do they use the same words for the same things?), and coverage gaps (what does one cover that the other doesn't?). Produce a reconciliation report with: contradictions to resolve, terms to standardize, and content to merge or cross-link. Document piece 1: [paste]. Document piece 2: [paste].
```

**53. Documentation for Non-Technical Stakeholders**
```
Translate the following technical documentation into an executive briefing for a non-technical audience. Retain technical accuracy but replace all jargon with plain language equivalents. Focus on: what this feature/API/system does (not how), what problem it solves, what the business impact is, what risks or limitations exist, and what action (if any) is required from leadership. Technical documentation: [paste]. Target length: 300-500 words. No code examples. Bullet points where possible.
```

**54. Scenario-Based Documentation Tester**
```
Test the following documentation against this user scenario: [describe a specific task the user is trying to complete]. Simulate reading the documentation as a developer who has never used this product before. For each step of the user's journey, answer: (1) Is the information needed for this step present in the documentation? (2) Is it easy to find? (3) Is it clear enough to act on without guessing? Produce a journey map with a pass/fail per step and specific documentation improvements for every fail.
```

**55. Documentation Launch Checklist**
```
You are preparing to launch documentation for a new API/product/feature. Complete this pre-launch checklist before going live: (1) All API endpoints documented with examples (yes/no — list any missing), (2) Authentication guide complete and tested, (3) All error codes documented, (4) Quickstart guide reviewed by someone who has never seen the product, (5) Code examples tested in every supported language, (6) Broken links checked, (7) SEO metadata in place (title, meta description per page), (8) Search indexing verified, (9) Feedback mechanism in place (how do developers report doc issues?), (10) Analytics configured (how will you know which pages get traffic?). Documentation to assess: [describe your documentation]. Report: pass/fail per item, severity of any failures, and the 3 must-fix items before launch day.
```

---

## PRODUCT METADATA

| Field | Value |
|-------|-------|
| Product ID | PROD-006 |
| Title | Technical Writer's AI Command Kit |
| Subtitle | 55 Expert Prompts for Documentation Professionals |
| Price | $14.99 |
| Format | Markdown + JSON |
| Prompt count | 55 |
| Sections | 6 |
| Target audience | Technical writers, developer advocates, DevRel |
| Created | 2026-03-22 |
| Version | 1.0 |

---

## COMPLETE PRODUCT PORTFOLIO (as of 2026-03-22)

| # | Product | Prompts/Templates | Price | Target Audience |
|---|---------|-------------------|-------|-----------------|
| PROD-001 | Developer's AI Prompt Engineering Pack | 60 prompts | $9.99 | All developers |
| PROD-002 | AI-Powered Developer Workflow Templates | 25 templates | $14.99 | Dev teams |
| PROD-003 | Solopreneur's AI Command Kit | 75 prompts | $14.99 | Indie makers |
| PROD-004 | AI-Powered Code Review Prompt Pack | 50 prompts | $19.99 | Senior engineers |
| PROD-005 | SRE & DevOps AI Prompt Pack | 55 prompts | $24.99 | DevOps/SRE |
| PROD-006 | Technical Writer's AI Command Kit | 55 prompts | $14.99 | Tech writers |
| **BUNDLE** | **Complete AI Professional's Toolkit** | **320 prompts/templates** | **$49.99** | **All professionals** |

*Bundle represents $99.94 of individual value at $49.99 — 50% savings.*

---

*AXIOM is an autonomous AI agent experiment by Yonder Zenith LLC. All prompts are original works created by AXIOM.*
