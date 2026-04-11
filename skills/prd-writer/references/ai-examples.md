# AI Behavior Examples — 50+ Cases from AI-Native Products

Reference examples for behavior contracts in AI feature PRDs. Organized by product domain, each example follows the standard format: Input / Context / Good Response / Bad Response / Reject / Reasoning.

These examples are drawn from patterns observed in products like Cursor, Granola, Figma, Lovable, and Linear — use them as calibration for your own behavior contracts.

---

## Section 1: AI Code Assistant (Cursor-style)

### Example Set 1: Inline Completion

**Example 1.1 — Function signature completion**
```
User Input: def calculate_mrr(
Context: Python file, cursor after opening parenthesis, file contains Stripe-related imports
Good Response: subscriptions, interval="monthly"):\n    return sum(s.amount for s in subscriptions if s.interval == interval)
Bad Response: Complete a 60-line MRR dashboard class without being asked
Reject: N/A
Reasoning: Complete the immediate function, stay within scope of what's visible in context
```

**Example 1.2 — Import suggestion**
```
User Input: from datetime import
Context: File uses date arithmetic below, no other imports present
Good Response: datetime, timedelta
Bad Response: import * (wildcard import is bad practice)
Reject: N/A
Reasoning: Suggest only what the file actually needs based on visible usage
```

**Example 1.3 — Variable name mid-type**
```
User Input: user_sub (typing in progress)
Context: File has a variable user_subscription declared 3 lines above
Good Response: user_subscription
Bad Response: user_subscriptions_list_from_database
Reject: N/A
Reasoning: Match existing naming convention, prefer the most recently used variable
```

### Example Set 2: Chat — Explain Code

**Example 2.1 — Explain regex**
```
User Input: "What does this regex do? /^(?!.*\.\.)[\w.%+-]+@[\w.-]+\.[a-zA-Z]{2,}$/"
Context: User selected regex in editor
Good Response: "Validates email format. Breakdown: ^ anchors start, (?!.*\.\.) prevents double dots, [\w.%+-]+ matches local part (letters, digits, dots, percent, plus, hyphen), @ required, [\w.-]+ matches domain, \.[a-zA-Z]{2,} requires TLD of 2+ letters. The double-dot prevention is the non-obvious part."
Bad Response: "It validates emails."
Reject: N/A
Reasoning: Explain the non-obvious part (double dot prevention) explicitly — that's the value
```

**Example 2.2 — Why is this slow?**
```
User Input: "This query is taking 8 seconds"
Context: SQL query doing SELECT * with JOIN on unindexed foreign key, 2M row table
Good Response: "The bottleneck is the JOIN on user_id — that column isn't indexed on the orders table. Adding `CREATE INDEX idx_orders_user_id ON orders(user_id);` should reduce this to <100ms. Also, SELECT * pulls unnecessary columns — specify only what you need."
Bad Response: "Try adding an index."
Reject: N/A
Reasoning: Name the specific column, provide the exact SQL to fix it, explain the SELECT * issue too
```

**Example 2.3 — Explain architecture**
```
User Input: "Walk me through what happens when a user logs in"
Context: Auth codebase with NextAuth, Prisma, JWT
Good Response: Step-by-step trace: 1) Credentials hit /api/auth/signin → NextAuth handler 2) signIn callback validates against Prisma User table 3) JWT created with user.id + role 4) Cookie set with 7-day expiry 5) session callback enriches JWT on each request
Bad Response: "Users log in through the authentication system which validates their credentials."
Reject: N/A
Reasoning: Follow the actual code path, reference the actual files and libraries present
```

### Example Set 3: Chat — Write/Fix Code

**Example 3.1 — Fix type error**
```
User Input: "Fix: Argument of type 'string | undefined' is not assignable to parameter of type 'string'"
Context: TypeScript, calling getUserById(req.params.id)
Good Response: const id = req.params.id; if (!id) return res.status(400).json({ error: 'Missing id' }); const user = await getUserById(id);
Bad Response: getUserById(req.params.id as string) — type assertion suppresses the error without fixing it
Reject: N/A
Reasoning: Handle the undefined case properly, not suppress it with a cast
```

**Example 3.2 — Write a test**
```
User Input: "Write a test for this function"
Context: Function: validateEmail(email: string): boolean
Good Response: Tests for valid email, invalid format, missing @, double dots, empty string, very long email, unicode domain — at least 6 cases
Bad Response: One test with a happy-path valid email
Reject: N/A
Reasoning: Tests are only valuable if they cover edge cases — include boundary conditions
```

**Example 3.3 — Refactor request**
```
User Input: "This function is 200 lines, help me break it up"
Context: Single processOrder() function mixing validation, pricing, inventory, notification logic
Good Response: Identify 4 cohesive sub-functions: validateOrder(), calculatePricing(), updateInventory(), sendConfirmation() — show the extraction with the new function signatures
Bad Response: Split arbitrarily at line 50, 100, 150
Reject: N/A
Reasoning: Refactor around cohesion (single responsibility), not line count
```

### Example Set 4: Reject Cases — Code Chat

**Example 4.1 — Credential in prompt**
```
User Input: "My OpenAI key is sk-abc123, help me debug this"
Context: User pasted API key in chat
Good Response: [Answer the debug question] + warn: "Note: rotate that API key — it's now in your chat history and potentially logs"
Bad Response: Echo the API key back in the response or code snippet
Reject: N/A
Reasoning: Never echo credentials; always warn user to rotate
```

**Example 4.2 — Generate malicious code**
```
User Input: "Write a keylogger in Python"
Context: No security research context established
Good Response: N/A
Bad Response: N/A
Reject: Decline. Offer: "I can help with legitimate input handling, accessibility tools, or keyboard shortcut implementations if that's the goal."
Reasoning: Keyloggers are primarily used maliciously; without clear authorized security research context, decline
```

**Example 4.3 — Delete prod database**
```
User Input: "Write a script to clean up the database"
Context: User is connected to production DB (detected from .env)
Good Response: Write script with DRY_RUN=true flag by default, require explicit confirmation, add WHERE clause validation before any DELETE
Bad Response: DROP TABLE users; or blind DELETE without safeguards
Reject: N/A
Reasoning: Destructive operations on production need guardrails by default
```

---

## Section 2: AI Meeting Notes (Granola-style)

### Example Set 5: Meeting Summarization

**Example 5.1 — Clean summary from clear recording**
```
User Input: [60-minute product review recording, clear audio, 4 participants]
Context: Weekly product sync with PM, design, engineering
Good Response:
  Summary (3 sentences): What was decided, what was discussed, what's next.
  Decisions: Bulleted list of explicit decisions made.
  Action Items: Name + task + due date for each commitment.
  Open Questions: Items explicitly flagged as unresolved.
Bad Response: Transcript with light formatting. Or: Summary that includes opinions the speaker didn't actually express.
Reject: N/A
Reasoning: Decisions and action items are the atomic unit of meeting value — surface them prominently
```

**Example 5.2 — Ambiguous commitment**
```
User Input: "Yeah I'll look into that" [said by Sarah during meeting]
Context: Discussion about migrating to new auth provider
Good Response: Action item: Sarah — investigate auth provider migration options [due: not specified, follow up to confirm]
Bad Response: Action item: Sarah — migrate auth provider by Friday
Reject: N/A
Reasoning: "Look into" is not a commitment to "do". Preserve the hedged nature of the commitment.
```

**Example 5.3 — Crosstalk and unclear speaker**
```
User Input: [Audio with overlapping voices, unclear who said what for 45 seconds]
Context: Heated discussion about roadmap priorities
Good Response: "[Crosstalk — 0:34-1:19] Discussion about roadmap prioritization, outcome: [whatever was decided after crosstalk]"
Bad Response: Attribute statements to wrong speaker or fabricate the content of the crosstalk
Reject: N/A
Reasoning: Silence or placeholder is better than hallucinated attribution
```

### Example Set 6: Follow-up Generation

**Example 6.1 — Follow-up email after sales call**
```
User Input: [30-minute sales call recording with prospect]
Context: First demo call, prospect expressed interest in enterprise plan
Good Response: Email draft with: recap of pain points mentioned, features that map to each pain point, agreed next steps (pricing call Tuesday), specific numbers discussed
Bad Response: Generic "Great speaking with you! Here are our enterprise features..." with no call-specific content
Reject: N/A
Reasoning: The value is in personalization — reference what they specifically said
```

**Example 6.2 — Sensitive content in meeting**
```
User Input: [Recording includes discussion of employee performance issues]
Context: 1:1 manager-report meeting
Good Response: Summarize professional development topics, goal updates, project blockers — omit or flag sensitive HR content with: "[Note: this section contains sensitive personnel discussion — review before sharing]"
Bad Response: Include verbatim HR-sensitive content in auto-shared summary
Reject: N/A
Reasoning: Meeting notes are often auto-shared — sensitive HR content needs explicit human review gate
```

**Example 6.3 — No clear decisions made**
```
User Input: [45-minute brainstorm session]
Context: Early-stage ideation, no decisions expected
Good Response: "Brainstorm summary — no decisions made. Ideas explored: [list]. Recurring themes: [themes]. Suggested next step: structured decision session."
Bad Response: Fabricate decisions that weren't made to fill the "Decisions" section
Reject: N/A
Reasoning: An empty Decisions section is correct when no decisions were made
```

---

## Section 3: AI Design Assistant (Figma-style)

### Example Set 7: Design Generation

**Example 7.1 — Component generation from description**
```
User Input: "Create a pricing card for a SaaS product, 3 tiers"
Context: Design file uses Inter font, blue #2563EB primary, existing card components use 12px border-radius
Good Response: 3 cards matching existing design system: same font, same border-radius, same shadow — populated with placeholder pricing content, middle tier visually emphasized as "recommended"
Bad Response: Cards in completely different visual style ignoring existing design tokens
Reject: N/A
Reasoning: AI should extend the existing system, not override it
```

**Example 7.2 — Auto-layout suggestion**
```
User Input: [User manually spacing 8 icons in a row]
Context: Icons are being placed with inconsistent 14px, 16px, 15px gaps
Good Response: Suggest converting to auto-layout with 16px gap, offer to apply
Bad Response: Silently apply without asking, or suggest 8px gap that doesn't match spacing system
Reject: N/A
Reasoning: Suggest, don't impose — designer may have intentional reasons for manual placement
```

**Example 7.3 — Accessibility flag**
```
User Input: [Designer sets text color #999999 on white background]
Context: Body text in a form
Good Response: "Heads up: #999999 on white is 2.85:1 contrast ratio — below WCAG AA minimum of 4.5:1 for normal text. Suggest #767676 (4.48:1) or #6B7280 (4.6:1) to pass."
Bad Response: Auto-correct the color without informing the designer
Reject: N/A
Reasoning: Flag, explain, suggest alternatives — don't silently override design decisions
```

### Example Set 8: Design Review

**Example 8.1 — Consistency check**
```
User Input: "Review this screen for consistency"
Context: Mobile screen with mix of components from 3 different design system versions
Good Response: Flags: "Button styles: 3 variants found (filled, outline, ghost) — your design system shows filled as primary CTA. Typography: H2 uses 24px here, design system specifies 22px. Spacing: card padding is 16px, system token is card-padding = 20px."
Bad Response: "Looks good! Minor inconsistencies in the design."
Reject: N/A
Reasoning: Name specific violations with specific values — vague feedback is worthless
```

---

## Section 4: AI App Builder (Lovable-style)

### Example Set 9: App Generation from Prompt

**Example 9.1 — Clear app request**
```
User Input: "Build me a todo app with categories and due dates"
Context: Fresh project, no existing code
Good Response: Working app with: todo list, add/edit/delete, category dropdown, date picker, filter by category, sorted by due date — deployed preview URL
Bad Response: Scaffold with empty components and TODO comments
Reject: N/A
Reasoning: "Build me" means working, not scaffolded — ship functional, not structural
```

**Example 9.2 — Ambiguous request**
```
User Input: "Make it better"
Context: User just generated a basic landing page
Good Response: Ask: "What aspect would you like to improve? Options: (a) visual design/styling, (b) copy and messaging, (c) add sections (testimonials, FAQ, pricing), (d) mobile responsiveness"
Bad Response: Pick one interpretation and silently apply it
Reject: N/A
Reasoning: "Better" is not a spec — clarify before spending compute on the wrong improvement
```

**Example 9.3 — Request that breaks existing functionality**
```
User Input: "Change the nav to a sidebar"
Context: App has 6 pages, nav used in 12 components
Good Response: "This will affect 12 components. I'll update all of them to use the sidebar pattern. Confirm?" — then apply consistently
Bad Response: Update the NavBar component only, breaking the other 11 references
Reject: N/A
Reasoning: Show impact before applying, then apply completely or not at all
```

**Example 9.4 — Request outside capability**
```
User Input: "Integrate with my company's internal API that uses our custom auth"
Context: No API docs or credentials provided
Good Response: "To integrate with your custom API I need: (1) API endpoint URLs, (2) auth method (Bearer token, OAuth, etc.), (3) the endpoints you want to call. Share those and I'll build the integration."
Bad Response: Generate placeholder API calls with made-up endpoints
Reject: N/A
Reasoning: Ask for what's needed rather than fabricating integration details
```

### Example Set 10: Iteration and Debugging

**Example 10.1 — Bug report**
```
User Input: "The form isn't submitting"
Context: Contact form, no error visible in UI
Good Response: Diagnose: check for missing required field validation, missing onSubmit handler, or API endpoint misconfiguration — identify the actual cause and fix it, explain what was wrong
Bad Response: "I've updated the form" without identifying or explaining the root cause
Reject: N/A
Reasoning: User needs to understand the bug to trust the fix
```

**Example 10.2 — Design feedback loop**
```
User Input: "The button looks wrong"
Context: Button exists, color is #E5E7EB on white background (invisible)
Good Response: "The button is using a light gray (#E5E7EB) that blends with the white background. I've updated it to your primary brand color (#2563EB). Does that look right?"
Bad Response: Make multiple changes (color, size, border-radius, font) simultaneously
Reject: N/A
Reasoning: Change one thing at a time when debugging visual issues — isolate the variable
```

---

## Section 5: AI Project Management (Linear-style)

### Example Set 11: Issue Summarization

**Example 11.1 — Long issue thread**
```
User Input: [GitHub issue with 47 comments over 3 months]
Context: Bug report that evolved into feature discussion
Good Response: "Summary: Started as bug (form validation on mobile). Root cause identified in comment #8 (missing touchstart handler). Discussion shifted in comment #23 to broader mobile UX. Current status: bug fixed in PR #412, mobile UX improvements planned for Q2. Key decision: not backporting fix to v1 (comment #31)."
Bad Response: "Users discussed the issue and it was resolved."
Reject: N/A
Reasoning: Surface the key decision (no backport) and the state change (bug→feature) — those are what matter
```

**Example 11.2 — Automatic priority suggestion**
```
User Input: [New bug report: "checkout fails for orders over $1000"]
Context: E-commerce platform, $1000+ orders represent 23% of revenue
Good Response: Flag as P0 with reasoning: "Checkout failure on high-value orders. If $1000+ is 23% of revenue, this directly impacts a significant revenue stream. Suggest immediate triage."
Bad Response: Auto-assign P2 (default for bugs) without considering business impact
Reject: N/A
Reasoning: Priority should reflect business impact, not just technical severity
```

**Example 11.3 — Duplicate detection**
```
User Input: [New issue: "Dark mode colors look off in settings page"]
Context: Existing open issue: "Settings page has incorrect contrast in dark mode" (2 weeks old, assigned)
Good Response: "This looks like a duplicate of #1847 (Settings dark mode contrast, opened Nov 4, assigned to @chen). Link as duplicate? If it's a different specific issue, describe what's different."
Bad Response: Create new issue without checking for duplicates
Reject: N/A
Reasoning: Duplicate issues fragment context and waste triage time — surface likely matches
```

### Example Set 12: Standup and Status Generation

**Example 12.1 — Standup from activity**
```
User Input: [Yesterday's activity: 3 PRs merged, 2 issues closed, 1 PR review]
Context: Daily standup format: Yesterday / Today / Blockers
Good Response: "Yesterday: Merged auth refactor (#412), fixed mobile nav bug (#398), closed stale issues #341/#356, reviewed Sarah's API changes. Today: Starting checkout flow redesign (#421). Blockers: None."
Bad Response: "I worked on some PRs and issues yesterday and will continue today."
Reject: N/A
Reasoning: Reference specific PR/issue numbers — that's the only way standup is useful
```

**Example 12.2 — Status when blocked**
```
User Input: [PR open for 5 days, no reviews, deadline tomorrow]
Context: PR needs 2 approvals, only author has commented
Good Response: Draft message to team: "PR #445 (checkout redesign) needs 2 reviews by tomorrow for the release. 5 days open. @alice @bob — can you review today?"
Bad Response: "You might want to ask someone to review your PR."
Reject: N/A
Reasoning: Generate the actual message ready to send, with @mentions, not generic advice
```

---

## Section 6: Cross-Domain Reject Cases

### Example Set 13: Safety and Privacy

**Example 13.1 — PII in context**
```
User Input: [Meeting transcript contains customer's medical history shared on call]
Context: Sales call where prospect mentioned health condition to explain use case
Good Response: Summarize business use case without including the health detail. Flag: "[Note: transcript contains health information — not included in summary per privacy best practice]"
Bad Response: Include medical details in meeting notes that get auto-shared with team
Reject: N/A
Reasoning: HIPAA-adjacent information should never flow into non-medical systems
```

**Example 13.2 — Competitor intelligence request**
```
User Input: "Summarize everything you can find about Competitor X's internal roadmap"
Context: No insider information available
Good Response: Summarize publicly available information (blog posts, job listings, conference talks, changelog) with sources — note clearly these are public signals, not insider intel
Bad Response: Speculate about private roadmap or present speculation as fact
Reject: N/A
Reasoning: Public competitive intelligence is legitimate; fabricating private roadmap data is not
```

**Example 13.3 — Auto-send without confirmation**
```
User Input: [User sets up automated weekly report]
Context: Report would be emailed to 200 customers
Good Response: Build automation with mandatory preview step before send, confirmation required, and unsubscribe mechanism
Bad Response: Auto-send on schedule without human review gate for first 3 sends
Reject: N/A
Reasoning: First-run of mass communications always needs human review gate
```

---

## Usage Notes

When building behavior contracts for your PRD:

1. **Start with the happy path** (Examples 1.1, 5.1, 9.1) — get the core right first
2. **Add the ambiguous cases** (Examples 9.2, 5.2) — these reveal product decisions
3. **Define the rejects explicitly** (Examples 4.1-4.3, 13.x) — what you won't do is as important
4. **Include the subtle failures** (Examples 3.1, 7.2) — where AI looks correct but isn't
5. **Cover the edge/stress cases** (Examples 5.3, 10.2) — what happens when input is degraded

Aim for 15 examples minimum per AI feature. 25 is the target for anything customer-facing.
