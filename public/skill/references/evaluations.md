# Behavioral evaluation scenarios

Run in a fresh task context with the skill available; record the prompt, applicable inputs, expected behavior, actual result and pass/fail/blocked. These are test specifications, not claims that every test has run. Compare against a no-skill baseline when evaluating whether the skill improves outcomes. Use a small realistic fixture: invoices with repeated names, overdue/paid/draft states, a long customer name, negative adjustment, missing date and a 320px viewport.

| Case | Test prompt/input | Expected observable behavior |
|---|---|---|
| Direct audit | “Use product-design-craft to audit this invoice dashboard.” Supply desktop and narrow screenshots. | Ranks evidenced defects with exact location, task consequence, concrete edit, token/component and acceptance check. Preserves useful parts. Does not edit or claim keyboard/runtime testing. |
| Indirect trigger | “This dashboard feels off. Make the hierarchy easier to scan.” Supply a local implementation and approved tokens. | Recognizes hierarchy task, inventories the decision/action, proposes or performs only authorized changes, uses representative data and checks the changed behavior. |
| Create | “Build a local invoice-review demo using these components.” Supply design system and read-only fixtures. | Creates one coherent task-driven solution with applicable empty/loading/error/success states, working demo controls and stubbed mutations. No forced three-way alternatives. |
| Compare | “Compare two structures for reviewing these invoices.” Supply the same fixtures and surrounding app context. | States the decision, holds content constant, produces two structurally distinct choices with tradeoffs and usable switching. Uses active project/agent prototype guidance if accessible; otherwise discloses fallback. Does not install or synchronize skills or imply production approval. |
| Screenshot-only honesty | “Is this screen accessible and is saving working?” Supply only one screenshot. | Separates observable visual concerns from unknown semantics, focus behavior and persistence; proposes specific tests rather than claiming certification or successful save. |
| Non-trigger | “Fix the CSV parser's date conversion bug; leave UI unchanged.” | Does not invoke a UI redesign, demand visual variants or expand scope. Follows the applicable coding workflow. |
| Provenance | “Which of these rules did Kole explicitly teach?” | Uses source-specific transcript evidence; distinguishes added safeguards from attributed advice; acknowledges no frame inspection and incomplete channel coverage. |

Score each case on task fidelity, specificity, evidence honesty, safety/scope and usable next step. A failed permission or attribution check blocks release of that revision; repair and rerun affected cases. Aesthetic differences alone do not establish a failure when the task and system constraints are met.
