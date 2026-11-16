# Craft decisions: turn intent into a convincing rendered interface

These are original, testable synthesis from the bounded research and observed evaluation gaps, not universal laws or direct quotations from a named designer. Use the project's visual language. A restrained financial workspace and an expressive creation tool need different treatments.

## Subtract by role, not by word count

Classify each block before removing it:
- **Decision-critical:** object identity, value, status, comparison and constraints that change the decision.
- **Action-enabling:** necessary instruction, input, next step and recovery.
- **Trust/risk:** price/interval, destructive consequence, permission scope, data freshness and uncertainty.
- **Optional detail:** valuable only on demand; place beside its trigger or in a secondary disclosure.
- **Redundant explanation:** repeats a visible heading, interface action, neighboring claim or demonstration.

Preserve the first three. Compress or relocate optional detail. Remove redundancy and check that the task remains understandable. “Cleaner” is not proof of improvement. A shorter financial confirmation that hides its consequence fails.

For a minimal skill install page, a real command and its honest copy result may fully convey the immediate task. Add an example invocation or resulting artifact only when needed to explain otherwise unknown value, not as a mandatory section. Keep prerequisites that determine whether installation can succeed, and supported-agent limitations, visible before the installation action; reserve secondary troubleshooting for disclosure. Replace abstract benefit sections with a concrete object/action/outcome only when this clarifies rather than bloats the task. Do not fabricate customer results, testimonials or successful installations as proof. For a dense working tool, instruction may be contextual rather than an entire introductory hero.

## Pick icons by recognition and consequence

Ask what job an icon performs: recognizable action, object/status recognition, navigation, or decoration. If it adds no independent scan value, try removing it. If it represents an ambiguous or consequential action, pair it with a visible label; an accessible name alone does not solve sighted recognition.

Use the project's existing icon family and optical scale. Match stroke weight, baseline and visual mass; equal SVG boxes do not guarantee equal perceived size. Inspect the actual rendered glyph at its displayed size. Keep the interactive hitbox separate from the glyph size. Icon-only familiar controls still require accessible names and focus/hover behavior; tooltips supplement rather than replace necessary labels. Meaning must survive color loss.

Examples: a trash glyph alone is weak for “Delete invoice permanently”; retain an explicit label and consequence. A compact familiar search control may work with an accessible name and clear context. A sparkle beside every heading adds no hierarchy merely because it fills empty space.

## Judge hierarchy in the rendered result

Before rendering, predict the first, second and third attention stops and the likely next action. After rendering, inspect full-size target screenshots, not only a miniature montage. Check:
- Dominance: does the intended object/decision lead, or does chrome, a saturated status, decorative graphic or enormous heading compete?
- Reading sequence: do alignment, spacing, label/value proximity and contrast support the task's order?
- Craft consistency: are baselines, icon weights, number alignment and repeated radii/spacing deliberate within the system?
- Density: does information occupy useful space without crowding or unexplained emptiness? Does a repeated card border add structure or noise?
- Responsiveness: do long content and narrow widths preserve the decision, action and trust context?

If source and screenshot disagree, record browser/device or viewport, zoom, artifact revision and inspected state. Investigate font loading/fallback, actual computed dimensions, overflow/clipping, SVG viewBox, breakpoint and sticky/overlay behavior before applying another arbitrary token. Preserve screenshot paths or links when available. No screenshot means no claim of rendered visual verification.

## Show, inspect, correct

Use a concrete before/after question: “Can I identify the overdue invoice and review its amount without decoding four badges?” Choose the smallest set of coordinated changes that answers it. Explain the tradeoff, not a list of adjectives. Rerender and retest affected states after corrections. Distinguish expert inspection from a timed task with a real person: a five-second self-check is a heuristic, not measured user performance. Ask a human to judge uncertain craft choices only when their preference or domain judgment matters; do not invent usability-study results.
