# Verification checklist

Use actual execution where possible and label the evidence source. Record N/A with a reason, not a silent omission.

1. **Task:** run the primary journey with representative data; verify completion and recovery. For prototypes, say that effects are simulated.
2. **Content:** long and short names, zero/negative/large numbers, missing values, many rows, localization expansion, and a realistic empty state.
3. **States:** initial, loading, loaded, empty, error, success, disabled/permission, selected and pending changes where applicable. Confirm a disabled state explains how to proceed when relevant.
4. **Keyboard:** tab order follows reading/task order; focus is visible; controls activate appropriately; menus/dialogs open, close and return focus; no accidental keyboard trap. Avoid arrow-key prototype shortcuts while editing fields.
5. **Semantics:** real buttons for actions and links for navigation; accessible names match visible purpose; associated field labels and errors; tables retain header relationships. Static visual inspection alone cannot prove these.
6. **Contrast and cues:** measure text contrast (WCAG AA 4.5:1 ordinary, 3:1 large text) and applicable non-text boundaries/state indicators (3:1); retain meaning without color alone. Report measured values, not a blanket compliance claim.
7. **Targets and zoom:** check applicable WCAG 2.2 target-size minimum 24 CSS px or qualifying spacing/exceptions; prefer larger comfortable touch targets when possible. Test 200% text resizing and reflow at 320 CSS px with appropriate exceptions for genuinely two-dimensional content.
8. **Motion:** respect reduced-motion preference; keep state understandable without motion; avoid unnecessary autoplay or flashing. A nonanimated variant is a real test, not a token declaration.
9. **Responsive:** verify task/action visibility, overflow, sticky layers, menus, virtual keyboard and content wrapping at target sizes. Test zoom as well as narrow screenshots.
10. **Regression:** compare the same data/state/viewport to baseline; confirm improvements do not remove necessary information or actions. For production-bound work preserve project test, security, independent review and release gates.

Evidence record: artifact revision; environment; viewport/state; action performed; observed outcome; pass/fail/blocked; unresolved risk. Separate visual review, interaction checks, automated checks and human validation. Never turn a checklist into a claim of complete accessibility certification.
