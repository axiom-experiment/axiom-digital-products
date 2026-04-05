# AI-Powered Code Review Prompt Pack
## 50 Expert Prompts for Senior Engineers & Engineering Teams

**Product ID:** PROD-004
**Price:** $19.99
**Format:** Markdown + JSON
**Audience:** Senior engineers, engineering leads, CTO, senior ICs, anyone doing code review

---

## Why This Pack Exists

Code review is where senior engineering time goes to die.

The average senior engineer spends 6–9 hours per week on code review. Most of that time is spent re-explaining the same patterns, catching the same classes of bugs, and writing variations of the same comments they've written a hundred times before.

These 50 prompts are designed to make AI your first-pass code reviewer — catching issues, suggesting improvements, and explaining trade-offs — so you can focus your human review time on architecture, context, and judgment that only you can provide.

Every prompt in this pack has been engineered for:
- **Specificity**: Tells the AI exactly what class of problem to look for
- **Actionability**: Gets concrete suggestions, not vague observations
- **Context-awareness**: Prompts you to provide the right context for better results
- **Learning amplification**: Explains the *why* behind every suggestion, so your team improves

---

## SECTION 1: Pre-Review Analysis (8 Prompts)

### PR-001: Quick PR Summary
```
You are a senior software engineer. I'm about to review this pull request and need a quick orientation.

Code diff:
[PASTE DIFF HERE]

Please provide:
1. A 2-sentence summary of what this PR does
2. The 3 most important files to review (and why)
3. The most likely areas of risk or concern
4. Anything that looks unusual or that I should ask the author about

Be direct. I have limited time.
```

### PR-002: Complexity Assessment
```
Analyze the following code change for complexity. I need to know if this PR is doing too much.

Code diff:
[PASTE DIFF HERE]

Evaluate:
1. Does this PR have a single clear purpose, or is it doing multiple things?
2. Rate the cognitive complexity on a scale of 1–10 (10 = hardest to understand)
3. Identify any functions over 20 lines that should be extracted
4. Flag any nested conditionals deeper than 3 levels
5. Suggest how to split this PR if it's too large (provide specific split points)
```

### PR-003: Test Coverage Evaluation
```
I'm reviewing a pull request. Evaluate the test quality and coverage.

Code changes:
[PASTE DIFF HERE]

Tests included:
[PASTE TEST FILES OR 'none']

Tell me:
1. What percentage of the changed behavior appears to be tested?
2. What critical paths are NOT tested?
3. Are there edge cases that should be tested but aren't?
4. Are the tests actually testing behavior or just implementation details?
5. What tests would you add if you were writing this?

Be specific — I want file names and test case descriptions.
```

### PR-004: Architecture Review
```
You are a systems architect reviewing a code change for architectural concerns.

Context about our system:
[DESCRIBE YOUR ARCHITECTURE: e.g., "Microservices, REST APIs, PostgreSQL, deployed on Railway"]

Code diff:
[PASTE DIFF HERE]

Review for:
1. Does this change fit the existing architecture, or does it introduce a new pattern?
2. Are there any violations of separation of concerns?
3. Does this create tight coupling between components that should be independent?
4. Are there scalability concerns if this code runs at 100x current load?
5. If this pattern is used everywhere, what does the system look like in 2 years?
```

### PR-005: Dependency Audit
```
Review the following code change for new dependencies being introduced.

package.json changes / import statements:
[PASTE RELEVANT SECTIONS]

For each new dependency:
1. What does it do? Is there a standard library alternative?
2. When was it last updated? (flag anything not updated in 12+ months)
3. What is its license? (flag anything non-permissive)
4. What security concerns should I check?
5. Is this dependency pulling in a large transitive dependency tree?
6. Recommendation: keep, replace with X, or remove?
```

### PR-006: Naming Convention Audit
```
Review the following code for naming quality. Good names are the foundation of readable code.

Code:
[PASTE CODE HERE]

Language/conventions: [e.g., "TypeScript, camelCase, we use Hungarian notation for DB models"]

Check for:
1. Variable names that don't describe their content (flag each one, suggest better name)
2. Function names that don't describe what the function does or returns
3. Boolean variables that don't start with is/has/can/should/was
4. Abbreviations that aren't universally understood
5. Any names that are misleading or opposite to what the thing actually does

Provide: original name → suggested name → reason
```

### PR-007: Change Log & Impact Assessment
```
I need to understand the blast radius of this change.

Code diff:
[PASTE DIFF HERE]

System context: [brief description of your system]

Analyze:
1. What existing behavior does this change?
2. What could break if this is deployed?
3. Which other teams or services might be affected?
4. Should this be behind a feature flag? Why or why not?
5. What monitoring/alerting should be in place before this goes to production?
6. What's the rollback plan if this causes issues?
```

### PR-008: First-Time Reviewer Context
```
I have no context on this codebase. Help me do a useful code review.

Code diff:
[PASTE DIFF HERE]

From the code alone, help me understand:
1. What problem is this code solving?
2. What are the inputs and outputs?
3. What are the assumptions the author seems to be making?
4. What would I need to know about the broader system to review this properly?
5. What questions should I ask the author before I begin my review?
```

---

## SECTION 2: Security Review (10 Prompts)

### SEC-001: Injection Vulnerability Scan
```
You are a security engineer. Scan this code for injection vulnerabilities.

Code:
[PASTE CODE HERE]

Language/framework: [e.g., "Node.js, Express, PostgreSQL via pg library"]

Check for:
1. SQL injection (raw string concatenation in queries)
2. NoSQL injection (unsanitized MongoDB/Redis queries)
3. Command injection (child_process with user input)
4. LDAP injection
5. XPath injection
6. Template injection (if applicable)

For each finding: line number, vulnerability type, risk level (critical/high/medium), and fix.
```

### SEC-002: Authentication & Authorization Audit
```
Review this code for authentication and authorization security issues.

Code:
[PASTE RELEVANT CODE — auth middleware, route definitions, permission checks]

Check for:
1. Missing authentication checks on sensitive routes
2. Authorization checks that can be bypassed (missing ownership validation, role checks)
3. Insecure direct object references (IDOR) — accessing resources by ID without ownership check
4. JWT implementation issues (algorithm confusion, missing expiry, weak secret)
5. Session management problems
6. Privilege escalation vectors

For each issue: severity, specific line/function, and remediation.
```

### SEC-003: Secrets & Credentials Scan
```
Scan this code for exposed secrets, credentials, or sensitive data handling issues.

Code:
[PASTE CODE HERE]

Look for:
1. Hardcoded API keys, passwords, tokens, or secrets
2. Credentials in comments or debug logging
3. Sensitive data being logged (passwords, tokens, PII)
4. Environment variable names that suggest they contain secrets (verify they're not hardcoded)
5. Secrets being passed in URLs or query parameters
6. Cryptographic keys or salts hardcoded in source

Flag: exact location, what was found, severity, and fix.
```

### SEC-004: Input Validation Review
```
Review this code for input validation completeness and correctness.

Code that handles user input:
[PASTE CODE HERE]

Input sources: [e.g., "HTTP request body, URL params, query strings"]

Check:
1. Is all user input validated before use?
2. Are there type coercions that could be abused?
3. Are string length limits enforced?
4. Are file upload types validated (if applicable)?
5. Is there protection against excessively large inputs (DoS via payload size)?
6. Is HTML/markdown output sanitized against XSS?
7. Are numeric inputs validated for range and integer overflow?
```

### SEC-005: Dependency Vulnerability Check
```
I need to assess the security posture of these dependencies.

package.json (or requirements.txt / Gemfile):
[PASTE YOUR DEPENDENCY FILE]

For each major dependency:
1. Are there known CVEs for this version? (check your knowledge up to your cutoff)
2. Is this package still actively maintained?
3. Any known security incidents with this package's maintainer?
4. Are we pinning to a specific version (good) or using a range (risky)?

Priority: flag anything with known critical or high CVEs first.
```

### SEC-006: Cryptography Implementation Review
```
Review this cryptographic implementation for correctness and security.

Code:
[PASTE CODE HERE]

Check for:
1. Use of deprecated or broken algorithms (MD5, SHA1, DES, RC4)
2. ECB mode block cipher usage (should be GCM or CBC with proper IV)
3. Hardcoded or predictable IVs/nonces
4. Insufficient key lengths
5. Improper key derivation (passwords hashed with raw SHA instead of bcrypt/argon2)
6. Missing integrity verification
7. Timing attacks in comparison functions (use constant-time comparison for secrets)
```

### SEC-007: Rate Limiting & DoS Protection
```
Review this API code for denial-of-service vulnerabilities and rate limiting gaps.

Code:
[PASTE ROUTE HANDLERS AND MIDDLEWARE]

Check:
1. Are unauthenticated endpoints rate-limited?
2. Are authentication endpoints (login, password reset) rate-limited and brute-force protected?
3. Are there any endpoints that do expensive computation without protection?
4. Is there protection against large request payloads?
5. Are there any N+1 query patterns that could be triggered by user input?
6. Is there protection against regex denial-of-service (ReDoS) in string processing?
```

### SEC-008: Data Exposure Review
```
Audit this code for unintended data exposure.

Code (API responses, serialization, logging):
[PASTE CODE HERE]

Check:
1. Are API responses returning more fields than the client needs?
2. Are internal IDs or implementation details exposed to clients?
3. Are error messages leaking stack traces or internal system details?
4. Is PII being logged anywhere?
5. Are database schemas or internal structure being exposed in error responses?
6. Is pagination implemented to prevent bulk data scraping?
```

### SEC-009: CORS & HTTP Security Headers
```
Review this server configuration for HTTP security issues.

Server setup code:
[PASTE CORS CONFIG, HELMET SETUP, OR EQUIVALENT]

Check:
1. Is CORS too permissive (wildcard origin with credentials)?
2. Are security headers set? (CSP, HSTS, X-Frame-Options, X-Content-Type-Options)
3. Is the server exposing version information in headers?
4. Is HTTPS enforced in production?
5. Are cookies set with Secure, HttpOnly, and SameSite attributes?
```

### SEC-010: File System & Path Traversal
```
Review this code for file system security vulnerabilities.

Code that reads/writes/serves files:
[PASTE CODE HERE]

Check:
1. Is user input used in file paths without sanitization? (path traversal risk)
2. Are file operations limited to an allowed directory?
3. Are file permissions validated before operations?
4. Is there symlink following that could escape intended directories?
5. Are temporary files created securely and cleaned up?
```

---

## SECTION 3: Performance Review (8 Prompts)

### PERF-001: Database Query Analysis
```
Review this code for database performance issues.

Code with database queries:
[PASTE CODE HERE]

Database: [e.g., "PostgreSQL 15, using Prisma ORM"]
Approximate data scale: [e.g., "1M users, 50M events, 10K writes/minute"]

Check for:
1. N+1 query patterns (fetching in a loop without batching)
2. Missing index opportunities (WHERE, ORDER BY, JOIN columns)
3. SELECT * when specific columns would suffice
4. Missing pagination on list queries
5. Synchronous queries that could run in parallel
6. Missing query timeouts
7. Transactions that hold locks longer than necessary
```

### PERF-002: Memory Allocation Profiling
```
Analyze this code for memory efficiency and potential memory leaks.

Code:
[PASTE CODE HERE]

Language/runtime: [e.g., "Node.js 20"]

Check for:
1. Large objects created in loops (unnecessary allocations)
2. Event listeners that are never removed
3. Caches or Maps that grow without bounds
4. Closures capturing large objects unnecessarily
5. Streaming opportunities (loading entire files/responses into memory vs streaming)
6. Object pooling opportunities for frequently created/destroyed objects
```

### PERF-003: Async/Await Efficiency
```
Review this async JavaScript/TypeScript code for concurrency efficiency.

Code:
[PASTE CODE HERE]

Check for:
1. Sequential awaits that should be parallelized with Promise.all()
2. Missing Promise.allSettled() where partial failure is acceptable
3. Async operations inside loops (should use Promise.all with map instead)
4. Waterfall patterns that could be restructured for parallel execution
5. Missing Promise.race() or AbortController for timeout patterns
6. Unnecessary async functions (no await inside)

Show me the before/after for any issues found.
```

### PERF-004: API Response Optimization
```
Analyze this API endpoint for response time optimization opportunities.

Endpoint code:
[PASTE HANDLER CODE]

Current p99 latency (if known): [X ms]
Expected request volume: [X req/min]

Check:
1. Are all database queries necessary for this response?
2. What can be cached? (Redis, in-memory, CDN layer)
3. Are there expensive computations that could be pre-computed?
4. Is pagination preventing full table scans?
5. Is the response payload larger than necessary?
6. Are there external API calls that could be parallelized or cached?
```

### PERF-005: Frontend Bundle Impact
```
Analyze this code change for browser bundle size impact.

New/changed imports and code:
[PASTE RELEVANT CODE]

Current bundle size (if known): [X KB]
Target: keep bundle under [X KB]

Check:
1. Are new dependencies being imported? What is their bundled size?
2. Are there tree-shaking issues (importing entire library vs named imports)?
3. Are there dynamic import opportunities for code splitting?
4. Are large objects or datasets being bundled that should be fetched at runtime?
5. Is dead code being included?
```

### PERF-006: Caching Strategy Review
```
Review this code's caching strategy for correctness and effectiveness.

Code with caching logic:
[PASTE CODE HERE]

Check:
1. Are cache keys unique and collision-free?
2. Is cache invalidation correct? What happens when the underlying data changes?
3. Are TTLs appropriate for the data volatility?
4. Is there a thundering herd problem (many requests missing cache simultaneously)?
5. Are there cache stampede protections (stale-while-revalidate, mutex on miss)?
6. Is sensitive data being cached (could cause data leaks between users)?
```

### PERF-007: Algorithm Complexity Review
```
Analyze this code's algorithmic complexity.

Code:
[PASTE CODE HERE]

For each function:
1. What is the time complexity? O(?)
2. What is the space complexity? O(?)
3. Is there a more efficient algorithm for this problem?
4. At what input size does this become a performance problem?
5. Are there early-exit optimizations missing?
6. Is any sorting using a suboptimal algorithm?
```

### PERF-008: Infrastructure & Deployment Performance
```
Review this infrastructure/deployment configuration for performance concerns.

Config files (docker-compose, k8s, nginx, etc.):
[PASTE CONFIG HERE]

Check:
1. Are worker/replica counts appropriate for the expected load?
2. Are resource limits (CPU, memory) set correctly?
3. Is connection pooling configured for the database?
4. Are there missing CDN or caching layers for static assets?
5. Is gzip/brotli compression enabled?
6. Are health check endpoints configured correctly?
```

---

## SECTION 4: Code Quality & Maintainability (12 Prompts)

### QUAL-001: SOLID Principles Review
```
Review this code against SOLID principles.

Code:
[PASTE CODE HERE]

Evaluate each principle:
1. **S** — Single Responsibility: Does each class/function do one thing?
2. **O** — Open/Closed: Is this open for extension but closed for modification?
3. **L** — Liskov Substitution: Can subtypes replace their base types?
4. **I** — Interface Segregation: Are interfaces too broad (forcing empty implementations)?
5. **D** — Dependency Inversion: Does high-level code depend on abstractions, not concretions?

For violations: line/class, which principle, why it matters, and how to fix it.
```

### QUAL-002: Error Handling Completeness
```
Review this code for error handling completeness and quality.

Code:
[PASTE CODE HERE]

Check:
1. Are all async operations wrapped in try/catch or chained with .catch()?
2. Are errors being swallowed silently (empty catch blocks)?
3. Are error messages helpful for debugging, or generic?
4. Are errors being re-thrown with context added?
5. Are network/timeout errors handled differently from application errors?
6. Is there a consistent error handling strategy, or is it inconsistent?
7. Are errors being logged with enough context to debug in production?
```

### QUAL-003: Documentation Quality
```
Review this code's documentation and comments for quality.

Code:
[PASTE CODE HERE]

Check:
1. Are public functions documented with: what they do, parameters, return value, exceptions?
2. Are complex algorithms explained with a brief comment on the *approach* (not just what the code does)?
3. Are there comments that just repeat what the code does (noise, should be removed)?
4. Are there "why" comments where non-obvious decisions were made?
5. Are deprecated functions/paths marked and alternatives provided?
6. Are TODO/FIXME comments specific (who, what, why) or vague?
```

### QUAL-004: Idiomatic Code Review
```
Review this code for language idioms and best practices.

Language: [e.g., TypeScript, Python, Go, Rust]
Code:
[PASTE CODE HERE]

Identify patterns that are:
1. Non-idiomatic for this language (doing things the hard way)
2. Using deprecated language features
3. Missing modern language features that would simplify this code
4. Anti-patterns specific to this language/ecosystem
5. Framework anti-patterns (if framework context is provided)

Show the idiomatic equivalent for each finding.
```

### QUAL-005: Refactoring Opportunities
```
Analyze this code for refactoring opportunities. I'm preparing to work in this area and want to understand what to clean up.

Code:
[PASTE CODE HERE]

Identify:
1. Duplicate code that should be extracted (DRY violations)
2. Long methods/functions that should be split (over 20 lines, doing multiple things)
3. Long parameter lists that should become objects
4. Primitive obsession (using strings/numbers where a type/enum would be cleaner)
5. Feature envy (a function that mostly uses another class's data)
6. Shotgun surgery opportunities (changes that always touch many files)

Prioritize by: impact × effort (quick wins first).
```

### QUAL-006: Test Quality Deep-Dive
```
Review this test code for quality and completeness.

Test file:
[PASTE TEST CODE]

Production code being tested:
[PASTE OR DESCRIBE]

Evaluate:
1. Are tests testing behavior or implementation? (behavioral tests survive refactors; implementation tests don't)
2. Are test names descriptive? (given X, when Y, then Z format)
3. Is the Arrange-Act-Assert pattern followed?
4. Are there any tests that always pass (testing nothing)?
5. Are mocks overused? (too many mocks = brittle tests)
6. Are edge cases (null, empty, boundary values) tested?
7. Are error paths tested?
8. What behavior is NOT tested that should be?
```

### QUAL-007: Code Readability Score
```
Score this code's readability on a 1–10 scale across these dimensions.

Code:
[PASTE CODE HERE]

Score and explain:
1. **Naming clarity** (1–10): Do variables/functions say what they are/do?
2. **Structural clarity** (1–10): Is the flow easy to follow top-to-bottom?
3. **Comment quality** (1–10): Do comments add signal, not noise?
4. **Function size** (1–10): Are functions the right size?
5. **Consistency** (1–10): Does this match the patterns around it?

Overall score: [X/10]
Top 3 improvements that would have the most impact on readability.
```

### QUAL-008: Magic Numbers & Hardcoded Values
```
Find all magic numbers, hardcoded strings, and unexplained literals in this code.

Code:
[PASTE CODE HERE]

For each finding:
1. Line number and the literal value
2. What does this value represent?
3. Should it be a named constant? An enum? A config value?
4. Suggested name and location (e.g., "MAX_RETRY_COUNT = 3, in src/config/constants.ts")
5. Risk: what happens if this value needs to change?
```

### QUAL-009: API Contract Review
```
You are reviewing an API design. I want feedback before this is shipped.

API design (routes, request/response schemas):
[PASTE OPENAPI SPEC, ROUTE DEFINITIONS, OR TYPE DEFINITIONS]

Evaluate:
1. Is the URL structure RESTful and consistent?
2. Are HTTP methods used correctly (GET for reads, POST for creates, etc.)?
3. Are HTTP status codes used correctly?
4. Is the request/response shape consistent across endpoints?
5. Are there versioning concerns?
6. What's missing that a client developer will immediately ask for?
7. Is pagination consistent for list endpoints?
8. Are error responses structured consistently?
```

### QUAL-010: Migration & Backwards Compatibility
```
Review this database migration / API change for backwards compatibility.

Change being made:
[PASTE MIGRATION FILE OR API CHANGE]

Current production usage: [describe existing clients/consumers if known]

Check:
1. Is this a breaking change for existing clients?
2. Is there a safe migration path that avoids downtime?
3. If a database migration: can it run without locking (large tables)?
4. Is there a rollback plan if this migration fails?
5. Should this be deployed in phases? What's the correct order?
```

### QUAL-011: Logging & Observability
```
Review this code for logging and observability completeness.

Code:
[PASTE CODE HERE]

Check:
1. Are all critical paths logged (start, success, failure)?
2. Are error logs structured with enough context to diagnose in production?
3. Are there any sensitive data being logged (passwords, tokens, PII)?
4. Are distributed trace IDs being propagated?
5. Are performance-critical operations timed and reported?
6. Are there any logging statements at wrong levels (debug in hot path, info for critical errors)?
7. What metrics should be incremented that aren't?
```

### QUAL-012: Code Review Comment Generator
```
I need to write code review comments for the following issues I found. Help me write comments that are: specific, actionable, kind, and educational.

Issues I found:
1. [DESCRIBE ISSUE 1]
2. [DESCRIBE ISSUE 2]
3. [DESCRIBE ISSUE 3]

Code context:
[PASTE RELEVANT CODE]

For each issue, write a code review comment that:
- Explains what the issue is
- Explains why it matters
- Suggests a specific fix
- Asks a question if intent is unclear (rather than assuming bad intent)
- Stays constructive and professional
```

---

## SECTION 5: Language-Specific Deep Dives (6 Prompts)

### LANG-001: JavaScript/TypeScript Async Patterns
```
Review this JavaScript/TypeScript code specifically for async pattern quality.

Code:
[PASTE CODE]

Check:
1. Missing await statements (common silent bug)
2. Promise chains that should be async/await
3. Unhandled promise rejections
4. Missing error boundaries around async React components (if applicable)
5. setTimeout/setInterval not being cleared
6. Race conditions in concurrent async operations
7. Missing AbortController for cancellable operations
```

### LANG-002: Python Production Code Review
```
You are a senior Python engineer. Review this code for Python-specific issues.

Code:
[PASTE PYTHON CODE]

Python version: [e.g., "3.12"]
Framework: [e.g., "FastAPI, SQLAlchemy 2.0"]

Check for:
1. Missing type hints (function signatures should be fully typed)
2. Mutable default arguments (a classic Python gotcha)
3. Not using context managers for resource management
4. Missing __slots__ for frequently instantiated classes
5. List comprehension vs generator expression (memory concern for large datasets)
6. Incorrect use of is vs == for value comparison
7. Thread safety issues (Global Interpreter Lock awareness)
```

### LANG-003: Go Code Review
```
Review this Go code for idiomatic patterns and correctness.

Code:
[PASTE GO CODE]

Check for:
1. Error values being ignored (if err != nil not checked)
2. Goroutine leaks (goroutines that never exit)
3. Channel direction specified where possible
4. Missing context propagation
5. defer in loops (execute outside the loop instead)
6. Mutex being copied (should always be passed by pointer)
7. Interface satisfied check (compile-time interface satisfaction)
```

### LANG-004: SQL Query Review
```
Review this SQL for correctness, performance, and security.

SQL:
[PASTE SQL HERE]

Database: [e.g., "PostgreSQL 15"]
Approximate table sizes: [e.g., "users: 2M rows, orders: 50M rows"]

Check:
1. Is this query using indexes? (check WHERE, ORDER BY, JOIN columns)
2. Are there Cartesian products from missing JOIN conditions?
3. Is DISTINCT hiding a join problem?
4. Are subqueries that could be CTEs or JOINs?
5. Are there NULLs in comparison logic (use IS NULL not = NULL)?
6. Is ORDER BY without LIMIT on large tables?
7. Are there any injection risks (parameterization check)?

Provide: EXPLAIN ANALYZE suggestions and query rewrite if applicable.
```

### LANG-005: Dockerfile & Container Review
```
Review this Dockerfile and container configuration for security and efficiency.

Dockerfile:
[PASTE DOCKERFILE]

docker-compose.yml (if applicable):
[PASTE OR SKIP]

Check:
1. Is the base image pinned to a specific digest, or using :latest (risky)?
2. Is the image running as root (security risk)?
3. Are there unnecessary packages in the final image?
4. Is multi-stage build used to minimize final image size?
5. Are secrets passed via ARG (risky — appears in image history) vs secrets mount?
6. Is .dockerignore configured to exclude node_modules, .env, etc.?
7. Is the correct USER set for the production container?
```

### LANG-006: Infrastructure as Code Review
```
Review this infrastructure code (Terraform/CDK/Pulumi) for security and correctness.

Code:
[PASTE IaC CODE]

Cloud provider: [AWS/GCP/Azure]

Check:
1. Are IAM permissions following least-privilege (no wildcard actions on production resources)?
2. Is sensitive output (passwords, keys) marked sensitive = true?
3. Is encryption at rest enabled for storage resources?
4. Are security groups/firewalls too permissive?
5. Are resources tagged for cost attribution?
6. Is the state backend secure (encrypted, versioned)?
7. Are there hardcoded credentials or account IDs?
```

---

## SECTION 6: Team & Process Prompts (6 Prompts)

### TEAM-001: Junior Developer Code Review
```
I'm reviewing code written by a junior developer. I want feedback that will help them grow, not just fix the immediate issue.

Their code:
[PASTE CODE HERE]

For each issue you find:
1. Identify the issue clearly
2. Explain the PRINCIPLE being violated (not just what to change)
3. Show the improved version
4. Point to a resource they could read to learn more (concept name, not URL)
5. Distinguish between: must-fix vs nice-to-have vs personal preference

Keep the tone encouraging and educational.
```

### TEAM-002: PR Description Generator
```
Generate a high-quality PR description for this code change.

Code diff:
[PASTE DIFF]

Ticket/issue reference (if any): [e.g., "JIRA-1234"]

Write a PR description with:
1. **Summary**: What this PR does (2-3 sentences, non-technical enough for a PM to understand)
2. **Changes made**: Bullet list of the specific technical changes
3. **Why these changes**: The problem being solved or improvement being made
4. **Testing done**: How this was validated
5. **How to test**: Steps for the reviewer to verify the changes work
6. **Notes**: Anything the reviewer should pay special attention to, known issues, or follow-ups
7. **Screenshots** (placeholder if UI change)
```

### TEAM-003: Architecture Decision Record
```
I need to write an Architecture Decision Record (ADR) for a technical decision I made in this PR.

Decision made:
[DESCRIBE THE DECISION: e.g., "Chose PostgreSQL over MongoDB for the new events table"]

Context:
[DESCRIBE THE SITUATION THAT REQUIRED THIS DECISION]

Code implementing this decision:
[PASTE RELEVANT CODE OR DESCRIBE]

Write an ADR in standard format:
- **Status**: [Proposed/Accepted/Deprecated]
- **Context**: Why was this decision needed?
- **Decision**: What was decided?
- **Options Considered**: What alternatives were evaluated?
- **Consequences**: Positive and negative consequences of this decision
- **Decision Makers**: [Your name/team]
- **Date**: [Today's date]
```

### TEAM-004: Code Style Enforcement Check
```
Check this code against our team's coding standards.

Our standards:
[PASTE YOUR TEAM'S STYLE GUIDE OR LINTING RULES — or describe them]

Code submitted for review:
[PASTE CODE HERE]

For each violation:
1. Line number
2. Rule violated
3. Correct pattern
4. Severity (blocking / non-blocking)

Also flag: inconsistencies where the code follows a different pattern than what's established in surrounding files.
```

### TEAM-005: Sprint Retrospective Code Quality Analysis
```
I want to analyze the code quality trends from our last sprint to identify process improvements.

Summary of PRs merged this sprint:
[PASTE PR TITLES, OR LIST OF ISSUES/IMPROVEMENTS FOUND IN REVIEWS]

Analyze:
1. What categories of issues came up most often? (security, performance, testing, naming, etc.)
2. Were there recurring patterns that suggest a knowledge gap on the team?
3. What training, tooling, or process changes would prevent these issues in future sprints?
4. Are there areas where linting/static analysis could catch issues automatically?
5. Recommend 2-3 concrete improvements for next sprint's review process.
```

### TEAM-006: Merge vs. Hold Decision Support
```
Help me decide whether to approve, request changes, or block this PR.

PR description: [PASTE]
Code diff: [PASTE DIFF OR KEY SECTIONS]
Author's seniority: [junior/mid/senior]
This code is going to: [production/staging/feature branch]

Evaluate:
1. Blocking issues (must fix before merge) — list each
2. Important improvements (should fix, could merge with agreement) — list each
3. Nice-to-haves (can be follow-up PR) — list each
4. What I would tell the author in a synchronous conversation

Recommendation: APPROVE / REQUEST CHANGES / BLOCK (with reasoning)
```

---

## Product Metadata

```json
{
  "product_id": "PROD-004",
  "title": "AI-Powered Code Review Prompt Pack — 50 Expert Prompts for Senior Engineers",
  "version": "1.0.0",
  "created_by": "AXIOM Autonomous Agent",
  "created_at": "2026-03-21",
  "price_usd": 19.99,
  "format": ["markdown", "json"],
  "license": "Single-user, non-transferable",
  "total_prompts": 50,
  "sections": {
    "pre_review_analysis": 8,
    "security_review": 10,
    "performance_review": 8,
    "code_quality_maintainability": 12,
    "language_specific": 6,
    "team_and_process": 6
  },
  "target_audience": [
    "Senior software engineers",
    "Engineering leads / tech leads",
    "Engineering managers doing hands-on review",
    "Staff and principal engineers",
    "Solo developers who want systematic review practice"
  ],
  "use_cases": [
    "Systematic code review checklists",
    "Training junior developers with structured feedback",
    "Security audits for pull requests",
    "Performance reviews before production deploys",
    "Team retrospective quality analysis"
  ],
  "compatible_with": [
    "Claude", "ChatGPT", "GPT-4o", "Gemini", "Mistral", "any LLM"
  ],
  "affiliate_placeholder": "[AFFILIATE_GUMROAD_LINK]"
}
```

---

*AXIOM is an autonomous AI agent experiment. This product was researched, designed, and written entirely by AI. All prompts are original work.*
