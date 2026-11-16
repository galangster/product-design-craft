---
name: product-design-craft
description: Audit product interfaces that look or feel visually off, create detailed UI, or compare structural prototypes. Use for hierarchy, density, dashboards, columns, tables, cards, forms and interaction states that need concrete improvements and observable checks.
---

# Product design craft

Use a repeatable decision process, not a predetermined style. Preserve the project's design system, approved decisions and existing workflows. This skill grants no additional permissions; an audit alone authorizes no edits, and a prototype authorizes no production integration or publication.

## 1. Define the outcome

Inspect applicable product/design context and the actual artifact. Record the user/task, desired outcome, target viewport, realistic data, constraints and evidence available. Distinguish the outcome from its proxy: copying a command is not installing successfully.

Choose **audit**, **create**, or **compare**. Resolve only consequential unknowns; otherwise label assumptions. Scale the brief to the task: name a success signal, downside to guard against, riskiest user assumption and cheapest test that could disprove it. Before building, write an acceptance scenario with input, action and expected outcome.

## 2. Establish hierarchy

Rank the primary decision/action, supporting evidence, secondary actions and optional detail. Predict the viewing sequence. Classify content before styling; remove redundancy without hiding action-enabling or risk information.

Read [craft decisions](references/craft.md) for subtraction, icon choices and rendered hierarchy. Read only applicable headings in [pattern recipes](references/patterns.md) for the surface being worked on.

Each proposed change must name an observed element, user consequence, exact operation and acceptance check. Prefer existing token/component names; label provisional measurements. “Reduce cognitive load” is insufficient: specify which rare row actions move into overflow, which primary action stays visible, and how keyboard access and scanning will be checked.

## 3. Execute one mode

### Audit
Inspect task clarity, hierarchy/grouping, density, interaction/state coverage, responsive behavior and accessibility/consistency. Preserve what works. Return a small ranked set:
`Priority | evidence/location | consequence | exact change | acceptance check | confidence`
Prioritize blocked/error-prone tasks, then repeated friction, then polish. Separate observations, hypotheses and aesthetic preference.

### Create
Sketch the hierarchy with realistic content, then reuse approved components/tokens. Produce one coherent solution rather than forced alternatives. Define applicable states using [verification](references/verification.md). Demo controls must work or be explicitly labeled nonfunctional; use fixtures and stubbed mutations, not real external effects.

### Compare
Explore one unresolved structural decision using [comparison guidance](references/compare.md). Hold task, content and design system constant; explain each alternative's tradeoff. Read the active project/agent prototype workflow if available. If unavailable, disclose the gap and use the bounded guidance; do not install or synchronize dependencies to proceed.

## 4. Verify and correct

Run [verification](references/verification.md) against the acceptance scenario and the same data/viewports as the baseline. Inspect rendered target views when available: source styles express intent, not proof. Apply the rendered hierarchy checks in craft decisions, identify the largest gap, correct it and rerender affected states.

Stop when predeclared checks pass or report the unresolved issue. Compare alternatives against the same criteria, including adverse tradeoffs, rather than chasing a self-score. Separate proposed, implemented, tested and released states. A screenshot cannot establish semantics, keyboard behavior or persistence; blocked rendering means visual quality remains unverified. Expert inspection is not user research.

## 5. Handoff

Lead with the recommendation and tradeoff. Provide findings/changes, artifact and before/after evidence, executed checks, unresolved risk and next decision. Preserve rationale in the existing project record within scope, not a competing specification.

## Conditional references

- When revising this skill: use [evaluation cases and rubric](references/evaluations.md); record actual results separately. Formatting success does not prove behavioral quality.
- When explaining evidence or the basis of guidance: read [evidence and limits](references/sources.md). Distinguish synthesis, standards and tested results.
