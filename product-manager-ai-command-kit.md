# Product Manager's AI Command Kit
## 60 Expert Prompts for Product Professionals

**Product ID:** PROD-007
**Price:** $19.99
**Format:** Markdown + JSON
**Category:** Product Management & Strategy
**Target Audience:** Product managers, product owners, heads of product, associate PMs, product leads at startups and growth-stage companies

---

## Why This Pack Exists

Product management is a role with no shortage of deliverables and no shortage of blank pages.

A single week for a PM might include: writing a PRD, running user interviews, updating the roadmap, presenting to executives, responding to stakeholder pushback, grooming the backlog, designing an A/B test, and drafting the launch plan. Each of those tasks requires a different mode of thinking. Each blank document is a tax on your time and energy.

These 60 prompts are built for working product managers who want to think faster, communicate more clearly, and produce better artifacts — without sacrificing the judgment that makes great PMs irreplaceable.

Every prompt includes role-priming, structured inputs, and explicit output requirements. They're not generic. They're built for the real situations PMs face — the 9 PM PRD, the exec who wants a "quick summary," the stakeholder who thinks their pet feature is the roadmap.

---

## SECTION 1: Product Requirements Documents (PRDs) — 10 Prompts

**1. Full PRD Generator**
```
You are a senior product manager at a Series B technology company known for clear, decision-enabling documentation. You write PRDs that engineers actually want to read and executives can review in 5 minutes.

Write a complete PRD for the following feature:

Feature name: [name]
Problem being solved: [describe the user/business problem]
Target users: [who specifically will use this?]
Business context: [why does the company care about this now?]
Known constraints: [technical, legal, timeline, budget]
What success looks like: [your early hypothesis on metrics]

Produce a complete PRD with:
1. Executive Summary (3 sentences: problem, solution, expected outcome)
2. Background & Problem Statement (user pain, business pain, evidence you have)
3. Goals and Success Metrics (primary metric, secondary metrics, guardrail metrics)
4. User Stories — minimum 5, in the format: "As a [user type], I want to [action] so that [benefit]"
5. Functional Requirements — numbered list, each testable
6. Non-Goals — explicit list of what this feature will NOT do
7. Dependencies — technical, product, and organizational
8. Open Questions — unresolved decisions that need input
9. Timeline — phases if applicable

Be specific. Replace [placeholders] with what has been provided. If information is missing, flag it as an open question rather than making it up.
```

**2. User Story Generator with Acceptance Criteria**
```
You are a product owner with deep experience in behavior-driven development (BDD). You write user stories that give engineers exactly what they need to build the right thing — no ambiguity, no assumption, no re-work loops.

Generate user stories with full acceptance criteria for:

Feature: [feature name and brief description]
User types involved: [list all user types who will interact with this]
Core workflow: [describe the main flow in plain English]
Edge cases you know about: [any known edge cases]

For each user story, produce:
1. Story headline: "As a [user], I want to [action] so that [benefit]"
2. Acceptance criteria (Given/When/Then format, minimum 3 per story)
3. Definition of Done checklist (5 items: unit tests written, design reviewed, etc.)
4. Story points estimate (1/2/3/5/8/13) with one-line rationale

Generate minimum 6 user stories covering: the happy path, error states, and at least one edge case.
```

**3. PRD Gap Analysis & Review**
```
You are a staff-level product manager reviewing a PRD before it goes to engineering. You have seen dozens of PRDs fail in execution because of gaps in the document. Your job is to find every gap before the engineers start building.

Review the following PRD section and identify:

[PASTE PRD CONTENT HERE]

Produce a structured review covering:
1. Missing Requirements — things that will clearly be asked about during development but aren't answered
2. Ambiguous Language — phrases that could be interpreted multiple ways by an engineer
3. Missing Edge Cases — user flows or error states not covered
4. Metric Gaps — success metrics that are too vague to actually measure
5. Dependency Risks — dependencies mentioned without owners or timelines
6. Scope Creep Risk — anything in the PRD that sounds like it belongs in a future phase
7. Questions to Ask Before Engineering Kickoff — your top 5, ranked by blocking risk

Format as a numbered checklist the author can work through before engineering kickoff.
```

**4. Problem Statement Sharpener**
```
You are a product strategist who specializes in problem definition. You believe that most product failures start with a poorly scoped problem statement — one that confuses symptoms with causes, or solutions with problems.

Sharpen the following problem statement:

Current problem statement: [paste current statement]
Evidence I have: [data points, user quotes, support tickets, NPS signals]
Who is most affected: [user segment(s)]
Current workarounds users use: [how are they solving this today?]

Produce:
1. The sharpened problem statement (2-3 sentences, no solution language)
2. Why the original statement was insufficient (be direct)
3. The jobs-to-be-done framing: "When [situation], users want to [motivation], so they can [expected outcome]"
4. The falsifiable hypothesis: "We believe that [users] need [change] in order to [outcome]. We'll know this is true when [measurable signal]."
5. Three ways to validate this problem before building anything
```

**5. Success Metrics Definition**
```
You are a PM at a data-driven company. Your head of product has a rule: every feature must have a primary metric, one secondary metric, and at least one guardrail metric — defined before engineering starts. No metrics defined, no green light to build.

Define the complete metric set for:

Feature: [feature name and one-line description]
Goal: [what you're trying to achieve — acquire users, reduce churn, increase usage, etc.]
User behavior this changes: [what will users do differently if this works?]

Produce:
1. Primary metric — one metric that, if it moves, you can declare success. Include: what it is, how it's measured, current baseline if known, target, and why this is the right primary.
2. Secondary metrics (2-3) — supporting signals that give confidence the primary is moving for the right reason
3. Guardrail metrics (2-3) — metrics you must NOT break (latency, error rates, churn, support volume, etc.)
4. Instrumentation requirements — what events need to be tracked that may not exist today
5. Metric review cadence — when should you check these, and what's the escalation threshold?
```

**6. Edge Cases & Out-of-Scope Generator**
```
You are a QA-minded product manager who has been burned by edge cases that weren't in the PRD. You think adversarially about your features — what breaks, who misuses it, what the system does when inputs are unexpected.

Generate the complete edge case and out-of-scope analysis for:

Feature: [description]
Core happy path: [describe the main success flow]
User types: [list all user types]
External dependencies: [APIs, third-party services, other internal systems]

Produce:
1. Edge Cases (minimum 10) — each with: scenario description, expected behavior, risk level (P0/P1/P2)
   Include: empty states, maximum input sizes, network failures, concurrent users, permission edge cases, error states
2. Out of Scope — explicit list (minimum 8 items) of things this feature will NOT handle, with one-line rationale for each
3. Error Message Requirements — for each failure mode, what message does the user see?
4. Graceful Degradation — if a dependency fails, what is the fallback behavior?
```

**7. Business-to-Engineering Requirements Translator**
```
You are a technical product manager with a software engineering background. You bridge business stakeholders who speak in outcomes and engineers who need precise specifications. Your translations prevent the most expensive kind of re-work: building the right product the wrong way.

Translate the following business requirement into engineering requirements:

Business requirement: [paste the business/stakeholder language requirement]
Technical context: [what system, stack, or constraints are relevant]
Performance expectations: [response time, scale, uptime if known]

Produce:
1. Technical requirements (numbered, each independently testable)
2. API contract sketch — inputs, outputs, error codes for any endpoints implied
3. Data model changes — new fields, tables, or relationships required
4. Performance requirements — specific numbers (e.g., "< 200ms p95 response time")
5. Security and privacy requirements (data classification, access control, audit logging)
6. Integration points — what other systems does this touch and how?
7. Rollout strategy recommendation — feature flag, gradual rollout, hard cutover?
```

**8. PRD Executive Summary Generator**
```
You are a VP of Product writing the executive summary section of a PRD that the CEO and CFO will read. They will spend exactly 90 seconds on this document. If they don't understand the value in 90 seconds, the feature doesn't get prioritized.

Write the executive summary for:

Feature: [name]
Full context: [paste the full PRD or key details]
Business goal this supports: [OKR or company goal]
Estimated engineering cost: [team-weeks or rough estimate]
Expected impact: [your best hypothesis on the outcome]

Produce an executive summary of exactly 3 paragraphs:
1. The problem and why it matters to the business now (not someday)
2. The proposed solution and how it works in one sentence
3. What we expect to happen (metric + timeline), what it costs, and what we're risking if we don't do it

No jargon. No passive voice. Every sentence earns its place.
```

**9. Dependency & Risk Assessment**
```
You are a program manager with a track record of shipping features that were supposed to require 6 systems and somehow only required 4. You find hidden dependencies before they become launch blockers.

Conduct a full dependency and risk assessment for:

Feature: [name and description]
Teams involved: [engineering, design, data, legal, marketing, ops, etc.]
External services: [third-party APIs, vendors, infrastructure]
Timeline: [target launch date]
Current unknowns: [list anything you're not sure about]

Produce:
1. Dependency Map — table: Dependency | Owner Team | Blocking (Y/N) | Current Status | Risk Level
2. Critical Path Analysis — what is the single longest chain of dependencies, and what's the earliest possible ship date?
3. Risk Register — table: Risk | Probability (H/M/L) | Impact (H/M/L) | Mitigation | Owner
4. Launch Blockers — specific items that MUST be resolved before launch
5. Contingency Triggers — specific conditions under which you would delay, descope, or cancel
```

**10. MVP Scope Reducer**
```
You are a product manager who believes that the best version 1 is the one that ships. You have a talent for identifying the irreducible core of a feature — the minimum that delivers the promised value — and ruthlessly cutting everything else to phase 2.

Apply MVP reduction to the following feature scope:

Full feature as designed: [describe everything in the current plan]
Core value promise: [in one sentence, what does this feature do for the user?]
Launch deadline: [date]
Engineering estimate for full scope: [weeks]
Available engineering capacity: [weeks]

Produce:
1. The Irreducible Core — what is the minimum functionality that still delivers the core value promise?
2. Cut List — everything removed from V1, with one-line rationale for each cut
3. Phase 2 Backlog — what gets built next after V1 ships?
4. V1 Success Test — how do you know V1 is worth building V2?
5. The "No" Email — a draft message to stakeholders explaining why their requested features are phase 2, not V1
```

---

## SECTION 2: User Research & Discovery — 10 Prompts

**11. User Interview Question Generator**
```
You are a UX researcher with 10 years of experience running product discovery interviews. You understand that bad interview questions produce bad data — leading questions, hypothetical questions, and feature-fishing questions are your enemies.

Generate a complete user interview guide for:

Research question: [what you're trying to learn]
User type being interviewed: [describe the user segment]
Current hypothesis: [what you believe to be true — to be tested, not confirmed]
Session length: [30 / 45 / 60 minutes]

Produce:
1. Screener criteria — how to identify the right participants to recruit (5-7 criteria)
2. Warm-up questions (3-4) — build rapport, understand context
3. Core research questions (10-12) — open-ended, behavior-focused, past-tense framing ("Tell me about the last time you...")
4. Probing follow-ups (5-6) — to go deeper on specific answers
5. Feature reaction questions (if applicable) — how to show a prototype or concept without leading
6. Wrap-up questions (2-3)
7. What NOT to ask — 5 question types to avoid and why

Format as a ready-to-use interview script with time allocations.
```

**12. Interview Transcript Analyzer**
```
You are a qualitative researcher analyzing user interview transcripts to surface product insights. You are skilled at identifying signal vs noise, patterns across multiple interviews, and converting observations into product recommendations without over-indexing on any single response.

Analyze the following interview transcript(s):

[PASTE TRANSCRIPT(S) HERE]

Number of interviews: [N]

Produce:
1. Key Themes (top 5-7) — patterns that appeared across multiple interviews, with supporting quotes
2. Jobs-to-be-Done — the underlying motivations and desired outcomes users expressed
3. Pain Points — ranked by frequency and intensity
4. Surprise Findings — things you didn't expect to hear
5. Unmet Needs — gaps between what users want and what currently exists
6. Invalidated Assumptions — hypotheses that the data does not support
7. Recommended Next Steps — 3 specific product decisions you could make based on this research
8. Gaps — what questions remain unanswered that need a follow-up study?
```

**13. User Persona Builder**
```
You are a product strategist building research-based personas that will be used to align a cross-functional team on who they're building for. You believe personas should be grounded in actual behavior, not demographic stereotypes.

Build a complete user persona from the following research inputs:

Research inputs: [paste interview themes, survey data, or behavioral analytics]
Primary use case: [what does this user do with the product?]
Team using this persona: [engineering, design, sales, marketing, etc.]

Produce a persona with:
1. Name and role (representative, not a caricature)
2. Context — what does their day look like? What are they responsible for?
3. Goals — what are they trying to achieve (professional and personal)?
4. Frustrations — what gets in their way right now?
5. Behavior patterns — how they currently solve the problem (workarounds, tools, habits)
6. Decision factors — what makes them choose, recommend, or reject a product?
7. A direct quote (synthesized from research, sounds like a real person)
8. What this means for the product — 3 specific design/feature implications of this persona
```

**14. Jobs-to-be-Done Framework Application**
```
You are a product strategist applying the Jobs-to-be-Done framework to understand why customers buy and use products. You distinguish between functional jobs, emotional jobs, and social jobs — and you understand that people don't buy products, they hire them to do a job.

Apply JTBD analysis to:

Product/feature: [describe what you're analyzing]
User context: [describe the situation in which this product is used]
Research data available: [paste any quotes, observations, or data]

Produce:
1. The Primary Functional Job — the concrete task the user is trying to accomplish
2. The Emotional Job — how they want to feel (or not feel) while doing it
3. The Social Job — how they want to be perceived by others in relation to this job
4. The "Hired" statement: "When [situation], I want to [motivation], so I can [expected outcome]"
5. What the user fires to hire your product — what they stop using or doing
6. Competing job solvers — everything else that gets hired for this job (not just direct competitors)
7. Underserved aspects of the job — where current solutions fall short
8. Product implications — 3 ways this JTBD analysis should change what you build
```

**15. Feature Validation Survey Design**
```
You are a product researcher designing a customer survey to validate feature demand before committing engineering resources. You understand survey design — question ordering, response scale selection, avoiding leading language, and separating stated preference from revealed preference.

Design a validation survey for:

Feature hypothesis: [what you believe users want]
Target respondents: [who will take this survey?]
Key questions to answer: [what decisions will this data inform?]
Survey channel: [email, in-app, user research panel, etc.]
Target responses: [how many responses do you need?]

Produce:
1. Survey introduction text (sets context without leading)
2. Screening question (to filter to relevant respondents)
3. Core validation questions (5-8) — mix of rating scales, ranking, and open-ended
4. Willingness-to-pay question (if relevant) — using Van Westendorp or direct question
5. Follow-up open-ended question for qualitative signal
6. Analysis plan — how will you interpret the results? What thresholds indicate go/no-go?
7. What this survey won't tell you — important limitations to flag for stakeholders
```

**16. Competitive Feature Matrix**
```
You are a senior PM conducting competitive analysis to inform product positioning and roadmap decisions. You go beyond feature checklists — you evaluate how well each competitor executes each capability, and what that means for your product strategy.

Build a competitive feature matrix for:

Your product: [name and core value proposition]
Competitors to analyze: [list 3-5]
Feature areas to compare: [list 8-12 capabilities you care about]
Your strategic goal: [differentiate on X, match table stakes on Y, ignore Z]

Produce:
1. Feature Matrix Table — rows: features, columns: your product + each competitor. Ratings: ✓ (has it), ○ (partial/weak), ✗ (missing), ★ (best-in-class)
2. Competitive Narrative — for each competitor: 2-3 sentence summary of their positioning and what they do best
3. Your Strengths — features where you have meaningful advantage
4. Table Stakes — features you must have to be considered (regardless of differentiation)
5. Differentiation Opportunities — gaps where you could establish unique advantage
6. Kill Zones — areas where a competitor is so dominant that competing is a waste of resources
7. Roadmap Implications — 3 specific decisions this analysis should drive
```

**17. User Feedback Synthesizer**
```
You are a PM analyzing a large volume of unstructured user feedback — support tickets, NPS responses, app store reviews, user interviews, Slack messages, sales call notes. Your job is to find the signal in the noise and translate it into a prioritized product backlog.

Synthesize the following user feedback:

[PASTE FEEDBACK DATA HERE — tickets, reviews, quotes, survey responses]

Volume: [approximate number of feedback items]
Time period: [when was this collected?]
Source(s): [support tickets / app store / NPS survey / interviews / other]

Produce:
1. Top 5 Themes — ranked by frequency, with representative quotes for each
2. Sentiment Breakdown — positive / neutral / negative ratio and what's driving each
3. Feature Requests — ranked list with frequency count and sample quotes
4. Bug Reports — separated from feature requests, with severity assessment
5. Delight Signals — what are users explicitly happy about? (protect this)
6. Churn Signals — feedback that suggests users are about to leave or have left
7. Prioritized Action List — top 10 items to address, with rationale for ordering
8. What you'd need more data on before acting
```

**18. Pain Point Prioritizer**
```
You are a product manager running a prioritization session. You have a long list of user pain points and you need to rank them by impact so you can make the case for what to build next.

Prioritize the following pain points:

Pain points list: [paste your list of 10-20 pain points]
User segments affected: [list the user segments in your product]
Company strategic priorities this quarter: [list 2-3]

Score each pain point using:
1. Frequency — how often does this pain occur? (1-5)
2. Intensity — how much does it hurt when it happens? (1-5)
3. Addressability — how feasible is it to solve? (1-5)
4. Strategic alignment — does solving this advance a company priority? (1-5)

Produce:
- Scored table: Pain Point | Frequency | Intensity | Addressability | Strategic Fit | Total Score
- Top 5 pain points with one-paragraph rationale for each ranking
- Quick wins — pain points with high score + low engineering effort
- Long-term bets — high impact but complex to solve
- Explicitly out of scope — pain points you're recommending to not address, and why
```

**19. Customer Journey Map Creator**
```
You are a PM creating a customer journey map to align your cross-functional team on the full user experience — from first awareness to power user to churn. You believe that most product teams over-invest in the activation phase and under-invest in everything else.

Create a customer journey map for:

Product: [name and core function]
User type: [the persona being mapped]
Entry point: [how does this user first encounter the product?]
Core value moment: [when do they first experience the core value?]
Known pain points: [what friction points do you already know about?]

Produce a journey map with these stages: Awareness → Consideration → Activation → Adoption → Habit → Advocacy (or adapt stages to fit your product):

For each stage:
1. What the user is doing
2. What they're thinking
3. What they're feeling (emotional tone)
4. Touchpoints (where they interact with the product or brand)
5. Pain points at this stage
6. Opportunities — what could reduce friction or amplify delight here?

End with: Top 3 moments of truth — the make-or-break moments where the journey succeeds or fails.
```

**20. Research Insight to Feature Brief**
```
You are a PM translating qualitative research insights into a one-page feature brief that will get an engineer excited to build it. You know that research reports get skimmed — the feature brief is where insights become action.

Write a feature brief based on:

Research insight: [paste the key finding or quote from user research]
Supporting evidence: [other data points that support this insight]
User impact: [who is affected and how often?]
Proposed solution direction: [your early hypothesis — doesn't have to be final]

Produce a one-page feature brief:
1. Insight headline (one sentence that anyone in the company could understand)
2. The user problem (2-3 sentences)
3. Evidence base (bullet list of supporting data)
4. Proposed approach (2-3 sentences — what you're proposing to build, not a full PRD)
5. Why now (why this quarter, not next quarter?)
6. Rough scope estimate (S/M/L/XL)
7. Success definition (one primary metric)
8. Who needs to sign off before this goes to planning?
```

---

## SECTION 3: Roadmap & Prioritization — 10 Prompts

**21. RICE Score Analysis**
```
You are a product manager running a prioritization meeting. You use the RICE framework (Reach, Impact, Confidence, Effort) to make prioritization decisions transparent and defensible. You know that RICE is a tool for structuring judgment, not replacing it.

Score the following features using RICE:

Features to score: [list 5-10 feature ideas or projects]
Time horizon: [one quarter / half year]
User base size: [approximate — for Reach calculation]

For each feature, estimate:
- Reach: how many users will this affect per quarter? (number)
- Impact: how much will it move the primary metric per user? (0.25 / 0.5 / 1 / 2 / 3)
- Confidence: how confident are you in your estimates? (100% / 80% / 50%)
- Effort: how many person-months will this take?

RICE Score = (Reach × Impact × Confidence) / Effort

Produce:
1. RICE table with all scores
2. Ranked list by RICE score
3. Top 3 recommendations with one-paragraph rationale for each
4. What RICE doesn't capture (qualitative factors the team should still discuss)
5. Your recommended Q[X] roadmap given this analysis
```

**22. Now/Next/Later Roadmap Builder**
```
You are a head of product building a public-facing or team-facing roadmap in the Now/Next/Later format. You believe roadmaps should communicate direction, not dates — and that a good roadmap creates alignment without creating a contract.

Build a Now/Next/Later roadmap for:

Product area: [what part of the product does this cover?]
Team: [number of engineers, designers, PMs]
Current quarter focus: [what is the team focused on now?]
Pending backlog items: [paste your list of features, bugs, and initiatives]
Strategic priorities: [company OKRs or strategic themes]

Produce:
NOW (current sprint/quarter — in progress):
- List current work with one-line description and expected outcome

NEXT (next quarter — committed):
- List 3-5 initiatives with: name, one-line description, strategic rationale

LATER (beyond next quarter — directional):
- List 5-8 items grouped by theme, clearly labeled as directional (not committed)

Also produce:
- The narrative summary (2-3 paragraphs) that would accompany this roadmap in a company all-hands
- What's explicitly NOT on this roadmap and why
```

**23. Quarterly Roadmap Narrative**
```
You are a VP of Product presenting the Q[X] product roadmap to the executive team. You know that executives care about three things: will this move revenue/retention/engagement? Is the team focused on the right things? Are we on track?

Write the Q[X] roadmap presentation narrative for:

Roadmap items: [list planned Q[X] features/projects with brief descriptions]
Company OKRs this quarter: [list]
Last quarter retrospective: [what shipped, what slipped, what you learned]
Resources: [team size, capacity constraints]
Key risks: [what could go wrong?]

Produce:
1. Opening — the one-sentence statement of what this quarter is about
2. Last Quarter Review — what shipped, what the metrics showed (2 paragraphs)
3. Q[X] Theme — the unifying strategic idea connecting this quarter's work
4. Roadmap walkthrough — for each major initiative: what it is, why now, expected impact
5. What we're NOT doing this quarter — explicit prioritization decisions
6. Risk Summary — top 3 risks and mitigation plans
7. What you need from leadership — decisions, approvals, resources
8. Close — the outcome you're committing to by end of quarter
```

**24. Stakeholder Trade-Off Communicator**
```
You are a PM who has just made a difficult prioritization decision that will disappoint at least one stakeholder. You know that avoiding the conversation doesn't make the conflict disappear — it makes it worse. You write communications that are honest, respectful, and clear about the reasoning.

Write a trade-off communication for:

The decision: [what was decided?]
What was deprioritized: [what is not getting built or is being delayed?]
Who is affected: [which stakeholder or team is disappointed?]
The reason: [why was this decision made? be honest]
What comes next: [when will this be revisited, if ever?]

Produce:
1. Subject line (email or Slack message format)
2. Opening — acknowledge the impact directly, don't bury it
3. The decision and the reason — clear, direct, no apologizing for making a decision
4. What we're prioritizing instead and why
5. When this will be revisited (if applicable)
6. What you need from the recipient (alignment? input? just acknowledgment?)
7. Close — forward-looking, not defensive

Tone: direct and respectful. No corporate speak. No passive voice. No "at this time."
```

**25. Technical Debt vs. New Feature Brief**
```
You are a PM who has been asked by engineering to dedicate 20% of next quarter to technical debt reduction. Sales wants three new features by the same date. You need to write a brief that helps leadership make an informed decision.

Write the technical debt vs. new feature decision brief for:

Technical debt items: [list what engineering wants to address]
New feature requests: [list what sales/stakeholders are asking for]
Current system pain: [what is the technical debt actually causing? Incidents? Slowdowns? Churn?]
Engineering estimate for debt work: [team-weeks]
Engineering estimate for feature work: [team-weeks]
Available capacity: [total team-weeks next quarter]

Produce:
1. Executive Summary — the decision and its trade-offs in 3 sentences
2. The Cost of Ignoring Technical Debt — specific business impact (incidents, developer velocity, customer impact)
3. The Cost of Delaying Features — revenue at risk, competitive pressure, stakeholder commitments
4. Three Options:
   Option A: 100% new features (short-term gains, long-term cost)
   Option B: 100% technical debt (long-term investment, short-term pain)
   Option C: Balanced split — your recommended split with rationale
5. Recommendation — which option and why
6. Success Metrics — how you'll know if the recommendation was right
```

**26. Roadmap to OKR Alignment Check**
```
You are a PM doing a quarterly alignment check: does your current roadmap actually move your company OKRs? You've seen too many teams ship roadmaps full of things that don't connect to any measurable objective.

Run an alignment check for:

Company OKRs this quarter: [paste OKRs with Key Results]
Current roadmap items: [paste list of planned features/projects]

Produce:
1. Alignment Matrix — table: Roadmap Item | Primary OKR it serves | Key Result it moves | Confidence (H/M/L)
2. Orphaned Items — roadmap items that don't map to any OKR (these need justification or removal)
3. Uncovered OKRs — OKRs with no roadmap work supporting them (these are at risk)
4. Alignment Score — what % of roadmap items have clear OKR connection?
5. Recommendations — what to add, remove, or reframe to improve alignment
6. The one-paragraph roadmap rationale you'd write if forced to justify every item on this roadmap to the CEO
```

**27. Backlog Grooming Facilitation**
```
You are a product owner facilitating a backlog grooming session with the engineering team. You have 47 items in the backlog. You have 2 hours. Your goal: a clearly prioritized, well-described backlog that engineers can pull from for the next two sprints without needing to ask clarifying questions.

Facilitate this grooming session for:

Backlog items: [paste list of backlog items — titles or brief descriptions]
Sprint capacity: [team velocity in story points]
Next sprint goal: [what the next sprint is focused on]
Known dependencies: [anything blocked on other teams?]

Produce:
1. Triage Decision for each item: Sprint Ready / Needs Refinement / Deprioritize / Delete
2. Sprint 1 Recommendation — which items to pull into the next sprint (within capacity)
3. Sprint 2 Preview — what's queued for the following sprint
4. Items Needing More Detail — list with specific questions for each
5. Items to Delete — with brief rationale
6. The clarifying questions to ask for each "Needs Refinement" item (so the team leaves with assignments, not vague action items)
```

**28. Feature Kill Decision Framework**
```
You are a PM evaluating whether to kill a feature that has been live for 6 months but isn't performing. You believe killing features is often harder than building them — and equally important to product health. You approach kill decisions with data, not sentiment.

Evaluate this feature for discontinuation:

Feature name: [name]
Launch date: [date]
Original hypothesis: [what was supposed to happen?]
Current metrics: [usage data, revenue, engagement, support volume]
Engineering maintenance cost: [estimated ongoing maintenance burden]
Known users: [is anyone relying on this? who?]
Alternative: [is there another feature that covers the use case?]

Produce:
1. Performance Assessment — did the feature achieve its original hypothesis? (yes/partial/no)
2. Usage Data Interpretation — what does the data actually tell you?
3. The Keep Case — the strongest argument for keeping this feature
4. The Kill Case — the strongest argument for removing it
5. Recommendation — keep / sunset / redesign — with rationale
6. If Kill: Sunset plan — timeline, user communication, data migration if needed
7. If Keep: What would need to change in the next 90 days to justify continued maintenance?
```

**29. Impact vs. Effort Matrix Analysis**
```
You are a PM running a prioritization workshop. You have a whiteboard and a long list of potential projects. Your tool: the Impact vs. Effort (2×2) matrix. Your goal: in 30 minutes, align the team on what to pursue, what to schedule, what to quickwin, and what to ignore.

Build the Impact vs. Effort matrix for:

Projects/features to evaluate: [paste list of 10-20 items]
Definition of "Impact": [how are you measuring impact for this exercise? revenue / retention / NPS / engineering velocity / other]
Definition of "Effort": [engineering weeks / story points / team-months]
Team size and velocity: [context for calibrating effort scores]

Produce:
1. Scored table — each item with Impact (H/M/L) and Effort (H/M/L)
2. Quadrant assignments:
   - Quick Wins (High Impact, Low Effort) — do these now
   - Big Bets (High Impact, High Effort) — plan and resource properly
   - Fill-Ins (Low Impact, Low Effort) — do if capacity allows
   - Time Sinks (Low Impact, High Effort) — avoid or kill
3. Your top 5 prioritized recommendations
4. The hard conversation — items the team is emotionally attached to that the matrix says to deprioritize
5. What the matrix doesn't capture — qualitative factors to overlay on the quantitative ranking
```

**30. Roadmap Risk Assessment**
```
You are a risk-aware PM doing a pre-mortem on your quarterly roadmap. It is day 1 of the quarter and you are imagining it is day 90 and the roadmap failed. What happened?

Conduct a roadmap pre-mortem for:

Planned roadmap: [paste the planned roadmap for the quarter]
Team: [team composition, any new hires, key person dependencies]
External dependencies: [other teams, vendors, third-party APIs]
Known risks going in: [anything already flagged as risky]

Produce:
1. Pre-Mortem Narrative — write the story of how this quarter failed (be specific — name the items that slipped and why)
2. Risk Register — table: Risk | Probability | Impact | Early Warning Sign | Mitigation
3. Single Points of Failure — people or systems where one failure causes cascading failures
4. Dependency Timeline — ordered list of when each external dependency must deliver for the roadmap to stay on track
5. Contingency Plan — if you're 50% through the quarter and 40% behind: what do you cut first?
6. The Three Things Most Likely to Go Wrong — your honest assessment
7. Pre-quarter commitments to make — decisions, conversations, or agreements needed in week 1 to prevent these risks
```

---

## SECTION 4: Stakeholder Communication — 8 Prompts

**31. Weekly PM Update Email**
```
You are a PM writing your weekly team update. You believe that good updates are brief, honest, and forward-looking. They don't bury bad news. They don't waste the reader's time. They create shared understanding, not a paper trail.

Write the weekly PM update for:

Team: [product area / squad name]
This week's accomplishments: [list]
This week's blockers or setbacks: [list — be honest]
Metrics update: [any numbers worth sharing]
Next week focus: [top 3 priorities]
Decisions needed: [anything requiring input from leadership or other teams]

Produce a weekly update email that:
- Opens with the most important thing (not "this week we...")
- Uses bullet points, not paragraphs
- Calls out blockers explicitly with proposed resolution
- Ends with a clear ask if one exists
- Is under 300 words

Tone: Direct, confident, no corporate speak.
```

**32. Engineering Kickoff Brief**
```
You are a PM writing the kickoff brief for a new feature sprint. You believe that the kickoff brief is the most important document you write — it sets the context for every engineering decision made in the next 2-6 weeks. Ambiguity here multiplies into bugs, rework, and missed deadlines.

Write the engineering kickoff brief for:

Feature: [name]
Sprint dates: [start - end]
Engineering team: [names or roles]
PRD reference: [link or summary]
Success criteria: [exactly what "done" means — this becomes the acceptance test]
Known technical constraints: [anything engineering needs to know before starting]
Design assets: [link to Figma or describe if not designed yet]
Who to contact for questions: [PM, designer, data, legal if relevant]

Produce a kickoff brief with:
1. Context (2-3 sentences — why we're building this now)
2. Scope — what's in, what's explicitly out
3. Success criteria (specific, testable — these become QA acceptance criteria)
4. Technical notes — constraints, APIs, existing systems to integrate with
5. Design reference — key screens and states
6. Timeline and milestones
7. Open questions (unresolved decisions the engineer may hit — here's who to ask)
8. Launch criteria — what has to be true before this goes to production?
```

**33. Executive Status Update**
```
You are a PM giving a 5-minute executive status update. You know that executives are time-starved and pattern-matching for: are we on track, what's at risk, and what do they need to decide. They don't want a feature walkthrough. They want signal.

Write the executive status update for:

Product area: [name]
Timeframe: [Q[X] / this month / this sprint]
Status: [Green / Yellow / Red — with honest rationale]
Key metrics: [2-3 numbers that matter most]
Milestones: [what shipped, what's in progress, what's next]
Risks: [what could derail things?]
Decisions needed from leadership: [be specific — this is the most important part]

Produce a 5-minute verbal update script (can be read aloud or adapted to slides):
1. Status declaration: "We are [green/yellow/red] because..."
2. What shipped and what the metrics show
3. What's in flight and on track
4. One risk to flag (with mitigation)
5. One decision or resource request
6. Close: what you expect to report next time

No more than 400 words. Every sentence earns its place.
```

**34. Pushback Response Generator**
```
You are a PM who has just received pushback on a product decision. The pushback is either: (a) a stakeholder who disagrees with the prioritization, (b) an engineering lead who thinks the approach is wrong, or (c) an executive who wants something added to the roadmap without removing anything else.

Write a pushback response for:

Original decision: [what was decided?]
Pushback received: [paste the actual pushback message or describe it]
Your assessment: [is the pushback valid? partly valid? not valid?]
Your position: [are you changing the decision, partially adjusting, or holding firm?]

Produce a response that:
1. Opens by genuinely acknowledging the concern (not dismissing it)
2. States what you heard (demonstrates you understood the pushback)
3. Explains the reasoning behind the original decision (the "why" not the "what")
4. States clearly whether you're changing course and why (or why not)
5. Proposes a path forward that respects the relationship even if the decision stands
6. Ends with alignment — what do you both agree on going forward?

Tone: confident, not defensive. Respectful, not deferential. A decision-maker's voice.
```

**35. Feature Delay Announcement**
```
You are a PM communicating that a feature customers were expecting is going to be delayed. You know that how you communicate bad news matters as much as the news itself. You don't spin. You don't bury the lead. You give people what they need to know and what they can do about it.

Write the feature delay announcement for:

Feature: [name]
Original expected date: [date]
New expected date: [date, or "still TBD"]
Reason for delay: [be honest — what actually happened?]
Impact on users: [who is affected and how?]
Workaround available: [is there anything they can do in the meantime?]
Audience: [customers / internal team / sales team / all of the above]

Produce:
1. Subject line that doesn't bury the news
2. Lead with the fact (not context): "[Feature] will now launch [date/TBD]"
3. Why — honest, brief, no blame language
4. Impact — who is affected and how
5. What we're doing about it — specific actions, not "we're working on it"
6. Workaround if applicable
7. When to expect the next update
8. Close — brief, forward-looking

Tone: Honest. Accountable. Not defensive.
```

**36. Internal Launch Announcement**
```
You are a PM writing the internal launch announcement for a feature that just shipped. You want the whole company to understand what shipped, why it matters, and how to talk about it — whether they're in sales, support, or engineering.

Write the internal launch announcement for:

Feature: [name and one-line description]
Launch date: [date]
What it does: [clear, plain-language description]
Who benefits: [which users? which customer segments?]
Why it matters: [business impact, user pain it solves, metrics we expect to move]
How to try it: [link or description]
Support resources: [where can people go with questions?]
Who worked on it: [shoutout to the team]

Produce an internal announcement with:
1. Headline: [Feature] is live — [one-line value statement]
2. What it does (3-4 bullet points, plain language, no jargon)
3. Why we built it — user problem + business case (2 paragraphs)
4. Who it affects and how to find it
5. What to watch for — metrics we're tracking in the first 30 days
6. How to get help or give feedback
7. Team appreciation

Tone: Celebratory but informative. Engineers and executives both should feel like they got something useful from this.
```

**37. Cross-Functional Alignment Meeting Agenda**
```
You are a PM who has called a cross-functional alignment meeting. You know that meetings without agendas become status updates that could have been emails. You know that status updates without decisions are theater. You are designing a meeting that ends with alignment and clear owners — not "let's follow up on that."

Design the alignment meeting for:

Meeting goal: [what specific alignment or decision is needed?]
Attendees: [list roles — PM, Eng Lead, Design, Data, Legal, Marketing, etc.]
Duration: [45 / 60 / 90 minutes]
Context: [what's the background a new attendee needs to understand the meeting?]
Decisions to make: [list the specific decisions that need to be made in this meeting]
Pre-read materials: [what should attendees review beforehand?]

Produce:
1. Meeting purpose statement (1 sentence — not "to discuss X" but "to decide X and align on Y")
2. Pre-read list with time estimate for each
3. Agenda with time allocations:
   - Context setting (brief — attendees should have read the pre-read)
   - Discussion blocks (one per decision, with clear facilitator prompt)
   - Decision capture (explicit — what did we decide? who owns it? by when?)
   - Parking lot (issues raised that need a separate conversation)
4. Decision log template (to fill in during/after the meeting)
5. What success looks like at the end of this meeting
```

**38. "No" to a Feature Request**
```
You are a PM who has received a well-intentioned feature request from a colleague, customer, or stakeholder that you are not going to build — at least not now. You believe that saying no is one of the most important skills in product management, and that a well-crafted "no" is better for the relationship than a vague "maybe later."

Write a "no" response to:

Feature request: [describe the request]
Who requested it: [customer / sales team / executive / internal colleague]
Why you're declining: [honest reason — not on roadmap, low priority, wrong direction, etc.]
Is there any version of this you'd build? [yes/no/maybe in X scenario]
Is there an alternative that addresses the underlying need? [if yes, describe it]

Produce a response that:
1. Opens by acknowledging the request and showing you understood it (don't dismiss)
2. States clearly that you're not building this — no ambiguity
3. Explains the why (honest, brief, no corporate deflection)
4. Offers the alternative if one exists
5. Leaves the door open for the right time, if applicable — with specific conditions, not vague promises
6. Ends with something they can do (provide feedback, watch a related feature, etc.)

Tone: Respectful, clear, direct. No "unfortunately." No "at this time." Just honest product thinking.
```

---

## SECTION 5: Go-to-Market Planning — 10 Prompts

**39. GTM Strategy Outline**
```
You are a head of product-marketing writing the go-to-market strategy for a new product or major feature launch. You know that "build it and they will come" is not a strategy. GTM is the difference between a launch that moves metrics and one that gets announced and forgotten.

Write the GTM strategy for:

Product/feature: [name and one-line description]
Launch date: [target date]
Target customer: [ICP — who specifically are you trying to reach?]
Core value proposition: [why should they care?]
Key differentiator: [what makes this different from alternatives?]
Channels available: [email, in-app, PR, social, content, paid, sales, etc.]
Success metrics: [how will you measure GTM success?]
Team and resources: [who is involved in the launch?]

Produce a GTM strategy covering:
1. Launch objective (one sentence — what does success look like in 30 days?)
2. Target segments — ranked by priority for this launch
3. Messaging framework: Headline | Problem we solve | How we solve it | Proof | CTA
4. Channel plan — for each channel: what content, what timing, who owns it
5. Launch timeline — T-4 weeks to T+2 weeks with milestones
6. Enablement plan — what does sales/support/success need to know and have?
7. Risk mitigation — what could go wrong and how do you prevent it?
8. Metrics dashboard — what you're watching in the first 30 days
```

**40. Launch Checklist Generator**
```
You are a program manager running a product launch. You have launched 20 features. You know that every launch has the same categories of things that get missed — support isn't trained, the error messages aren't right, the analytics aren't firing, the email is scheduled for the wrong segment. You've turned your lessons into a checklist.

Generate a complete pre-launch checklist for:

Feature type: [UI feature / API change / new product / pricing change / other]
Launch scope: [percentage rollout / segment / full launch]
Teams involved: [engineering, design, data, marketing, sales, support, legal, etc.]
Known risk areas: [anything you're already worried about]

Produce a checklist organized by category:
- Engineering: code complete, tests passing, feature flags configured, rollback plan defined, monitoring alerts set
- Data & Analytics: instrumentation verified, dashboards built, baseline metrics captured
- Design: final design review complete, empty states exist, error states designed, mobile tested
- Content & Copy: all UI strings final, error messages human-readable, help docs written
- Marketing: announcement drafted, send list confirmed, timing approved
- Sales & Success: enablement doc delivered, demo script updated, FAQ written
- Support: training completed, escalation path defined, known issues documented
- Legal & Compliance: privacy review done, terms updated if needed, GDPR/CCPA check
- Executive: launch approved, metrics committed, stakeholder comms sent

For each item: owner role, completion status field, and notes field.
```

**41. Positioning Statement Builder**
```
You are a product marketer applying Geoffrey Moore's positioning statement framework — the discipline of forcing a product's value into a structure that exposes whether the proposition is actually clear. You believe that if you can't fill in the blanks, the product isn't positioned.

Build the positioning statement for:

Product: [name]
Target customer: [who specifically?]
The need or opportunity: [what problem do they have or goal they're pursuing?]
Product category: [what category does this compete in?]
Key benefit: [the single most important benefit you deliver]
Proof point: [what makes this credible? evidence, capability, differentiator]
Primary alternative: [who do you win against?]

Produce:
1. The complete positioning statement in Moore's format:
   "For [target customer] who [need], [product name] is a [category] that [key benefit]. Unlike [primary alternative], our product [key differentiator]."

2. Three alternative positioning statements (different angles — different emphasis on benefit, audience, or differentiator)

3. The elevator pitch (30 seconds, conversational, what you'd say at a conference)

4. The one-liner (10 words or fewer — the tagline candidate)

5. Positioning stress test — 5 questions to ask yourself to know if this positioning will hold up in market
```

**42. Beta User Recruitment Message**
```
You are a PM recruiting beta testers for a feature in development. You need people who fit the target user profile, are willing to use something unfinished, and will give honest feedback — not just positive validation. You're not looking for fans; you're looking for critical users.

Write the beta recruitment message for:

Feature being tested: [name and one-paragraph description]
Ideal beta user profile: [who exactly should be in this beta?]
What beta users will do: [what tasks, how often, for how long?]
What they get in return: [early access, input on the product, credit, compensation?]
How to apply: [link, email, form?]
Beta start date: [date]
Number of spots: [N]

Produce:
1. Subject line (email) or first sentence (in-app/Slack message)
2. The hook — why should they care? (one paragraph that earns the read)
3. What they're signing up for (be honest — it's unfinished, there will be bugs)
4. What we're asking of them (specific time commitment, specific feedback tasks)
5. What's in it for them (be specific — don't oversell)
6. How to apply / express interest
7. Timeline (application deadline, beta start, beta end)

Tone: Excited but honest. Not a marketing message. A direct ask from one professional to another.
```

**43. Post-Launch Retrospective Template**
```
You are a PM running a launch retrospective 30 days after a major feature went live. You believe launch retrospectives are the most underrated PM practice — they're where the team learns how to launch better. You run them blameless, structured, and specific.

Facilitate a launch retrospective for:

Feature launched: [name]
Launch date: [date]
Team that launched: [roles]
Original success metrics: [what you committed to]
Actual metrics 30 days out: [what actually happened]
Notable events: [any incidents, surprises, feedback spikes?]

Produce a retrospective structure:
1. By the numbers — dashboard: metric | target | actual | delta | status
2. What went well (specific — not "good teamwork")
3. What didn't go as planned (specific — not "communication could be better")
4. What surprised us (things we didn't anticipate)
5. Root causes of the gaps (5 Whys for the top miss)
6. Action items — table: Action | Owner | Due Date | Success Criteria
7. Process improvements for the next launch
8. What we'd do differently if we were launching this today

Format as a working document, not a slide deck.
```

**44. Press Release Framework**
```
You are a communications lead writing a press release using Amazon's "working backwards" approach. You write the press release before the product is built to ensure the value proposition is clear enough to announce before a line of code is written.

Write the press release for:

Product/feature: [name]
Launch date: [date or "today"]
Headline statement: [what's the news?]
Target audience: [who is this for?]
Problem solved: [what pain does this eliminate?]
How it works: [plain language — how does it deliver the benefit?]
Customer quote: [what would a happy customer say?]
Company quote: [what would your CPO or CEO say?]
Supporting data: [any stats, metrics, or evidence]
Call to action: [what should the reader do?]

Produce a complete press release:
1. Headline (compelling, specific, not vague)
2. Dateline and opening paragraph (who, what, where, when, why — lead with news)
3. Problem paragraph (context — why this matters now)
4. Solution paragraph (how the product works, in plain English)
5. Customer quote (sounds like a real person, not a testimonial ad)
6. Company quote (vision-level — what this means for the category)
7. Supporting details (pricing, availability, technical specs if relevant)
8. About [Company] boilerplate
9. Call to action and contact info
```

**45. Sales Enablement Brief**
```
You are a PM handing off a new feature to the sales team. You know that salespeople are busy, and if your enablement materials are too long or too abstract, they won't be used. You write the brief that actually gets read and used in calls.

Write the sales enablement brief for:

Feature: [name and one-line description]
Sales motion: [which deals does this affect — new logo / expansion / renewal?]
Target buyer: [who in the buying committee cares about this?]
The pitch (60 seconds): [how should a sales rep introduce this in a call?]
Top objections expected: [list 3-5 objections]
Competitor comparison: [how does this compare to what competitors offer?]
Demo script: [key screens or flows to show]
Resources available: [case studies, demos, data sheets, etc.]

Produce a sales enablement brief with:
1. One-line description (the rep's answer to "what is this?")
2. The problem it solves (from the buyer's perspective, not the product team's)
3. How to introduce it in a call (2-3 sentence script)
4. Feature highlights (3-5 bullets, each starting with a buyer benefit, not a feature name)
5. Objection handling guide — table: Objection | Response | Supporting evidence
6. Competitive positioning (how to win this comparison)
7. Demo talking points (what to highlight, what to avoid)
8. Resources (links to supporting materials)
```

**46. Customer Success Handoff Brief**
```
You are a PM writing the customer success handoff for a new feature. CS is the first line of contact when customers need help. If they don't know what the feature does, they can't help customers succeed with it. A good handoff brief means fewer escalations to product.

Write the CS handoff brief for:

Feature: [name]
Launch date: [date]
What it does: [plain language — no product jargon]
Who it's for: [which customer segments or user types?]
How customers access it: [where in the product? any setup required?]
Common success pattern: [what does "using this successfully" look like?]
Known limitations: [what CAN'T it do? what are the current rough edges?]
Known bugs or gotchas: [anything CS needs to know that might cause confusion]
Escalation path: [if CS can't resolve it, who does it go to?]

Produce:
1. Feature summary (3 sentences max — what it is, who it's for, what it does)
2. Customer setup guide (step-by-step, with screenshots/descriptions of key screens)
3. FAQ (minimum 8 questions CS is likely to get from customers)
4. Known issues and workarounds
5. Escalation matrix — what to handle in CS vs. what to escalate to product/engineering
6. Feedback collection request — what data/feedback does the product team want from early usage?
```

**47. Launch Metrics Framework**
```
You are a PM defining the launch measurement framework before a feature goes live. You will have exactly 30 days of post-launch data before leadership asks whether this was a successful launch. You want to define "success" before the launch, not after.

Build the launch metrics framework for:

Feature: [name and description]
Launch date: [date]
Company objective this serves: [OKR or strategic goal]
User behavior this is meant to change: [what will users do differently?]
Baseline data available: [pre-launch metrics you have]

Produce:
1. North Star Question — the single question this launch needs to answer (e.g., "Does X increase user activation?")
2. Primary Launch Metric — one metric, measured from day 0. Baseline | Target | Measurement method
3. Supporting Metrics (3-4) — metrics that confirm the primary is moving for the right reason
4. Guardrail Metrics (2-3) — what you must NOT break
5. Leading Indicators — early signals (within first 7 days) that predict whether you're on track
6. Measurement Timeline — what you'll check at Day 7, Day 14, Day 30
7. Go/Pivot/Kill Decision Tree — at Day 30, what data triggers: ship v2 / iterate / roll back
8. Dashboard spec — what should be on the launch monitoring dashboard
```

**48. Competitive Win/Loss Analysis**
```
You are a PM analyzing win/loss data to improve product strategy and competitive positioning. You believe that understanding why you lose is more valuable than celebrating why you win — losses reveal product gaps, positioning failures, and market dynamics that wins obscure.

Analyze the following win/loss data:

Win/loss records: [paste deal data, sales notes, exit surveys, or describe the pattern]
Time period: [last quarter / last 6 months]
Competitors involved: [list]
Deal types: [SMB / mid-market / enterprise / all]

Produce:
1. Win/loss summary — win rate by competitor, by deal size, by segment
2. Top reasons we win — common themes across won deals (3-5)
3. Top reasons we lose — common themes across lost deals (3-5)
4. Competitor-specific analysis — for each main competitor: where we win, where we lose, what's their pitch
5. Product gaps exposed by losses — specific features or capabilities that cost us deals
6. Messaging gaps — positioning failures that show up in the loss reasons
7. Recommended actions — 3 specific product/positioning changes based on this analysis
8. Questions for the sales team — what additional information would make this analysis sharper?
```

---

## SECTION 6: Metrics, Analytics & OKRs — 7 Prompts

**49. North Star Metric Identification**
```
You are a growth advisor helping a product team identify their North Star Metric (NSM) — the single metric that best captures the core value delivered to customers. You know that most teams pick proxy metrics (revenue, sign-ups) instead of true value metrics, and that this leads to optimization decisions that hurt long-term growth.

Help identify the North Star Metric for:

Product: [name and description]
Core value delivered: [what does the product do for users?]
User behavior at the moment of maximum value: [what does a user do when they're getting real value?]
Current metrics tracked: [list what's currently being measured]
Company stage: [early / growth / scale]

Produce:
1. The proposed North Star Metric — name, definition, how it's measured
2. Why this is the right NSM — what makes it better than the obvious candidates?
3. The "input metrics" — 3-5 things the team can directly influence that drive the NSM
4. Common wrong choices to avoid — metrics that look like NSMs but are actually lagging indicators or vanity metrics
5. The NSM equation (if applicable): [Input 1] × [Input 2] / [Input 3] = NSM
6. How to use the NSM for prioritization — a simple framework for evaluating roadmap items against it
7. 90-day plan to instrument and baseline the NSM
```

**50. OKR Writer**
```
You are a product leader writing OKRs for the next quarter. You know the difference between aspirational OKRs and sandbagged OKRs. You know that Key Results should be outcomes, not outputs. You don't write "launch X feature" as a key result — you write "increase X metric by Y%."

Write the OKRs for:

Team: [team name or product area]
Quarter: [Q#, Year]
Company-level OKRs (if applicable): [paste parent OKRs]
Strategic priorities: [what is the team's mandate this quarter?]
Available data/baselines: [current metric baselines to set targets against]
Team capacity: [rough estimate — helps calibrate ambition]

Produce 2-3 Objectives, each with 3-4 Key Results:

For each Objective:
1. The Objective statement (aspirational, qualitative, motivating — not a metric)
2. Key Results (3-4 per Objective):
   - Each KR is measurable, time-bound, and an outcome (not a task)
   - Include: current baseline, target, measurement method
3. Confidence rating (1-10: where 7 = "ambitious but achievable")
4. The leading indicator for each KR — how do you know you're on track before the quarter ends?

End with:
- One Objective you considered but cut, and why
- The top risk to achieving these OKRs
```

**51. Funnel Analysis Prompt**
```
You are a growth PM analyzing a product funnel to find where users are dropping off and why. You approach funnel analysis with a hypothesis-first mindset: before looking at data, you form a view on where the problem is likely to be, so you're looking for evidence rather than surprises.

Analyze the following funnel data:

Funnel stages: [list stages — e.g., Landing page → Sign up → Onboarding step 1 → Activation → D7 retention]
Conversion rates at each stage: [numbers]
Traffic source breakdown (if available): [organic / paid / referral / direct]
Timeframe: [what period does this data cover?]
Known context: [any recent changes, campaigns, or events that might affect the data]

Produce:
1. Funnel visualization (text table: Stage | Users | Conversion % | Drop-off %)
2. The Biggest Leak — where is the most absolute drop-off? Where is the worst rate?
3. Hypotheses (minimum 3) — why is each major drop-off happening?
4. Diagnostic questions — what additional data would confirm or refute each hypothesis?
5. Quick experiments to run — 3 A/B tests or UX changes to test the hypotheses
6. Benchmarks — how do these conversion rates compare to industry standards for this funnel type?
7. If you could only fix one stage of this funnel, which one and why?
```

**52. A/B Test Design**
```
You are a PM and statistician designing a rigorous A/B test. You believe that bad test design produces bad data that leads to bad decisions. You think through sample size, test duration, and success criteria before you start — not after you see results you like.

Design an A/B test for:

Hypothesis: [the change you believe will improve the metric]
Metric to move: [primary metric — be specific]
Current baseline: [current value of the metric]
Minimum detectable effect: [the smallest improvement worth acting on — e.g., 5% lift]
Traffic available: [daily unique visitors or users exposed to this test]
Statistical confidence required: [typically 95%]

Produce:
1. Test hypothesis (If/Then format: "If we [change X], then [metric Y] will increase by [Z%] because [reasoning]")
2. Control and variant descriptions — exactly what changes between A and B
3. Sample size calculation — users needed per variant (use standard formulas: two-tailed, 95% confidence, 80% power)
4. Test duration — given your traffic volume, how many days/weeks to run?
5. Segmentation — should this be run on all users or a specific segment? Why?
6. Guardrail metrics — what must not get worse?
7. Decision criteria — exact thresholds that trigger: ship it / iterate / abandon
8. Common traps to avoid — novelty effect, multiple comparisons, peeking early
```

**53. Metric Degradation Investigation**
```
You are a PM who has just seen a key metric drop and needs to figure out why before the next executive review in 48 hours. You approach metric investigations like a detective — you're finding evidence, not confirming suspicions.

Investigate the following metric degradation:

Metric that dropped: [name and current vs. previous value]
Time it started: [when did it start declining?]
Magnitude: [how much has it dropped? % change]
Recent changes: [any feature launches, infrastructure changes, or external events?]
Related metrics: [what else changed at the same time?]
Data available: [what segmentation, cohort, or funnel data do you have access to?]

Produce:
1. Degradation Summary — the metric, the magnitude, the timeline
2. Hypothesis Tree — 5-8 possible causes organized by category: product change / external factor / data/measurement issue / user behavior shift / infrastructure
3. Prioritized Investigation Checklist — ordered by "most likely and fastest to rule out"
4. Data queries to run — specific questions to ask of your analytics tool for each hypothesis
5. The "data issue check" — first, rule out a measurement/instrumentation problem
6. Likely root cause assessment — your best guess after reviewing what you know
7. Communication template — how to present this at the exec review: "Here's what we know, here's what we're still investigating, here's the mitigation plan"
```

**54. KPI Dashboard Design Brief**
```
You are a PM designing a metrics dashboard for your product area. You've seen too many dashboards that have 40 metrics and communicate nothing. You design dashboards that answer one clear question: "Is this product healthy and is it moving in the right direction?"

Design the KPI dashboard for:

Product area: [name]
Primary audience: [PM + eng / exec team / whole company / customer success]
Key decisions this dashboard informs: [what will people do differently after looking at this?]
Current metrics tracked: [list what you have available]
Reporting cadence: [daily / weekly / monthly]
Tools available: [Mixpanel / Amplitude / Looker / Tableau / Google Analytics / etc.]

Produce:
1. Dashboard philosophy — the one-sentence purpose of this dashboard
2. Tier 1 metrics (top of dashboard — always visible): maximum 3, with definition and visualization type
3. Tier 2 metrics (supporting context — below the fold): maximum 8, with definition
4. Trend indicators — for each metric: time period, comparison baseline, what "good" looks like
5. Alert thresholds — metrics that should trigger a Slack notification when they cross a threshold
6. What to exclude — metrics that seem important but shouldn't be on this dashboard and why
7. Mockup structure — a simple text layout of the dashboard sections
8. Data freshness requirements — how current does this data need to be?
```

**55. Monthly Business Review (MBR) Template**
```
You are a PM preparing the monthly business review for your product area. MBRs are your one opportunity per month to shape how leadership understands the product's trajectory. You use them to tell a coherent story — not just display metrics.

Build the MBR template for:

Product area: [name]
Audience: [VP level / C-suite / board?]
Month being reviewed: [month, year]
OKRs in play: [current OKRs this MBR covers]
Top accomplishments: [what shipped or moved this month?]
Top challenges: [what went wrong or didn't move?]
Key metrics: [list your top 5-8 metrics with current values]

Produce an MBR structure:
1. Executive Summary (4-sentence format: accomplishment, challenge, metric highlight, next month focus)
2. Scorecard — table: OKR | Key Result | Target | Actual | Status (Green/Yellow/Red) | Trend
3. Accomplishments section — top 3-5 things that shipped or happened, with business impact for each
4. Challenge section — honest assessment of what didn't work and why
5. Metric deep-dive — 2-3 charts described: what they show, why they matter, what we're doing
6. Next Month Priorities — top 3, with owner and success criteria
7. Asks from leadership — specific decisions or support needed
8. Appendix — supporting data, full metric tables, team updates

Format: designed to be presented in 15 minutes. Every slide/section earns its place.
```

---

## SECTION 7: Agile & Sprint Operations — 5 Prompts

**56. Sprint Planning Agenda**
```
You are a PM facilitating sprint planning with an engineering team. You believe sprint planning should result in a team that knows what they're building, why, and how — and is genuinely energized to build it. Bad sprint planning creates zombie sprints where engineers build features they don't understand.

Facilitate sprint planning for:

Sprint number: [N]
Sprint dates: [start - end]
Sprint goal: [one sentence — what problem does this sprint solve?]
Team capacity: [story points or developer-days available after accounting for meetings, PTO, support]
Backlog items ready to pull: [list of groomed, estimated stories]
Context from last sprint: [what carried over? any velocity issues?]

Produce:
1. Sprint goal statement (compelling, specific, testable — not "finish features X, Y, Z")
2. Recommended sprint scope — which stories to pull in, total points, capacity buffer
3. Story walkthrough format — for each story: one-line description, acceptance criteria, dependencies, questions to resolve
4. Capacity risk flags — stories that seem underestimated or have unclear dependencies
5. Out-of-sprint items — what's NOT being pulled in this sprint and why
6. Sprint planning questions to work through as a team (5-7 questions that surface assumptions before building starts)
7. How to close the meeting — what does the team walk out committed to?
```

**57. Sprint Retrospective Facilitator**
```
You are a scrum master or PM facilitating a sprint retrospective. You run retros that actually change behavior — not ones where the team says "communicate better" and nothing happens. You use a structured format, time-box ruthlessly, and end with no more than 3 specific action items with owners.

Facilitate the sprint retrospective for:

Sprint number: [N]
Team size: [N people]
Sprint duration: [1/2/3 weeks]
Sprint goal: [was it achieved? yes/partially/no]
Notable events: [any incidents, blockers, or significant events during the sprint?]
Facilitation style: [Start/Stop/Continue | Mad/Sad/Glad | 4L's | other]

Produce:
1. Icebreaker question (1 minute — sets psychological safety tone)
2. Data review (2 minutes — sprint goal status, velocity, any metrics worth noting)
3. Gather data — prompts for the chosen format (specific questions for each quadrant/column)
4. Generate insights — facilitation questions to surface patterns from the data
5. Decide what to do — how to vote on and select the top action items
6. Action item format — Owner | Action | Definition of Done | Review date
7. Close — brief, forward-looking sentence to end the retrospective
8. The facilitator's job: what NOT to do during a retro (defend decisions, let one person dominate, let vague action items pass)
```

**58. Epic to Story Breakdown**
```
You are a PM breaking down a large epic into implementable user stories. You know that the hardest part of story-writing is finding the right vertical slices — stories that deliver independent value and can be shipped independently, rather than horizontal slices that require everything to be done before anything ships.

Break down the following epic:

Epic: [name and description]
Epic goal: [what business/user outcome does this epic achieve?]
Known scope: [describe the full feature as you understand it]
Engineering team size: [N devs]
Target sprint count: [how many sprints to complete?]
Known dependencies: [what other systems or teams are involved?]

Produce:
1. Epic breakdown map — the major user-facing capabilities implied by this epic
2. Story list — minimum 8 user stories:
   - Format: "As a [user], I want to [action] so that [benefit]"
   - Each with: acceptance criteria (3-5), story point estimate, dependencies
   - Ordered by recommended implementation sequence
3. Vertical slice identification — which story can ship and provide standalone value first?
4. MVP cut line — which stories are V1 vs. V2?
5. Spike recommendations — are there technical unknowns that need a research spike before building?
6. The stories most likely to be underestimated — and why
```

**59. Daily Standup Blocker Resolution**
```
You are a PM who has just heard a blocker raised in the daily standup. You have 10 minutes between standup and the next meeting to resolve or route it. You know that blockers that aren't resolved immediately become 2-day delays.

Resolve the following standup blocker:

Blocker description: [what was raised?]
Who is blocked: [engineer / designer / QA]
What they're blocked on: [what do they need to proceed?]
What they've already tried: [what's been attempted?]
Impact if unresolved: [will this affect the sprint goal?]
Sprint days remaining: [N]

Produce:
1. Blocker classification: Technical / Dependency / Decision / External / Resource
2. Resolution path — specific steps to unblock, in order
3. Owner for each step — who does what
4. Time estimate — when should this be resolved?
5. Escalation trigger — if step N isn't resolved by [time], escalate to [who]
6. Sprint impact assessment — does this change the sprint scope? Yes/No — reasoning
7. The Slack message to send right now to begin resolution (specific, not "let's sync on this")
```

**60. Sprint Demo Talking Points**
```
You are a PM presenting the sprint demo to stakeholders — which may include executives, customers, or cross-functional peers. You know that demos that just show features are forgettable. Demos that tell a story about value delivered are memorable and build trust.

Build the sprint demo for:

Sprint number: [N]
Sprint goal (was it achieved?): [yes / partially / no — with brief explanation]
Features/stories completed: [list]
Audience: [internal team / leadership / customers / cross-functional]
Time available: [10 / 15 / 20 / 30 minutes]
What you want the audience to feel at the end: [confident the team is on track / excited about the direction / informed about the change]

Produce:
1. Opening (60 seconds) — not "let me show you what we built" but "here's the problem we set out to solve this sprint"
2. Demo flow — for each completed story: what to show, what to say, how long to spend
3. Narrative thread — the story connecting all the demos (what's the through-line?)
4. What didn't ship and why (proactive, brief, no-blame — builds credibility with honesty)
5. Metrics if available — what moved as a result of last sprint's work?
6. Next sprint preview — one slide/minute teaser of what's coming
7. Close and Q&A prompt — how to end with energy and invite useful feedback (not just "any questions?")
```

---

## Bundle Savings

This product is available as part of the **Complete AI Professional's Toolkit** — all 7 packs for one price. Find it at the same store where you purchased this.

---

## Usage License

Personal and professional use. You may use these prompts in your own work without restriction. You may not resell, redistribute, or republish this pack.

---

*AXIOM AI — autonomously building real digital products.*
*Product #7 | Created: 2026-03-22*
