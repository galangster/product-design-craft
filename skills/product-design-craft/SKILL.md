---
name: product-design-craft
description: Audit product interfaces that feel visually off, create detailed product UI, or compare structural prototype directions. Use for hierarchy, dashboards, tables, columns, cards, forms, and interaction-state design; turn critique into specific changes and observable acceptance checks.
---

# Product design craft

Use a repeatable decision process, not a predetermined visual style. Improve how a person identifies, understands, and completes the task. This skill complements the project's design system and existing prototype workflow; it does not replace their authority.

## 1. Establish the decision

Read the applicable product/design context and inspect the actual screen, code or design file. Record:
- Primary user, task, decision, and successful next action.
- Surface and available space; realistic data volume, content lengths and permissions.
- Approved design system, existing components, responsive constraints, and immutable decisions.
- Evidence available: live interaction, screenshot, code, design file, or description. State missing evidence; do not claim runtime verification from static artifacts.

Choose a mode: **audit** identifies evidenced defects; **create** makes one coherent solution; **compare** explores a specific unresolved structural decision. Ask only when a missing answer changes a consequential design decision; otherwise label a working assumption and proceed. Done: one sentence defines what this pass must improve and how improvement will be observed.

## 2. Map hierarchy before decoration

Write a ranked inventory: primary decision/action, supporting evidence, secondary actions, and optional detail. Trace the first five seconds of viewing: where attention starts, what explains it, and where the next action lives. Check this against the real task rather than generic visual impact.

Load [pattern recipes](references/patterns.md) only for the relevant surfaces. For each candidate change, specify the observed symptom, affected element, intended behavior, exact operation, and test. Use real labels and example values. Prefer the existing token or component name over invented pixel precision; give a measured or explicitly provisional value when useful.

Example: replace “reduce cognitive load” with “Move the three per-row secondary actions into a labeled overflow menu; retain the primary Review action in the action column. Show the menu with keyboard and pointer, return focus to its trigger on close, and verify the row still scans without horizontal scrolling at the target viewport.”

Done: each proposed change names an element and a falsifiable expected improvement.

## 3. Execute the selected mode

### Audit
Review in this order: task clarity; hierarchy and grouping; information density; interaction and states; responsive behavior; accessibility and visual consistency. Examine applicable states rather than assuming the happy path is representative.

Report a small ranked set of findings using:
`Priority | evidence/location | user consequence | exact change | acceptance check | confidence`
Priority follows consequence: blocked/error-prone task first, repeated friction second, polish last. Distinguish observed defects from hypotheses. Aesthetic preference alone is not a usability defect. Name what already works and should remain. An audit request alone authorizes no implementation.

### Create
Build a hierarchy sketch using realistic content before high-fidelity styling. Select structure using the task and pattern recipes. Reuse approved components/tokens; design the meaningful empty, loading, error, success and permission states. State which are applicable and why. Implement only within the request's authorized scope. A demo uses local fixtures and stubbed mutations, not real payments, submissions or destructive actions.

### Compare
State one decision question. Default to three materially different structures; use fewer when only two credible alternatives exist. Hold content, task, data and design system constant. Vary layout, reading order or interaction model, not merely colors. Name each variant by its tradeoff and define what the user should try.

Choose and read the prototype workflow applicable to the active agent and project before building. If none is accessible, disclose that gap and use the bounded comparison guidance in this section; do not install, synchronize or replace another workflow merely to satisfy this step. Prefer real app context in a safe development preview, with all mutations stubbed. Make switching shareable and obvious, protect form keyboard input, and exclude demo controls from production. Retain this skill's evidence and safety checks when using a prototype dependency; its shortcuts or cleanup steps do not authorize production edits, commits, issue changes or publication. For state-model uncertainty, a small standalone demo with readable state, free exploration and resettable scenarios can be more useful than polished variants. Owner selection and production authorization are distinct from creating a prototype.

Done: the artifact can answer the stated question; controls used in the demo work or are explicitly labeled as nonfunctional.

## 4. Verify the result

Use [verification](references/verification.md). Test the target task and the exact acceptance checks, not just whether the page loads. Revisit the same realistic data and viewport used for the baseline. Record executed checks, failures, and untested states separately. A reduced screenshot cannot establish focus behavior, semantics, assistive technology support or successful data persistence.

Done: the report separates proposed design, implemented artifact, tested behavior, and release status. Never imply a prototype is production-ready or deployed.

## 5. Handoff

Lead with the recommended direction and its tradeoff. Include the ranked findings or change list, artifact location, before/after evidence where available, exact checks performed, remaining uncertainty, and the next decision. Preserve the rationale and chosen direction in the existing project record, within authorized scope; avoid competing specifications.

## Skill evaluation

When changing this skill, run the relevant cases in [evaluation scenarios](references/evaluations.md) and record actual results. Installing the files or passing a format check does not establish behavioral quality.

## Evidence and attribution

Read [sources](references/sources.md) before attributing advice to a named designer. The pattern recipes are original working guidance, not quotations, a transcript collection, or proof that a creator endorses every rule. Missing video or screen access must remain visible. Use source-specific evidence for creator-specific claims. This skill never grants account access, publication, production mutation, or permission to change approved designs.
