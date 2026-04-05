# The Developer Productivity AI Prompt Pack

**50 Expert-Level Prompts for Professional Software Developers**

*Version 1.0 | Created by AXIOM*

---

## How to Use This Pack

1. Find the prompt that matches your task
2. Replace all `[PLACEHOLDERS]` with your specific context
3. Paste into any AI assistant (Claude, ChatGPT, Copilot, Gemini)
4. Iterate on the output as needed

The more context you provide in the placeholders, the better the output.

---

## Category 1: Code Review & Quality

### 1. Deep Bug Hunter

> Review this [LANGUAGE] code for bugs, including: off-by-one errors, null/undefined access, race conditions, resource leaks, integer overflow, and incorrect boundary handling. For each bug found, show the exact line, explain why it's a bug, rate severity (critical/high/medium/low), and provide the fixed code.
>
> ```[LANGUAGE]
> [YOUR_CODE_HERE]
> ```

**Use case:** Find hidden bugs before they reach production.

---

### 2. Security Vulnerability Scanner

> Perform a security audit on this [LANGUAGE] code. Check for: injection vulnerabilities (SQL, command, XSS), authentication/authorization flaws, sensitive data exposure, insecure deserialization, broken access control, SSRF, path traversal, and hardcoded secrets. For each finding, cite the OWASP category, show the vulnerable line, explain the attack vector, and provide a secure alternative.
>
> ```[LANGUAGE]
> [YOUR_CODE_HERE]
> ```

**Use case:** Security review before merging sensitive code.

---

### 3. Performance Profiler

> Analyze this [LANGUAGE] code for performance issues. Identify: O(n^2) or worse algorithms that could be optimized, unnecessary allocations, N+1 query patterns, missing caching opportunities, blocking operations that should be async, redundant computations, and memory leaks. For each issue, estimate the impact (high/medium/low), explain the bottleneck, and show the optimized version.
>
> ```[LANGUAGE]
> [YOUR_CODE_HERE]
> ```
>
> Context: This code handles approximately [EXPECTED_LOAD] requests/records per [TIME_PERIOD].

**Use case:** Optimize slow code paths before scaling.

---

### 4. Refactoring Advisor

> Suggest refactoring improvements for this [LANGUAGE] code. Focus on: extracting methods/functions longer than 20 lines, reducing cyclomatic complexity, eliminating code duplication, improving naming clarity, applying appropriate design patterns, reducing coupling between components, and simplifying conditional logic. For each suggestion, show before/after code and explain why the refactoring improves maintainability.
>
> ```[LANGUAGE]
> [YOUR_CODE_HERE]
> ```

**Use case:** Clean up code before it becomes tech debt.

---

### 5. Code Smell Detector

> Identify code smells in this [LANGUAGE] codebase excerpt. Check for: God classes/functions, feature envy, data clumps, primitive obsession, shotgun surgery patterns, inappropriate intimacy between modules, refused bequest, and speculative generality. For each smell, name it, show where it occurs, explain why it's problematic, and propose a specific fix.
>
> ```[LANGUAGE]
> [YOUR_CODE_HERE]
> ```

**Use case:** Identify structural problems during code review.

---

### 6. Error Handling Auditor

> Audit the error handling in this [LANGUAGE] code. Identify: swallowed exceptions, overly broad catch blocks, missing error cases, error messages that leak internal details, inconsistent error response formats, missing retry logic for transient failures, and unhandled promise rejections or async errors. Provide corrected error handling for each issue.
>
> ```[LANGUAGE]
> [YOUR_CODE_HERE]
> ```

**Use case:** Harden error handling before production deployment.

---

### 7. Dependency Risk Assessor

> Analyze this dependency list and assess risk for each dependency:
>
> ```
> [PASTE_PACKAGE_JSON_OR_REQUIREMENTS_TXT]
> ```
>
> For each dependency, evaluate: maintenance status, security history, bundle size impact, transitive dependencies, license compatibility with [YOUR_LICENSE], and whether a lighter alternative exists. Flag any dependency that is unmaintained (>12 months since last release) or has known vulnerabilities.

**Use case:** Audit dependencies before major version upgrades.

---

### 8. Type Safety Improver

> Improve the type safety of this [LANGUAGE] code. Identify: uses of `any`/`object`/`dynamic` that could be narrowed, missing null checks, implicit type coercions, union types that should be discriminated, generic functions that should have constraints, and places where branded/opaque types would prevent bugs. Show the improved typed version.
>
> ```[LANGUAGE]
> [YOUR_CODE_HERE]
> ```

**Use case:** Strengthen types in TypeScript/Java/C# codebases.

---

### 9. Concurrency Review

> Review this [LANGUAGE] code for concurrency issues. Check for: race conditions, deadlock potential, incorrect use of locks/mutexes, shared mutable state without synchronization, unsafe lazy initialization, thread-unsafe collection usage, and missing atomic operations. For each issue, explain the failure scenario, show when it could trigger in production, and provide the thread-safe fix.
>
> ```[LANGUAGE]
> [YOUR_CODE_HERE]
> ```

**Use case:** Review multi-threaded or async code for safety.

---

### 10. API Contract Validator

> Compare this API implementation against its contract and identify mismatches:
>
> API Specification:
> ```
> [PASTE_OPENAPI_SPEC_OR_INTERFACE]
> ```
>
> Implementation:
> ```[LANGUAGE]
> [YOUR_CODE_HERE]
> ```
>
> Check for: missing endpoints, incorrect response shapes, missing required fields, wrong HTTP status codes, undocumented error responses, missing input validation, and inconsistent naming.

**Use case:** Verify implementation matches API contract.

---

## Category 2: Architecture & Design

### 11. System Design Reviewer

> Review this system architecture and identify weaknesses:
>
> [DESCRIBE_YOUR_SYSTEM: components, data flow, storage, APIs, external services]
>
> Evaluate: single points of failure, scalability bottlenecks, data consistency risks, security boundaries, operational complexity, cost efficiency, and disaster recovery gaps. For each weakness, rate severity and propose a specific architectural change. Assume the system needs to handle [EXPECTED_SCALE] with [AVAILABILITY_TARGET] uptime.

**Use case:** Architecture review before major launches or redesigns.

---

### 12. API Design Critic

> Critique this API design and suggest improvements:
>
> ```
> [PASTE_API_ENDPOINTS_OR_OPENAPI_SPEC]
> ```
>
> Evaluate against: REST best practices, consistency, pagination strategy, versioning approach, error response format, authentication model, rate limiting design, and developer experience. Propose a revised API design for any endpoints that need improvement.

**Use case:** Polish API design before publishing to consumers.

---

### 13. Database Schema Optimizer

> Review this database schema and optimize it:
>
> ```sql
> [YOUR_SCHEMA_HERE]
> ```
>
> Query patterns this schema must support:
> [LIST_YOUR_COMMON_QUERIES]
>
> Evaluate: normalization level, missing indexes, data types, missing constraints, and potential for query performance issues at scale. Provide the optimized schema with CREATE INDEX statements.

**Use case:** Optimize schema before data migration or launch.

---

### 14. Microservices Boundary Analyzer

> We have a [MONOLITH/MODULAR_MONOLITH] with these domains:
>
> [LIST_YOUR_DOMAINS_AND_THEIR_RESPONSIBILITIES]
>
> Data dependencies: [DESCRIBE_WHICH_DOMAINS_SHARE_DATA]
>
> Analyze where the service boundaries should be drawn. For each proposed service, specify: bounded context, owned data, API surface, event contracts, and deployment independence. Recommend which boundaries to split first.

**Use case:** Plan microservice extraction from a monolith.

---

### 15. Scalability Stress Test Designer

> Design a scalability analysis for this system:
>
> [DESCRIBE_YOUR_SYSTEM_ARCHITECTURE]
> Current load: [CURRENT_METRICS] | Target load: [TARGET_METRICS]
>
> For each component, identify: theoretical throughput limit, first bottleneck under load, scaling strategy, required infrastructure changes, estimated cost at target load, and monitoring metrics. Create a load test plan.

**Use case:** Prepare for 10x traffic growth.

---

### 16. Event-Driven Architecture Planner

> Convert this synchronous workflow into an event-driven architecture:
>
> Current flow: [DESCRIBE_STEP_BY_STEP_WORKFLOW]
>
> Design: event names and schemas, producer/consumer relationships, ordering guarantees, idempotency requirements, dead letter queue strategy, retry policies, and saga patterns.

**Use case:** Migrate from synchronous to event-driven patterns.

---

### 17. Caching Strategy Designer

> Design a caching strategy for this system:
>
> [DESCRIBE_YOUR_APPLICATION_AND_DATA_ACCESS_PATTERNS]
> Hot paths: [LIST_THEM] | Write frequency: [DESCRIBE] | Acceptable staleness: [PER_DATA_TYPE]
>
> For each data type, recommend: cache layer, key structure, TTL, invalidation strategy, warming approach, and thundering herd prevention.

**Use case:** Design caching before performance optimization.

---

### 18. Data Migration Planner

> Plan a zero-downtime data migration:
>
> Current schema: ```sql [CURRENT] ``` | Target: ```sql [TARGET] ```
> Constraints: [UPTIME], [DATA_VOLUME], [WRITE_TRAFFIC]
>
> Design a phased plan with: DDL changes, dual-write strategy, backfill queries, validation queries, rollback procedure, and estimated duration per phase.

**Use case:** Plan database migrations with zero downtime.

---

### 19. Authentication Architecture Review

> Review this auth architecture:
>
> [DESCRIBE: auth flow, token types, session management, permission model, identity provider]
>
> Evaluate: token security, session risks, privilege escalation paths, OAuth/OIDC correctness, CORS policy, CSRF protection, and multi-tenancy isolation. Provide a revised architecture.

**Use case:** Security review of auth system before audit.

---

### 20. Technology Decision Record Writer

> Write an ADR for: [WHAT_WE_ARE_DECIDING]
> Context: [WHY_NOW] | Options: [LIST_OPTIONS] | Constraints: [TEAM, BUDGET, TIMELINE, STACK]
>
> Write: Title, Status, Context, Decision, Alternatives Considered (pros/cons each), Consequences, and Compliance Notes. Be balanced — show genuine tradeoffs.

**Use case:** Document architectural decisions for the team.

---

## Category 3: Testing & Debugging

### 21. Comprehensive Test Generator

> Generate a complete test suite for this [LANGUAGE] function/class using [TEST_FRAMEWORK]:
>
> ```[LANGUAGE]
> [YOUR_CODE_HERE]
> ```
>
> Include: happy path, edge cases (empty, null, boundary), error cases, concurrency tests if applicable. Each test named: 'should [behavior] when [condition]'. Aim for >90% branch coverage.

**Use case:** Generate thorough tests for new or untested code.

---

### 22. Root Cause Analyzer

> Symptom: [WHAT_IS_HAPPENING] | Expected: [WHAT_SHOULD_HAPPEN]
> Reproduction: [STEPS_OR_FREQUENCY] | Environment: [LANGUAGE, FRAMEWORK, VERSIONS]
> Code: ```[LANGUAGE] [CODE] ``` | Recent changes: [DEPLOYMENTS/CONFIG] | Logs: [RELEVANT_LOGS]
>
> Walk through possible causes from most to least likely. For each: what would cause this, how to confirm/rule it out, and the fix if confirmed.

**Use case:** Systematic debugging of hard-to-find bugs.

---

### 23. Edge Case Discovery

> Analyze this function and enumerate every edge case:
>
> ```[LANGUAGE]
> [YOUR_CODE_HERE]
> ```
>
> Consider: boundary values, empty/null, Unicode, concurrency, timezones, locales, integer overflow, floating point, file permissions, network timeouts, resource exhaustion. For each: input, expected behavior, and why it matters.

**Use case:** Find edge cases you haven't thought of.

---

### 24. Flaky Test Investigator

> Test: ```[LANGUAGE] [TEST_CODE] ``` | Implementation: ```[LANGUAGE] [CODE] ```
> Fails: [HOW_OFTEN] | Error: [MESSAGE_WHEN_FAILING]
>
> Analyze: timing deps, shared state, ordering deps, external calls, date/time sensitivity, random data, race conditions, cleanup issues. Provide a concrete fix.

**Use case:** Fix intermittently failing tests.

---

### 25. Integration Test Designer

> Service depends on: [LIST_DATABASES, APIS, QUEUES, CACHES]
> Code: ```[LANGUAGE] [CODE] ```
>
> For each dependency: real vs. fake vs. mock (with justification). Write integration tests covering: happy path, failure modes, data consistency, and isolation.

**Use case:** Design integration tests for services with external dependencies.

---

### 26. Production Debugging Playbook

> Service: [NAME] | Symptom: [REPORT] | Impact: [SCOPE] | Start: [WHEN]
> Stack: [TECH] | Observability: [TOOLS]
>
> Write: triage (first 5 min), diagnostic queries, common root causes, mitigation options (ranked by speed), stakeholder comms, and post-incident items.

**Use case:** Structured response to production incidents.

---

### 27. Regression Test Prioritizer

> ```diff
> [YOUR_DIFF]
> ```
>
> Identify: (1) which tests are most likely to break, (2) ripple effect areas, (3) new tests needed, (4) manual testing priorities. Rank by risk. Focus on non-obvious downstream effects.

**Use case:** Prioritize testing effort after a code change.

---

### 28. Memory Leak Detective

> ```[LANGUAGE]
> [YOUR_CODE_HERE]
> ```
>
> Check: event listeners, closures retaining objects, caches without eviction, circular references, unclosed streams, unreleased connections, uncleared timers, growing static collections. For each: retention path, growth conditions, impact, and fix.

**Use case:** Find memory leaks before OOM crashes.

---

### 29. Load Test Scenario Builder

> API: [ENDPOINTS_AND_USAGE_PATTERNS]
> Target: [RPS], [CONCURRENT_USERS], [RESPONSE_TIME_SLA]
>
> Create: ramp-up profiles, user journey scripts, data generation, p50/p95/p99 assertions, and breakpoint test. Provide the [K6/LOCUST/GATLING] script.

**Use case:** Design load tests before benchmarking.

---

### 30. Error Reproduction Assistant

> User report: [BUG_REPORT] | Stack: [TECH] | User env: [BROWSER, OS]
> Code path: ```[LANGUAGE] [CODE] ```
>
> Create: minimal reproduction steps, a trigger test case, environment conditions to check, and questions for the user if reproduction fails.

**Use case:** Reproduce hard-to-trigger user-reported bugs.

---

## Category 4: Documentation & Communication

### 31. API Documentation Generator

> ```[LANGUAGE]
> [YOUR_ROUTE_HANDLERS]
> ```
>
> For each endpoint: method, path, description, auth, request params with types, response schemas (success + errors), curl example, rate limiting, and side effects.

**Use case:** Generate API docs from implementation code.

---

### 32. Technical Spec Writer

> Feature: [NAME] | Goal: [WHAT_AND_WHY] | Constraints: [TECH, TIMELINE, TEAM]
>
> Write: Overview, Goals & Non-Goals, Technical Design, Alternatives Considered, Security, Observability, Rollout Plan, Open Questions, Timeline.

**Use case:** Write specs for new features.

---

### 33. Code Comment Improver

> Remove comments restating code. Add comments explaining: non-obvious business logic, why an approach was chosen, gotchas, relevant ticket links, and performance constraints.
>
> ```[LANGUAGE]
> [YOUR_CODE_HERE]
> ```

**Use case:** Improve code documentation quality.

---

### 34. PR Description Writer

> ```diff
> [YOUR_DIFF]
> ```
> Context: [WHY] | Ticket: [NUMBER]
>
> Write: Summary, Motivation, Changes Made, Testing Done, Migration Notes, Rollback Plan, Checklist. A reviewer should understand the PR in 30 seconds.

**Use case:** Write clear PR descriptions quickly.

---

### 35. Incident Postmortem Writer

> Incident: [DESCRIPTION] | Duration: [START] to [END] | Impact: [SCOPE]
> Timeline: [EVENTS] | Root cause: [WHAT] | Fix: [HOW]
>
> Write: Summary, Impact, Timeline, Root Cause (5 Whys), Contributing Factors, Action Items (with owners), Lessons Learned. Blameless tone.

**Use case:** Write professional postmortems after incidents.

---

### 36. Runbook Creator

> Service: [NAME] | Purpose: [WHAT] | Dependencies: [EXTERNAL] | Infra: [WHERE]
>
> Cover: overview, architecture diagram (ASCII), health checks, alert responses, scaling, deployment, rollback, database ops, log queries, emergency contacts. Write for a new on-call engineer.

**Use case:** Create runbooks for on-call engineers.

---

### 37. Technical Blog Post Outliner

> Topic: [TOPIC] | Audience: [LEVEL] | Goal: [LEARNING_OUTCOME] | Your angle: [UNIQUE_INSIGHT]
>
> Create: SEO title, hook paragraph, section breakdown with key points, code example locations, misconceptions to address, actionable takeaways, CTA. Estimate word counts.

**Use case:** Plan technical content before writing.

---

### 38. Architecture Diagram Describer

> [DESCRIBE_SYSTEM_COMPONENTS_AND_DATA_FLOW]
>
> Generate a [MERMAID/ASCII/PLANTUML] diagram with: all components, databases, queues, external APIs, load balancers, data flow directions, protocols (HTTP, gRPC, SQL), and sync/async labels.

**Use case:** Generate architecture diagrams from descriptions.

---

### 39. Changelog Generator

> ```
> [GIT_LOG_OR_CHANGES]
> ```
> Product: [WHAT_IT_DOES] | Audience: [DEVS/USERS/BOTH] | Version: [NUMBER]
>
> Write Keep a Changelog format: Added, Changed, Deprecated, Removed, Fixed, Security. Translate commits to user-meaningful descriptions. Highlight breaking changes.

**Use case:** Generate changelogs from git history.

---

### 40. Onboarding Guide Builder

> Project: [NAME] | Stack: [TECH] | Structure: [DIRS] | Key concepts: [LIST] | Gotchas: [LIST]
>
> Cover: prerequisites, getting started, project structure, architecture decisions, dev workflow, tests, common tasks, debugging tips, who to ask, first issues. Target: productive in day one.

**Use case:** Create onboarding docs for new team members.

---

## Category 5: Productivity & Workflow

### 41. Sprint Planning Assistant

> Team: [DEVS] devs, [LENGTH] sprint | Carryover: [ITEMS] | Priorities: [LIST]
> Tech debt: [LIST] | Risks: [BLOCKERS]
>
> For each item: complexity (S/M/L/XL), dependencies, risk, assignee profile. Sprint plan with 20% buffer, feature/debt ratio, sequence, and ONE sprint goal.

**Use case:** Structure sprint planning sessions.

---

### 42. Tech Debt Prioritizer

> [LIST_TECH_DEBT_ITEMS]
>
> For each: pain frequency, blast radius, remediation cost, risk of inaction. Calculate debt score (pain x blast / cost). Quarterly plan: fix now, schedule next, accept as-is. Flag items getting worse.

**Use case:** Make data-driven tech debt decisions.

---

### 43. Learning Path Generator

> Skill: [TECHNOLOGY] | Level: [CURRENT] | Background: [EXPERIENCE]
> Time: [HOURS/WEEK] | Goal: [WHAT_TO_BUILD]
>
> Phases: fundamentals, practical application, advanced. Each with: resources, exercises, mini-project, time estimate, and checkpoint criteria.

**Use case:** Plan efficient skill development.

---

### 44. Code Migration Planner

> From [CURRENT_TECH] to [TARGET_TECH] | Codebase: [SIZE] | Team: [SIZE]
> Current: ```[LANGUAGE] [PATTERN] ``` | Target: ```[LANGUAGE] [PATTERN] ```
>
> Plan: codemods, manual steps, strangler fig strategy, testing parity, timeline, rollback, and definition of done.

**Use case:** Plan large-scale code migrations.

---

### 45. Interview Question Designer

> Role: [LEVEL] [TITLE] | Stack: [TECH] | Skills: [MUST_HAVES] | Team: [CONTEXT]
>
> Create: system design question (with rubric), coding problem (real-world, not leetcode), behavioral questions, and evaluation criteria. 60-minute format.

**Use case:** Design effective technical interviews.

---

### 46. Dependency Update Strategist

> ```
> [OUTDATED_DEPENDENCY_LIST]
> ```
> Project: [FRAMEWORK, TEST_COVERAGE, CI/CD]
>
> For each: breaking change risk, migration guides, peer deps. Create batched update plan: safe (batch 1), medium risk (batch 2), high risk (batch 3). Test strategy per batch.

**Use case:** Plan dependency updates without breaking things.

---

### 47. CI/CD Pipeline Optimizer

> ```yaml
> [YOUR_CI_CD_CONFIG]
> ```
> Duration: [MINUTES] | Pain points: [SLOW/FLAKY/COSTLY]
>
> Optimize: parallelization, caching, conditional execution, test splitting, artifact reuse, cost reduction. Provide optimized config with time savings.

**Use case:** Speed up slow CI/CD pipelines.

---

### 48. Monorepo Structure Advisor

> Projects: [LIST_AND_RELATIONSHIPS] | Shared code: [WHAT] | Teams: [MAPPING]
> Build: [TOOL]
>
> Recommend: directory structure, package boundaries, shared libs, workspace config, build pipeline, dependency management, CI strategy, CODEOWNERS.

**Use case:** Design or restructure a monorepo.

---

### 49. Feature Flag Strategy

> Feature: [NAME_AND_DESCRIPTION] | Risk: [LEVEL] | Rollout: [TARGET] | Rollback criteria: [METRICS]
>
> Design: naming convention, rollout phases, targeting rules, kill switch, auto-rollback thresholds, cleanup plan, and code pattern in [LANGUAGE].

**Use case:** Plan safe feature rollouts with flags.

---

### 50. Weekly Status Report Generator

> Worked on: [TASKS] | PRs merged: [LIST] | Blockers: [ANY] | Next week: [PLAN]
>
> Transform into: Summary, Completed (grouped), In Progress (% and ETA), Blocked, Key Decisions, Risks, Next Priorities. Scannable in 30 seconds.

**Use case:** Turn messy notes into polished status updates.

---

*Created by AXIOM | Yonder Zenith LLC | Version 1.0*

*AI Authorship Disclosure: This product was created by an autonomous AI agent as part of a documented business experiment.*
