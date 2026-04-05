# The SRE & DevOps AI Prompt Pack
## 55 Production Reliability Prompts for Engineers Who Own the Stack

**Product ID:** PROD-005
**Price:** $24.99
**Format:** Markdown + JSON
**Audience:** Site Reliability Engineers, DevOps Engineers, Platform Engineers, Infrastructure Leads, Engineering Managers who own reliability

---

## Why This Pack Exists

At 2:47 AM, your pager fires. The payment service is down. Every second costs money.

You don't need an AI to write your runbook in that moment — you needed the runbook *before* that moment. You don't need help writing a postmortem after the outage — you needed the *culture* in place to make postmortems valuable. You don't need to debug alerting philosophy in an incident bridge — you needed your SLOs *defined*.

These 55 prompts exist for the 99% of SRE/DevOps work that happens *between* incidents — the runbook writing, the SLO definition sessions, the alert tuning, the IaC reviews, the postmortem facilitation, the on-call process improvement — that never gets enough time because there's always a fire somewhere.

Use AI to do the heavy drafting. Use your expertise to make it right.

Every prompt in this pack is engineered for:
- **Operational specificity**: Asks for exactly the context an SRE needs to think about
- **Blameless framing**: Postmortem and incident prompts focus on systems, not individuals
- **Production realism**: No toy examples — these are prompts for real systems under load
- **Reviewable output**: Gets you a strong first draft you verify, not output you trust blindly

> **Note on AI-assisted operations**: These prompts are drafting and thinking tools. Never apply AI-generated infrastructure changes without human review. Never paste production secrets into AI prompts. These prompts are designed to help you think and document — the final judgment is always yours.

---

## SECTION 1: Incident Response & Command (10 Prompts)

### INC-001: Incident Triage & Priority Assessment
```
You are an experienced SRE helping triage an active incident. Based on the information below, help me determine priority and initial action.

Service affected: [SERVICE NAME]
Symptoms observed: [WHAT IS BROKEN - errors, latency, unavailability]
Affected users: [NUMBER/PERCENTAGE]
Time since start: [DURATION]
Recent deployments: [ANY DEPLOYS IN LAST 24H]
Monitoring alerts fired: [ALERT NAMES]

Please provide:
1. Incident severity assessment (P1/P2/P3/P4) with reasoning
2. Immediate actions to take in the next 5 minutes
3. Key hypotheses ranked by likelihood (most likely cause first)
4. Who should be paged right now
5. First diagnostic commands to run

Be direct. Skip preamble. I am in an active incident.
```

### INC-002: Incident Communication — Status Page Update
```
I need to write a customer-facing status page update for an ongoing incident. This will be public.

Incident summary: [WHAT IS HAPPENING]
Current status: [INVESTIGATING / IDENTIFIED / MONITORING / RESOLVED]
Time of first impact: [TIMESTAMP]
Services affected: [LIST]
Customer impact: [WHAT CUSTOMERS CANNOT DO]
What we know: [CAUSE IF KNOWN, OR "under investigation"]
What we're doing: [CURRENT ACTIONS]

Write a status page update that is:
- Clear and jargon-free for non-technical customers
- Honest about impact without alarming language
- Specific about what you know and what you don't
- Under 150 words
- Written in present tense ("we are investigating" not "we investigated")

Also write the 1-line tweet-length summary for the status banner.
```

### INC-003: Internal Incident Bridge Kickoff Script
```
I'm the incident commander for a P1 incident. Help me structure the first 3 minutes of the incident bridge call.

Service down: [SERVICE]
Estimated customer impact: [SCOPE]
People on the call: [SRE LEAD, ON-CALL ENG, COMMS, MANAGEMENT - adjust as needed]
What we know so far: [BRIEF SUMMARY]

Write a structured kickoff script for the first 3 minutes that covers:
1. The opening statement (who I am, what we know, what we're doing)
2. Role assignments for this incident
3. Communication cadence we'll maintain
4. How we'll document findings in real-time
5. The specific question I'll ask the first technical lead

Tone: calm, directive, professional. No panic language.
```

### INC-004: Rollback Decision Framework
```
I'm in an active incident and considering a rollback. Help me think through this decision.

Current situation: [WHAT IS BROKEN]
Last deployment: [WHAT CHANGED, WHEN]
Confidence that deployment caused this: [HIGH/MEDIUM/LOW - reasoning]
Rollback risks: [DATA MIGRATIONS? SCHEMA CHANGES? OTHER DEPENDENCIES?]
Time since deployment: [DURATION]
Current user impact: [SEVERITY]

Please give me:
1. A structured go/no-go assessment for rollback right now
2. The 3 key questions to answer before deciding
3. If rollback: the specific steps to execute safely
4. If no rollback: the next best mitigation path
5. What to monitor immediately after rollback to confirm it worked

I need to make this decision in 2 minutes.
```

### INC-005: Hypothesis-Driven Debugging Script
```
I'm debugging a production issue and need to work through hypotheses systematically.

Observed behavior: [WHAT IS BROKEN AND HOW IT MANIFESTS]
Error messages / logs: [PASTE RELEVANT SNIPPETS]
Infrastructure stack: [E.G., K8S + RDS POSTGRES + REDIS + CLOUDFRONT]
Recent changes: [DEPLOYS, CONFIG CHANGES, TRAFFIC CHANGES, ANYTHING]
Checks already done: [WHAT YOU'VE RULED OUT]

Please:
1. Generate 5 specific hypotheses ranked by probability
2. For each hypothesis: the single fastest diagnostic command or check
3. The decision tree: if check X shows Y → conclusion Z
4. Any "gotcha" patterns that match these symptoms in production systems
5. The most commonly missed check for incidents like this

Format as a numbered decision tree I can follow live.
```

### INC-006: Escalation Decision Helper
```
I'm an on-call engineer and need to decide whether to escalate this incident.

Current incident: [DESCRIPTION]
Severity so far: [P1/P2/P3]
Time spent investigating: [DURATION]
Progress made: [WHAT YOU'VE TRIED AND RESULTS]
My confidence in resolution path: [0-100%]
Available escalation targets: [WHO COULD HELP AND THEIR EXPERTISE]
Time of day/timezone: [CONTEXT]

Help me decide:
1. Should I escalate right now? Why or why not?
2. If yes: who specifically and what information do I give them?
3. What is the 15-minute checkpoint — if I haven't found X by then, I escalate?
4. Draft the escalation message/page I would send

I want to be neither over-escalating nor heroically solo-ing things I shouldn't be.
```

### INC-007: Customer Impact Estimation During Incident
```
I need to estimate customer impact during an active incident for our incident report and status communications.

Service affected: [SERVICE]
Error type: [TIMEOUTS / 5XX / DATA INCORRECT / PARTIAL OUTAGE]
Error rate in monitoring: [PERCENTAGE OR COUNT/MINUTE]
Normal request volume: [REQUESTS/MINUTE OR DAY]
Time window of impact: [START TO NOW]
User geography: [GLOBAL / SPECIFIC REGIONS]
Affected features: [LIST WHAT DOESN'T WORK]

Calculate:
1. Estimated affected user-sessions (show your math)
2. Estimated failed requests total
3. Customer-facing language for the impact ("approximately X% of users attempting to Y experienced Z")
4. What data we should be preserving now for the postmortem impact analysis
5. SLA/SLO breach assessment: will this trigger a credit/violation?
```

### INC-008: War Room Notes Synthesis
```
I have raw notes from an incident bridge call and need to turn them into a structured incident timeline.

Raw notes: [PASTE YOUR MESSY NOTES]

Please:
1. Reconstruct a chronological timeline with timestamps (in [TIME]: [EVENT] format)
2. Identify the key turning points: when did we detect, when did we identify the cause, when did we mitigate, when did we resolve?
3. Flag any gaps in the timeline where we should add more context
4. Extract action items that came up during the incident (format: [OWNER] will [ACTION] by [DATE])
5. Write the one-paragraph "incident summary" for the postmortem document header

Note: Do not speculate — only include what's in the raw notes. Flag anything unclear as [UNCLEAR - VERIFY].
```

### INC-009: Post-Incident Immediate Actions Checklist
```
The incident is resolved. Help me make sure I don't miss anything in the next 30 minutes.

Incident: [BRIEF DESCRIPTION]
Root cause (preliminary): [WHAT WE THINK HAPPENED]
Duration: [START TO RESOLUTION TIMESTAMP]
Impact: [SCOPE]
Fix applied: [WHAT WE DID TO RESOLVE]

Generate a post-incident checklist covering:
1. Monitoring to watch for recurrence in the next hour
2. Status page update to write (resolved message)
3. Customer communications to send (if any)
4. Internal communications (eng-team Slack, leadership)
5. Postmortem scheduling (who, when, what doc to start)
6. Any temporary mitigations to clean up later
7. On-call handoff notes if the shift is changing

Mark each as [IMMEDIATE] (< 30 min), [TODAY], or [THIS WEEK].
```

### INC-010: Regression Risk Assessment After Fix
```
We've applied a fix to resolve the incident. Before we stand down, help me assess regression risk.

Fix applied: [WHAT CHANGE WAS MADE]
How it was deployed: [CANARY / FULL ROLLOUT / CONFIG CHANGE / ROLLBACK]
Confidence in fix: [HIGH/MEDIUM/LOW - reasoning]
Side effects we checked: [WHAT YOU VERIFIED]
Monitoring we have: [ALERTS, DASHBOARDS WATCHING]

Please provide:
1. What could go wrong with this specific fix (fresh eyes assessment)
2. The 5 key metrics to watch for the next 2 hours
3. Decision criteria: at what threshold do we consider re-escalating?
4. Recommended standby period before full stand-down
5. A one-line go/no-go statement for leadership: "We believe this is resolved because..."
```

---

## SECTION 2: Runbook & Playbook Creation (10 Prompts)

### RUN-001: Full Service Runbook Template Generation
```
Help me write a comprehensive runbook for a production service.

Service name: [NAME]
What it does: [1-2 sentence description]
Technology stack: [E.G., NODE.JS API + POSTGRES + REDIS + K8S]
Primary failure modes we've seen: [LIST]
Who owns it: [TEAM]
Dependencies: [UPSTREAM AND DOWNSTREAM SERVICES]
SLO targets: [UPTIME %, LATENCY P99]

Generate a complete runbook outline and fill in the sections I can't fill with placeholders. The runbook should include:
1. Service overview and purpose
2. Architecture diagram (describe as ASCII or markdown)
3. Key metrics and dashboards (with [PASTE YOUR DASHBOARD URLS] placeholders)
4. Common failure modes and resolution steps
5. Escalation contacts
6. Deployment procedure
7. Rollback procedure
8. Maintenance tasks (and their frequency)
9. On-call context (what new on-call engineers need to know)

Format as a markdown document I can paste into Confluence/Notion/GitHub.
```

### RUN-002: Incident-Specific Playbook From an Outage
```
We just had an incident and I want to turn it into a runbook playbook so the next person handles it faster.

What broke: [SERVICE / COMPONENT]
Root cause: [WHAT ACTUALLY HAPPENED]
How we detected it: [ALERT / USER REPORT / MONITORING]
How we diagnosed it: [STEPS TAKEN]
How we resolved it: [THE FIX]
Time from detection to resolution: [DURATION]
What made it hard to debug: [FRICTION POINTS]

Create a runbook playbook entry that includes:
1. Title: "[SYMPTOM] — [SERVICE] Runbook"
2. When to use this playbook (symptoms to look for)
3. Prerequisite knowledge and access required
4. Step-by-step diagnostic procedure (numbered, specific)
5. Resolution steps (numbered, with verification checks)
6. Common variations and edge cases
7. Prevention: what we're doing so this doesn't happen again

The goal: the next on-call engineer should be able to resolve this 3x faster.
```

### RUN-003: Database Maintenance Runbook
```
Write a database maintenance runbook for the following scenario.

Database: [POSTGRES / MYSQL / MONGODB / OTHER]
Task needed: [E.G., VACUUM, INDEX REBUILD, MIGRATION, BACKUP RESTORE TEST, FAILOVER TEST]
Environment: [MANAGED (RDS/CLOUD SQL) OR SELF-HOSTED]
Database size: [APPROXIMATE SIZE]
Traffic pattern: [PEAK HOURS, ACCEPTABLE MAINTENANCE WINDOWS]
Team expertise level: [BEGINNER / INTERMEDIATE / EXPERT]

Create a step-by-step runbook that includes:
1. Pre-task checklist (what to verify before starting)
2. Estimated duration and impact on service
3. Step-by-step execution with exact commands
4. Verification checkpoints throughout
5. Rollback/abort procedure
6. Post-task verification
7. When to stop and escalate

Include warnings for the 3 most common mistakes teams make with this task.
```

### RUN-004: Kubernetes Troubleshooting Playbook
```
Create a Kubernetes troubleshooting playbook for the following scenario.

Issue type: [POD CRASHLOOP / IMAGEPULLBACKOFF / PENDING SCHEDULING / OOM / HIGH LATENCY / NODE NOT READY]
Cluster environment: [EKS / GKE / AKS / SELF-MANAGED]
Team K8s experience: [BEGINNER / INTERMEDIATE / EXPERT]
Available tooling: [KUBECTL, K9S, LENS, DATADOG - LIST WHAT YOU HAVE]

Create a structured playbook:
1. Initial triage commands (with exact kubectl commands, explain each)
2. Decision tree: if [SYMPTOM A] → check [X]; if [SYMPTOM B] → check [Y]
3. Common root causes for this issue type (ranked by frequency)
4. Fix procedures for each cause
5. How to verify the fix
6. Monitoring to watch after fix
7. Prevention: admission controllers, resource limits, or configurations to prevent recurrence

Format kubectl commands in code blocks with expected output examples.
```

### RUN-005: Load Testing Runbook
```
I need a runbook for running load tests against our service before a major launch.

Service: [NAME AND BRIEF DESCRIPTION]
Expected peak traffic: [REQUESTS/SECOND OR CONCURRENT USERS]
Normal traffic baseline: [CURRENT LOAD]
Target SLOs: [LATENCY P95/P99, ERROR RATE THRESHOLD]
Load testing tool available: [K6 / LOCUST / GATLING / ARTILLERY / OTHER]
Environment for testing: [STAGING / PROD WITH FEATURE FLAG / OTHER]

Create a complete load testing runbook:
1. Pre-test checklist (dependencies, monitoring, team notification)
2. Test scenarios to run (ramp-up profile, steady state, spike test)
3. Metrics to monitor in real-time during test
4. Go/no-go criteria: what results indicate we're ready to launch
5. Failure criteria: when to stop the test immediately
6. How to analyze results and document findings
7. Post-test cleanup

Include the specific K6/Locust config template for the ramp-up profile.
```

### RUN-006: Certificate & Secret Rotation Playbook
```
Create a certificate/secret rotation runbook for our environment.

What to rotate: [TLS CERT / API KEY / DATABASE PASSWORD / JWT SECRET / SSH KEY]
Service affected: [NAME]
Dependencies: [WHAT ELSE USES THIS SECRET]
Current rotation frequency: [NEVER / ANNUALLY / QUARTERLY / AS NEEDED]
Secret management tool: [AWS SECRETS MANAGER / VAULT / K8S SECRETS / .ENV FILES]

Write a rotation playbook:
1. Pre-rotation checklist and validation
2. How to generate/obtain the new credential
3. Zero-downtime rotation procedure (how to roll without dropping requests)
4. Service-by-service update order (if multiple services)
5. Verification that new credential works before revoking old
6. Revocation of old credential
7. Documentation updates needed
8. How to set up automated rotation going forward

Highlight any step where a mistake could cause an outage — mark these [HIGH RISK].
```

### RUN-007: On-Call Handoff Template
```
Create a structured on-call handoff template for our engineering team.

Team size: [NUMBER OF ENGINEERS]
On-call rotation: [WEEKLY / BI-WEEKLY / OTHER]
Services owned: [LIST]
Current known issues: [ANY ACTIVE INCIDENTS OR DEGRADATIONS]
Recent changes: [NOTABLE DEPLOYS OR CONFIG CHANGES IN LAST WEEK]
Upcoming changes: [PLANNED DEPLOYMENTS, MAINTENANCE, LOAD EVENTS]

Generate a handoff document template with these sections filled based on context:
1. "State of the system" summary (traffic normal? any degradations?)
2. Active incidents or monitoring anomalies to watch
3. Known issues that aren't incidents yet (things to keep an eye on)
4. Recent deployments and their status
5. Upcoming work the incoming engineer should know about
6. Open action items from the previous rotation
7. "Things I'd do differently" — lessons from this rotation

Goal: incoming on-call engineer should be productive in 5 minutes with this doc.
```

### RUN-008: Disaster Recovery Drill Playbook
```
Create a disaster recovery drill playbook for the following scenario.

Service: [NAME]
DR scenario to test: [DATABASE FAILOVER / REGION FAILOVER / COMPLETE DATA RESTORE / SERVICE FAILOVER]
Last DR test: [DATE OR "NEVER"]
RTO target (recovery time): [HOURS]
RPO target (data loss tolerance): [HOURS / MINUTES]
Team: [WHO SHOULD BE INVOLVED]

Create a DR drill playbook:
1. Drill objectives and success criteria
2. Pre-drill communication plan (who to notify, how far in advance)
3. Safety measures (how to avoid making the drill into an actual incident)
4. Step-by-step drill execution procedure
5. Metrics to capture during drill (actual RTO/RPO vs. targets)
6. What to do if the drill reveals a real problem
7. Post-drill documentation and improvement tracking

Also: list the 5 most common ways DR drills go wrong and how to prevent each.
```

### RUN-009: Capacity Planning Runbook
```
Help me create a capacity planning runbook for a production service.

Service: [NAME]
Current infrastructure: [E.G., 3x C5.XLARGE EC2, 2X POSTGRES RDS M5.LARGE]
Current utilization: [CPU %, MEMORY %, STORAGE %]
Current traffic: [REQUESTS/DAY OR CONCURRENT USERS]
Growth trend: [% MONTH OVER MONTH]
Upcoming events that affect load: [LAUNCHES, SEASONALITY, CAMPAIGNS]

Create a capacity planning runbook:
1. How to read capacity signals (what metrics matter, what thresholds trigger action)
2. Capacity review cadence (weekly check vs. monthly deep review)
3. Scale-up decision criteria and procedure
4. Lead time considerations for different resource types
5. Cost vs. performance trade-off framework for this service
6. How to model growth scenarios
7. Quarterly capacity review template
8. When to escalate capacity concerns to leadership

Include specific alert thresholds to configure for proactive capacity warnings.
```

### RUN-010: New Service Pre-Launch Reliability Checklist
```
A new service is about to launch. Help me create a pre-launch reliability checklist.

Service name: [NAME]
What it does: [DESCRIPTION]
Expected traffic at launch: [ESTIMATE]
Launch date: [DATE]
Tech stack: [STACK]
Team: [SIZE AND EXPERIENCE]

Generate a comprehensive pre-launch reliability checklist with these categories:
1. Observability (logging, metrics, tracing, alerting — what must exist before launch)
2. Runbook status (minimum docs required)
3. Load testing (what tests to run and pass criteria)
4. Failure mode testing (chaos engineering / fault injection)
5. Dependency review (what we depend on and their reliability)
6. Security review (minimum security requirements)
7. Rollback procedure (is it documented and tested?)
8. On-call preparation (who is on-call, do they know the service?)
9. Customer communication plan (if things go wrong at launch)
10. Launch day monitoring plan (what will we watch in real-time)

Mark each item: [BLOCKER] (can't launch without this) or [RECOMMENDED] (important but not blocking).
```

---

## SECTION 3: Postmortem Writing & Blameless Culture (8 Prompts)

### POST-001: Postmortem Document Drafter
```
Help me write a blameless postmortem for a production incident.

Incident: [TITLE / TICKET ID]
Date and duration: [WHEN / HOW LONG]
Customer impact: [WHAT CUSTOMERS EXPERIENCED]
Severity: [P1/P2/P3]
Root cause: [TECHNICAL CAUSE]
Contributing factors: [WHAT MADE IT WORSE OR HARDER TO CATCH]
Timeline: [KEY EVENTS IN CHRONOLOGICAL ORDER]
Resolution: [WHAT FIXED IT]
Team involved: [ROLES — NOT NAMES]

Write a complete postmortem document following the blameless format:
1. Executive summary (3 sentences max — what happened, impact, fix)
2. Timeline (formatted as [TIME]: [EVENT])
3. Root cause analysis (5 Whys or fishbone)
4. Contributing factors
5. What went well (must include real positives — detection speed, team response, etc.)
6. What went wrong
7. Where we got lucky (often overlooked — add this)
8. Action items (with category: DETECT / PREVENT / MITIGATE / PROCESS)

Blameless language guidelines: focus on systems, processes, and conditions — not individuals.
```

### POST-002: 5 Whys Facilitator
```
Facilitate a 5 Whys analysis for the following incident.

Incident: [DESCRIPTION OF WHAT BROKE]
Observable failure: [THE END SYMPTOM — E.G., "users could not check out"]
Technical context: [BRIEF DESCRIPTION OF THE SYSTEM]

Guide me through 5 Whys analysis:
1. Ask "Why did [OBSERVABLE FAILURE] happen?" and provide 2-3 candidate answers
2. For each answer: ask why THAT happened
3. Continue until we reach a systemic root cause (not "someone made a mistake")
4. Identify if there are multiple parallel causal chains
5. Map each chain to a category: DETECTION failure / PREVENTION failure / MITIGATION failure / PROCESS failure
6. Suggest what type of action addresses the true root cause

Stop at a root cause that is organizational or systemic — never stop at "a person did X wrong."
```

### POST-003: Postmortem Action Item Quality Review
```
Review these postmortem action items and improve them.

Incident: [BRIEF DESCRIPTION]
Current action items: [PASTE YOUR CURRENT LIST]

For each action item, evaluate:
1. Is it specific enough? (Vague: "improve monitoring" → Specific: "Add P95 latency alert on checkout-service with threshold 500ms")
2. Does it address a root cause or just a symptom?
3. Is it categorized correctly: DETECT / PREVENT / MITIGATE / PROCESS?
4. Does it have a clear owner role and realistic due date?
5. Is it the highest-leverage action we could take?

Then:
- Rewrite any weak action items with concrete specificity
- Identify if we're over-indexing on one category (e.g., all DETECT items, no PREVENT)
- Suggest 1-2 action items we might have missed
- Flag any action items that are actually just "someone will do better next time" (those don't prevent recurrence)
```

### POST-004: Blameless Language Audit
```
Review this postmortem draft for blameless language and rewrite problem sections.

Postmortem draft: [PASTE DRAFT]

Find and fix:
1. Any language that implies individual blame (name-based, "should have", "failed to")
2. Any language that assumes intent ("they forgot to", "ignored the alert")
3. Any place where "human error" is treated as a root cause rather than a symptom
4. Passive-aggressive phrasing ("the engineer, who had been warned...")
5. Language that implies one person could have prevented a systemic failure

For each issue:
- Quote the problematic text
- Explain why it's problematic
- Provide a blameless rewrite

Principle: a blameless postmortem assumes everyone made reasonable decisions given the information they had at the time. Blame belongs to systems and processes, not people.
```

### POST-005: What Went Well Excavator
```
Help me identify genuine "what went well" items for this postmortem.

Context: This was a [P1/P2] incident. Duration: [TIME]. Impact: [SCOPE].

Incident timeline: [PASTE KEY EVENTS]

Find genuine positives in these categories:
1. Detection: How quickly did we find out? Was it monitoring or a customer report? (Even if slow, was there anything good about how we detected?)
2. Response speed: How long from detection to bridge call? Any unusually fast responses?
3. Communication: Was the status page updated promptly? Internal comms clear?
4. Diagnosis speed: Did anyone demonstrate expertise that shortened the debugging?
5. Collaboration: Any examples of good cross-team coordination?
6. Rollback/mitigation: Was the fix applied cleanly and safely?
7. Lucky catches: Anything that could have been much worse that wasn't?

Goal: "What went well" should be real, specific, and educational — not just morale-padding. Every item should teach the team what good looks like.
```

### POST-006: Systemic Pattern Analyzer
```
I have postmortems from the last 6 months. Help me identify systemic patterns.

Postmortem summaries: [PASTE TITLES + ROOT CAUSES + ACTION ITEM CATEGORIES FROM EACH]

Analyze for:
1. Recurring root cause categories (deployment issues? dependency failures? alerting gaps? capacity?)
2. Action items we keep creating but never completing (process vs. prioritization problem?)
3. Services that appear repeatedly as the source of incidents
4. Time-of-day or day-of-week patterns
5. Failure modes that are spreading vs. modes we've fixed
6. Any root causes that suggest architectural debt needing real investment

Output:
- Top 3 systemic problems we're not fixing at the root
- 1 "quick win" that would reduce incident frequency immediately
- 1 "strategic investment" that would change the reliability trajectory
- Recommended quarterly reliability OKR based on this analysis

This analysis is for engineering leadership. Be direct about uncomfortable patterns.
```

### POST-007: Postmortem Meeting Facilitation Guide
```
Help me prepare to facilitate a blameless postmortem meeting.

Incident: [BRIEF DESCRIPTION]
Draft postmortem doc: [PASTE OR LINK]
Attendees: [ROLES — NOT NAMES — WHO WILL BE IN THE ROOM]
Known sensitivities: [ANY DYNAMICS TO BE AWARE OF — E.G., CROSS-TEAM TENSION, RECENT ORG CHANGES]
Duration: [30 MIN / 60 MIN / 90 MIN]

Create a facilitation guide:
1. Meeting structure with time allocations
2. Opening statement I should read (sets blameless tone)
3. Questions to drive each section of discussion
4. How to handle it if someone starts assigning blame
5. How to handle it if the person who made the mistake is quiet and seeming ashamed
6. How to close the action items discussion (get commitment without micromanaging)
7. How to close the meeting on a constructive note
8. The one question to send to attendees as a follow-up survey

Goal: everyone leaves feeling like this was useful, not like a trial.
```

### POST-008: Postmortem Retrospective — Are Our Action Items Actually Closing?
```
It's been 90 days since a significant incident. Help me run a follow-up review.

Original incident: [DESCRIPTION]
Original action items: [PASTE THE LIST WITH ORIGINAL DUE DATES]
Current status of each item: [COMPLETED / IN PROGRESS / STALLED / ABANDONED]

Analyze:
1. Completion rate (and whether this is normal for your team)
2. Which categories of action items completed vs. stalled (DETECT vs. PREVENT vs. PROCESS)
3. For stalled items: most likely reason (prioritization? unclear owner? turned out to be harder than expected?)
4. Has the underlying problem recurred in 90 days? (if yes: which uncompleted items would have prevented it?)
5. What should we do with abandoned items: reprioritize, deprioritize formally, or break them down smaller?

Output: A 1-page "action item health" report for the engineering manager and a recommended decision for each stalled item.
```

---

## SECTION 4: SLO/SLA Definition & Monitoring Strategy (10 Prompts)

### SLO-001: SLO Definition Workshop
```
Help me define meaningful SLOs for a production service.

Service: [NAME]
What it does: [DESCRIPTION]
Customer expectations: [HOW CUSTOMERS DESCRIBE "WORKING"]
Business criticality: [REVENUE-CRITICAL / IMPORTANT / INTERNAL TOOL]
Current known performance: [LATENCY P50/P95/P99, UPTIME, ERROR RATE — AS KNOWN]
Competitors/industry benchmarks: [IF KNOWN]

Walk me through defining:
1. The correct SLI (Service Level Indicator) to measure — what metric actually represents "is this working for the user?"
2. A realistic SLO target based on what's achievable and meaningful (not "four nines" by default)
3. The error budget this SLO implies (how much downtime/errors are allowed per month)
4. How to measure this SLI (what queries, what data source)
5. What to do when 50% of the error budget is consumed — and when 90% is consumed
6. How this SLO maps to any customer-facing SLA commitments

Output as a structured SLO definition document I can add to our reliability handbook.
```

### SLO-002: Alert Design for an SLO
```
Help me design alerts that protect an SLO without creating alert fatigue.

Service: [NAME]
SLO target: [E.G., 99.9% availability over 30 days]
Error budget: [CALCULATED FROM SLO]
Current alert setup: [WHAT EXISTS NOW — OR "NONE"]
Monitoring tool: [DATADOG / PROMETHEUS+GRAFANA / CLOUDWATCH / NEWRELIC / OTHER]

Design a multi-window alerting strategy:
1. Burn rate alert for fast-burn scenarios (consuming error budget too quickly)
2. Burn rate alert for slow-burn scenarios (steady degradation we'd miss)
3. Exact alert thresholds with reasoning (don't just give numbers, explain why)
4. Alert severity mapping: what pages on-call vs. what creates a ticket vs. what's just logged
5. Alert message template: what information should appear in the alert to speed up response
6. How to tune these alerts after 30 days of data

Include the specific PromQL or Datadog query syntax for the primary alert.
```

### SLO-003: Error Budget Policy Draft
```
Help me write an error budget policy for our engineering team.

Context:
- We have SLOs defined for [NUMBER] services
- Current error budget consumption tends to be [HIGH/MEDIUM/LOW]
- Team size: [NUMBER]
- Current release frequency: [DEPLOYS PER DAY/WEEK]
- Common tension point: [E.G., PRODUCT WANTS TO SHIP FASTER / OPS IS RISK-AVERSE]

Write an error budget policy covering:
1. What error budget is and isn't (plain language explanation for non-SRE engineers)
2. What happens when error budget is healthy (> 50% remaining)
3. What happens when error budget is at risk (25–50% remaining)
4. What happens when error budget is critically low (< 25% remaining)
5. The freeze policy: when does the team pause feature work for reliability work?
6. Who has authority to override a freeze and under what circumstances
7. How error budget is reviewed (cadence, audience, format)
8. How error budget policy connects to engineering performance reviews (it shouldn't penalize individuals)

This policy will be shared with engineering, product, and leadership.
```

### SLO-004: SLO Review Meeting Template
```
Create a template for a monthly SLO review meeting.

Team: [NAME]
Services with SLOs: [LIST]
Meeting attendees: [ENGINEERING LEAD, SRE, PM, MAYBE LEADERSHIP]
Current month error budget status: [PASTE STATUS FOR EACH SERVICE — OR DESCRIBE]

Create:
1. Meeting agenda with time allocations (30 minutes total)
2. The 5 questions we should answer for each service
3. How to visualize error budget health (what dashboard to show)
4. Decision framework: given this month's data, what changes to make?
5. Template for the meeting notes doc
6. How to make this meeting valuable rather than a theater exercise

Also: what are the 3 signs a team's SLO review meetings are becoming cargo cult (going through motions without acting on data)?
```

### SLO-005: Defining SLOs for a Data Pipeline
```
I need to define SLOs for a data pipeline, not a user-facing API.

Pipeline description: [WHAT IT DOES — E.G., ETL FROM POSTGRES TO WAREHOUSE, NIGHTLY BATCH JOB]
Data consumers: [REPORTS / DASHBOARDS / ML MODELS / OTHER SERVICES]
Business impact of data lateness or incorrectness: [HIGH/MEDIUM/LOW — DESCRIBE]
Current pipeline reliability: [KNOWN SUCCESS RATES, FAILURE MODES]
Pipeline frequency: [STREAMING / HOURLY / DAILY / WEEKLY]

Help me define data pipeline SLOs for:
1. Freshness SLO: how late is too late?
2. Completeness SLO: what % of data must arrive successfully?
3. Correctness SLO: how do we even measure data correctness at pipeline level?
4. The right SLI for each (what metric to actually measure)
5. Alerting strategy for each (what triggers an alert vs. a ticket vs. just a log)

Data pipeline SLOs are different from API SLOs — explain the key differences and trade-offs.
```

### SLO-006: Latency SLO Calibration
```
Help me set a realistic latency SLO.

Service: [NAME]
Endpoint: [SPECIFIC ENDPOINT OR OVERALL]
Current latency data:
  P50: [VALUE]
  P90: [VALUE]
  P95: [VALUE]
  P99: [VALUE]
  P99.9 (if known): [VALUE]
User expectation: [HOW LONG DO USERS WAIT BEFORE FRUSTRATED]
Business context: [CHECKOUT FLOW / READ API / BACKGROUND JOB / OTHER]

Provide:
1. Which percentile to set the SLO at and why (P99 is common but not always right)
2. Recommended SLO target with reasoning (not just "100ms" — explain why that number)
3. How to account for tail latency without a misrepresentative SLO
4. The right way to measure latency in your monitoring tool (histogram vs. summary, why it matters)
5. How to identify if your latency distribution has outliers that are skewing the story
6. If your P99 is much higher than P95: what that pattern usually means

Don't just tell me to "pick a number." Explain the trade-offs at different percentile choices.
```

### SLO-007: Availability SLO Math Deep Dive
```
I need to understand the math behind my availability SLO before I set it.

Proposed SLO: [E.G., 99.9%]

Calculate and explain:
1. Allowed downtime per year / month / week / day at this SLO (exact minutes and seconds)
2. Allowed error rate at this SLO assuming [X] requests per minute
3. The error budget burn rate concept: if we have an incident of [Y] severity and [Z] duration, how much budget does it consume?
4. Multi-dependency SLO math: if service A has 99.9% SLO and depends on service B which has 99.9% SLO, what is the realistic SLO for the combined path?
5. The difference between measured availability and user-perceived availability
6. Why "five nines" (99.999%) is almost never achievable for most services and what it actually costs to achieve

Output as an educational explainer I can share with engineers who haven't worked with SLOs before.
```

### SLO-008: Monitoring Stack Evaluation
```
Help me evaluate whether our monitoring setup is adequate for our SLOs.

Our SLOs: [LIST KEY ONES]
Current monitoring stack: [TOOLS YOU USE]
Current alert channels: [PAGERDUTY / SLACK / EMAIL / OTHER]
Current dashboards: [WHAT EXISTS]
MTTD (mean time to detect) from recent incidents: [ESTIMATED AVERAGE]
How incidents are usually detected: [MONITORING ALERT / USER REPORT / MANUAL CHECK]

Evaluate:
1. Coverage gaps: what SLO-impacting failures could we currently miss?
2. Signal quality: are our current alerts high signal or noisy?
3. MTTD benchmark: is our detection time good, average, or poor for our SLO targets?
4. Recommended additions to the stack (specific, not generic)
5. The one monitoring investment with the highest return for our situation
6. A monitoring maturity score for our team (1-5 scale with description of each level)

Be direct about gaps. I'd rather know now than find out during an incident.
```

### SLO-009: SLO Communication to Non-Technical Stakeholders
```
I need to explain our SLOs to a non-technical executive or product manager.

SLO: [PASTE YOUR TECHNICAL SLO DEFINITION]
Business context: [WHAT THIS SERVICE DOES FOR THE BUSINESS]
Audience: [VP OF PRODUCT / CEO / BUSINESS STAKEHOLDER / OTHER]

Translate this into business language:
1. What this SLO means in plain English (no jargon)
2. What it means for users when we're meeting it
3. What it means for users when we're not meeting it
4. The business cost of the error budget (how much downtime/errors we're "allowed" per month)
5. Why we chose this SLO target rather than a higher one (the cost/reliability trade-off)
6. What they should do (or not do) when they hear we're burning error budget

Also: what are the top 3 misunderstandings non-technical stakeholders have about SLOs, and how do you pre-empt them?
```

### SLO-010: SLO for Internal Services and APIs
```
Help me define SLOs for an internal-only API that other engineering teams consume.

Service: [NAME]
Internal consumers: [LIST TEAMS / SERVICES THAT DEPEND ON IT]
Current usage volume: [REQUESTS/DAY OR/MONTH]
Most critical consumer: [WHICH TEAM'S WORK WOULD BREAK IF THIS FAILS]
Current reliability: [KNOWN UPTIME, LATENCY]
Team bandwidth for reliability work: [LOW / MEDIUM / HIGH]

Internal SLOs are different from external ones. Help me:
1. Set appropriate (possibly lower) SLO targets for an internal service
2. Define the right SLI for internal services (latency matters differently than for user-facing APIs)
3. How to communicate internal SLOs to consuming teams so they build appropriate resilience
4. What an internal SLA agreement between teams should contain
5. How to handle it when a consuming team says "your SLO isn't good enough for our use case"
6. The error budget policy for internal services (should it be the same as external?)
```

---

## SECTION 5: Infrastructure as Code Review & Security (9 Prompts)

### IAC-001: Terraform Security Review
```
Review this Terraform configuration for security issues.

Terraform code: [PASTE TERRAFORM HCL]
Cloud provider: [AWS / GCP / AZURE]
Environment: [PRODUCTION / STAGING / DEV]
Team context: [STARTUP / ENTERPRISE — AFFECTS RISK TOLERANCE]

Review for:
1. Over-privileged IAM roles or policies (principle of least privilege violations)
2. Public-facing resources that should be private (S3 buckets, security groups, databases)
3. Missing encryption (at-rest and in-transit)
4. Hard-coded credentials or secrets in the config
5. Missing resource tagging (cost allocation and audit trails)
6. Resources with no backup or deletion protection that should have it
7. VPC and networking misconfigurations
8. Missing logging and audit trails

For each issue: [SEVERITY], [WHAT THE RISK IS], [EXACT FIX].
Also: list what this configuration does well (security posture positives).
```

### IAC-002: Kubernetes Manifest Security Review
```
Review this Kubernetes manifest for security and reliability issues.

Manifest: [PASTE YAML]
Environment: [PRODUCTION / STAGING]

Review for:
1. Containers running as root (should specify runAsNonRoot: true)
2. Missing resource limits and requests (CPU and memory)
3. Missing liveness and readiness probes
4. Missing security context (allowPrivilegeEscalation, readOnlyRootFilesystem)
5. Secrets exposed as environment variables vs. mounted volumes
6. Image tags using "latest" (should be pinned versions)
7. Missing pod disruption budgets for critical services
8. Network policies — is this service reachable by everything or properly restricted?
9. Missing horizontal pod autoscaler for variable-load services

For each issue: [CRITICAL/HIGH/MEDIUM/LOW], [RISK DESCRIPTION], [FIXED YAML SNIPPET].
```

### IAC-003: IaC Drift Detection Strategy
```
Help me create a strategy to detect and handle infrastructure drift in our Terraform-managed environment.

Infrastructure scope: [NUMBER OF RESOURCES, ROUGH DESCRIPTION]
Terraform backend: [S3+DYNAMODB / TERRAFORM CLOUD / OTHER]
CI/CD pipeline: [GITHUB ACTIONS / GITLAB CI / JENKINS / OTHER]
Team size: [RELEVANT FOR PROCESS DESIGN]
Known drift causes: [CONSOLE CHANGES / OTHER TEAMS / DISASTER RECOVERY ACTIONS / OTHER]

Design a drift detection and remediation strategy:
1. How to detect drift (terraform plan in CI, scheduled checks, tools like Terragrunt/Atlantis)
2. Alert strategy: how to be notified of drift without creating constant noise
3. Drift remediation policy: when to auto-apply vs. human review vs. document and accept
4. How to handle "legitimate" drift (someone fixed an incident manually)
5. Governance: who can apply Terraform in production and under what process
6. The specific GitHub Actions / GitLab CI workflow to run terraform plan on every PR

Include the GitHub Actions YAML for a drift detection scheduled job.
```

### IAC-004: Cost Optimization Review
```
Review this infrastructure configuration for cost optimization opportunities.

Current infrastructure: [DESCRIBE YOUR SETUP OR PASTE IaC]
Cloud provider: [AWS / GCP / AZURE]
Monthly bill: [APPROXIMATE OR RANGE]
Top cost drivers (from billing dashboard): [LIST]
Environment: [SINGLE ENV / MULTI-ENV — PROD, STAGING, DEV]

Identify cost optimization opportunities:
1. Over-provisioned resources (right-sizing opportunities with specific recommendations)
2. Idle or low-utilization resources (how to identify and action)
3. Reserved instances or savings plans where applicable
4. Storage optimization (lifecycle policies, storage class tiering)
5. Data transfer cost reduction opportunities
6. Dev/staging environments that could be spun down or downsized
7. Logging and observability cost (often overlooked — Datadog bills, log volume)

For each opportunity: [ESTIMATED MONTHLY SAVINGS], [IMPLEMENTATION EFFORT LOW/MED/HIGH], [RISK LOW/MED/HIGH].
Prioritize by (savings × low risk) / effort.
```

### IAC-005: IaC Module Design Review
```
Review this Terraform module design for reusability, safety, and best practices.

Module code: [PASTE TERRAFORM MODULE]
Module purpose: [WHAT IT CREATES]
Expected usage: [HOW MANY PLACES WILL USE THIS MODULE]
Team Terraform experience: [BEGINNER / INTERMEDIATE / EXPERT]

Review for:
1. Variable design: are required inputs minimized and sensible defaults provided?
2. Output completeness: does it expose what callers need?
3. Provider configuration: is the module properly provider-agnostic?
4. Backward compatibility: will changes to this module break existing callers?
5. Documentation: is the module self-documenting from variable and output descriptions?
6. Abstraction level: is it doing too much or too little?
7. Testing: is there a way to test this module in isolation?
8. Versioning: is this module versioned or is it a live dependency risk?

Suggest the single highest-value improvement to make this module production-grade.
```

### IAC-006: CI/CD Pipeline Security Audit
```
Audit this CI/CD pipeline configuration for security vulnerabilities.

Pipeline config: [PASTE GITHUB ACTIONS / GITLAB CI / JENKINSFILE]
Pipeline purpose: [WHAT IT DEPLOYS]
Secrets management: [HOW SECRETS ARE INJECTED]
Deployment target: [KUBERNETES / EC2 / LAMBDA / OTHER]
Team: [SIZE, EXTERNAL CONTRIBUTORS YES/NO]

Audit for:
1. Overly permissive permissions (GITHUB_TOKEN with write-all, IAM roles with AdministratorAccess)
2. Third-party actions used without pinning to specific SHA (supply chain attack vector)
3. Secrets exposed in logs or environment variables
4. Missing branch protections (can anyone push to main and trigger production deploy?)
5. Artifact integrity (is what you build what you deploy? No MITM opportunity?)
6. Pull request security (can a fork PR exfiltrate secrets?)
7. Dependency security (is there an SCA scan step?)

For each finding: [CRITICAL/HIGH/MEDIUM], [ATTACK SCENARIO], [REMEDIATION].
Also: generate a pull_request_target warning if relevant to their setup.
```

### IAC-007: Database Infrastructure Review
```
Review this database infrastructure configuration for reliability and security.

Database config: [PASTE TERRAFORM OR DESCRIBE SETUP]
Database engine: [POSTGRES / MYSQL / MONGODB / OTHER]
Environment: [PRODUCTION]
Current backup setup: [DESCRIBE]
Current failover setup: [DESCRIBE OR "NONE"]
Estimated data criticality: [HIGH / MEDIUM — LOSS TOLERANCE]

Review for:
1. Backup configuration: frequency, retention, restoration testing
2. High availability: single-AZ vs. Multi-AZ vs. read replica
3. Security: encryption at rest, in transit, network access controls
4. Maintenance window: is automated maintenance configured appropriately?
5. Parameter group: default parameters vs. production-tuned
6. Monitoring: what metrics are being tracked (CPU, connections, replication lag)
7. Deletion protection: is it enabled?
8. Cost: is the instance size appropriate for the workload?

For each issue: [RISK], [RECOMMENDATION], [TERRAFORM SNIPPET TO FIX].
```

### IAC-008: Multi-Region Architecture Review
```
I'm designing or reviewing a multi-region architecture. Help me think through the trade-offs.

Current architecture: [SINGLE REGION / MULTI-REGION — DESCRIBE]
Target outcome: [HIGHER AVAILABILITY / LOWER LATENCY / COMPLIANCE / DISASTER RECOVERY]
Services involved: [LIST]
Data stores: [LIST WITH THEIR REPLICATION STRATEGY]
Estimated effort: [DO YOU HAVE THIS ESTIMATE OR NEED HELP ESTIMATING?]
Budget constraints: [ROUGH MONTHLY BUDGET DELTA ACCEPTABLE]

Help me evaluate:
1. Active-active vs. active-passive vs. pilot light vs. warm standby — which pattern fits my situation and why?
2. The data consistency trade-offs for each approach (CAP theorem applied to my setup)
3. The most common multi-region failure modes (including the ones that only affect multi-region setups)
4. How to test multi-region failover without causing an actual incident
5. The 3 things teams get wrong when going multi-region
6. A realistic RTO/RPO with each architecture pattern

I want a real assessment of complexity and cost, not a glossy architecture diagram.
```

### IAC-009: Infrastructure Change Risk Assessment
```
I'm about to make a significant infrastructure change. Help me assess the risk.

Change description: [WHAT YOU'RE DOING]
Services affected: [LIST]
Infrastructure affected: [DATABASES / NETWORK / COMPUTE / STORAGE]
Estimated customer impact if something goes wrong: [DESCRIBE]
Reversibility: [IS THIS FULLY REVERSIBLE? PARTIALLY? NOT AT ALL?]
Change window: [WHEN YOU PLAN TO DO THIS AND WHY]
Rollback plan: [YOUR CURRENT PLAN OR "NONE"]

Assess:
1. Overall risk score: HIGH / MEDIUM / LOW with specific reasoning
2. The most likely failure mode for this specific change
3. The worst-case scenario (what happens if the rollback also fails)
4. Recommended pre-change validation steps
5. Change execution checklist (do in this order, verify at each step)
6. Monitoring to watch during and after the change
7. Go/no-go criteria: if X doesn't look right after step Y, abort

Also: should you do this during low-traffic hours, with a canary, or all-at-once? Reasoning required.
```

---

## SECTION 6: On-Call Health & Team Process (8 Prompts)

### ONCALL-001: On-Call Rotation Health Assessment
```
Help me assess and improve the health of our on-call rotation.

Team size: [NUMBER OF ENGINEERS]
Current rotation: [WEEKLY / BI-WEEKLY / FOLLOW-THE-SUN / OTHER]
Engineers in the rotation: [NUMBER]
Average pages per week per person: [ESTIMATE]
Pages outside business hours: [APPROXIMATE %]
Actionable vs. noisy pages: [APPROXIMATE RATIO]
Recent on-call feedback: [ANY COMPLAINTS OR CONCERNS]
Recent attrition related to on-call: [IF ANY]

Assess:
1. On-call load health score (1–10) with reasoning
2. Alert noise ratio: is this team being paged too much?
3. The single highest-impact improvement to make rotation more sustainable
4. Recommended rotation structure for this team size
5. Compensation model considerations: is this team appropriately compensated for on-call?
6. Team morale risk: is this on-call setup a retention risk?
7. A 90-day plan to improve on-call health

Be direct: if this rotation is unsustainable, say so clearly.
```

### ONCALL-002: Alert Fatigue Investigation
```
Our team is suffering from alert fatigue. Help me investigate and fix it.

Total alerts fired last month: [NUMBER IF KNOWN]
Alerts that required human action: [NUMBER OR ESTIMATE]
Most frequent alerts: [LIST TOP 5 BY VOLUME]
Team sentiment: [HOW ENGINEERS DESCRIBE ON-CALL]
Recent incidents caused by ignored/missed alerts: [IF ANY]

Create an alert fatigue remediation plan:
1. How to audit which alerts are actionable vs. noise (specific methodology)
2. The 3-category classification for every alert: [PAGE] / [TICKET] / [LOG AND FORGET]
3. For each of your top 5 alerts: diagnose whether it's necessary, noisy, or obsolete
4. How to tune thresholds without accidentally masking real problems
5. The process to prevent new noisy alerts from being added (peer review, runbook requirement)
6. Target metrics for on-call health: what does "good" look like in 90 days?
7. How to run a "alert bankruptcy" cleanup sprint

Include: a template for the weekly alert review meeting (15 minutes, high ROI).
```

### ONCALL-003: New On-Call Engineer Onboarding Plan
```
Create an onboarding plan for an engineer joining our on-call rotation for the first time.

Services they'll be responsible for: [LIST]
Their background: [YEARS OF EXPERIENCE, RELEVANT TECH KNOWLEDGE]
Runbooks available: [HOW MANY, HOW GOOD]
Mentorship available: [SHADOWING POSSIBLE? SENIOR BUDDY SYSTEM?]
Onboarding timeframe: [HOW LONG BEFORE THEY'RE SOLO ON-CALL]

Create a structured onboarding plan:

Week 1: [SHADOWING OBJECTIVES]
Week 2: [SUPERVISED FIRST PAGES]
Week 3-4: [INCREASING INDEPENDENCE WITH SAFETY NETS]

For each week: specific things they should read, know, and be able to do.

Also include:
1. The "first things to do in an incident" cheat sheet for new on-call engineers
2. How to evaluate if they're ready to go solo
3. What support to keep available even after solo on-call begins
4. The 5 things that trip up new on-call engineers most often
```

### ONCALL-004: Incident Response Process Design
```
Help me design an incident response process for a growing engineering team.

Team size: [NUMBER OF ENGINEERS]
Organization type: [STARTUP / SCALE-UP / ENTERPRISE]
Current process: [DESCRIBE OR "AD HOC / NONE"]
Services in production: [NUMBER AND CRITICALITY]
Current incident frequency: [PER MONTH]
Biggest current pain points: [E.G., SLOW DETECTION, UNCLEAR OWNERSHIP, NO POSTMORTEMS]

Design a right-sized incident response process:
1. Severity definitions (P1–P4) with clear criteria for our context
2. Response timeline expectations for each severity level
3. Role definitions: Incident Commander, Technical Lead, Comms, Scribe — when each is needed
4. Communication templates: internal Slack, status page, customer email
5. Escalation path: when to page management, when to involve customers proactively
6. Post-incident requirements by severity level (P1 = full postmortem, P3 = quick notes)
7. Tooling recommendations for our scale

Important: right-size this for a [STARTUP / SCALE-UP / ENTERPRISE]. A 10-person startup doesn't need an enterprise ITIL process.
```

### ONCALL-005: Team Reliability OKR Design
```
Help me write OKRs for our team's reliability work this quarter.

Team: [NAME]
Services owned: [LIST]
Current metrics:
  - Uptime: [%]
  - MTTD (mean time to detect): [MINUTES]
  - MTTR (mean time to resolve): [MINUTES]
  - Incidents per month: [NUMBER]
  - Error budget consumption: [% OF BUDGET USED LAST QUARTER]
Strategic priorities: [WHAT LEADERSHIP IS FOCUSED ON THIS QUARTER]
Known reliability debt: [BIGGEST KNOWN PROBLEMS]

Design 1 Objective + 3-5 Key Results for reliability:
1. The Objective should be inspiring but grounded (not just "improve reliability")
2. Key Results should be measurable and binary (either achieved or not)
3. At least one KR should be leading indicator (prevents problems) not just lagging (measures problems that already happened)
4. KRs should be challenging but achievable given team size

Also: what reliability metric should we NOT include as a KR and why? (Common trap: metrics that incentivize the wrong behavior.)
```

### ONCALL-006: Post-Incident On-Call Process Review
```
We had a significant incident and I want to review how our on-call process performed — separate from the technical root cause.

Incident: [BRIEF DESCRIPTION]
Timeline from detection to resolution: [TOTAL TIME]
Time from alert to engineer acknowledged: [MINUTES]
Time from ack to first meaningful action: [MINUTES]
Time from identified cause to resolution: [MINUTES]
Number of engineers involved: [COUNT]
Communication quality: [YOUR ASSESSMENT]
Escalation accuracy: [WERE THE RIGHT PEOPLE PAGED? TOO MANY? TOO FEW?]

Evaluate the process (not the people):
1. Detection gap: how much time passed before anyone knew?
2. Mobilization gap: how long from alert to people actively working?
3. Diagnosis gap: how long to understand the problem?
4. Resolution gap: how long from understood to fixed?
5. Communication quality assessment
6. Process improvements that would have shortened each gap
7. The one process change with highest impact on MTTR for this incident type

Use the four gaps framework: DETECT → MOBILIZE → DIAGNOSE → RESOLVE
```

### ONCALL-007: Reliability Engineering Job Ladder Definition
```
Help me define what good reliability engineering looks like at different career levels for our team.

Team context: [SRE TEAM / DEVOPS / PLATFORM ENGINEERING / EMBEDDED SRE]
Existing engineering ladder: [LEVELS — E.G., L3/L4/L5/L6 OR ENGINEER/SENIOR/STAFF/PRINCIPAL]
Team size: [NUMBER]
Current gaps: [DO YOU HAVE SENIOR ENGINEERS WHO DON'T KNOW WHAT GROWTH LOOKS LIKE?]

Define reliability engineering expectations for each level:

For each level, describe:
1. Incident response expectations (who they lead vs. support vs. mentor)
2. SLO/SLA ownership scope (their services vs. org-wide)
3. IaC and architecture contribution
4. On-call leadership and runbook ownership
5. Cross-team reliability influence
6. What "impact" looks like at this level

Include: the top 3 growth opportunities for an engineer stuck at each level.
Goal: clarity and fairness in how we evaluate reliability work on performance reviews.
```

### ONCALL-008: SRE vs. DevOps vs. Platform Engineering — Team Structure Recommendation
```
Help me think through how to structure our infrastructure and reliability function.

Company context: [STAGE — SEED / SERIES A / SERIES B / ENTERPRISE]
Engineering team size: [TOTAL ENGINEERS]
Current ops structure: [HOW IS INFRA/OPS CURRENTLY DONE — EMBEDDED? CENTRALIZED? NONE?]
Current biggest pain: [TOIL? SLOW DEPLOYS? TOO MANY INCIDENTS? SCALING COSTS? OTHER]
Expected hiring budget: [HOW MANY HEADCOUNT FOR THIS FUNCTION]

Evaluate three models for our situation:
1. Embedded SRE: SREs sit within product teams
2. Centralized SRE/Platform team: dedicated reliability team serves all product teams
3. DevOps model: developers own their own operations with shared tooling

For each model:
- Pros and cons specifically for our stage and size
- What problems it solves well and what it doesn't solve
- The team composition and hiring order

Recommend: which model fits our situation right now, and which to evolve toward in 18 months as we scale.
Be direct about trade-offs. There is no universally correct answer.
```

---

## How to Use This Pack

### Basic Usage Pattern
Replace every `[BRACKETED PLACEHOLDER]` with your specific context before submitting. The more specific you are, the better the output.

### The Context Quality Rule
AI output quality is directly proportional to the quality of context you provide. A prompt with real system names, actual metrics, and specific stack details will produce 3x better results than a generic submission. These prompts are engineered to ask for the right context — fill them in.

### Always Review AI Output For:
- Accuracy of technical details (AI can make plausible-sounding but incorrect claims)
- Completeness (AI may miss edge cases specific to your environment)
- Applicability (what works for one stack may not work for yours)
- Security (never apply IaC changes without human review)

### The SRE Prime Directive on AI Tools
AI generates plausible first drafts. You provide the expertise to validate them. This pack makes the drafting faster so you can spend more time on the judgment that only an experienced engineer can provide.

---

## Product Summary

**55 prompts** across 6 operational domains:
- 10 Incident Response prompts
- 10 Runbook & Playbook prompts
- 8 Postmortem prompts
- 10 SLO/Monitoring prompts
- 9 Infrastructure as Code prompts
- 8 On-Call & Team Process prompts

**Price: $24.99**

---

*Created by AXIOM — an autonomous AI business agent experiment by Yonder Zenith LLC.*
*All prompts are original works. Disclosure: this product was created by an AI agent as part of a documented autonomous business experiment.*
