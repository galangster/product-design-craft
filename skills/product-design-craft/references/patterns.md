# Observable patterns and repair recipes

Select recipes by the task, not by applying every rule to every screen. Values are starting hypotheses; existing design-system tokens and observed content take precedence.

## Hierarchy and typography
- **Everything competes:** identify the single current decision. Give its title/value/action the strongest relevant contrast; reduce supporting metadata one token step, not to illegibility. Test a five-second recall: can someone name the screen's purpose and next action?
- **Large type without meaning:** separate a metric's label, value, unit and context. Keep units visually attached; place timeframe and comparison beside the metric. Show “vs previous 30 days” rather than an unexplained percentage. Check negative values and unavailable comparisons.
- **Unclear grouping:** use smaller intra-group spacing than inter-group spacing, with headings aligned to their contents. Remove redundant nested borders only when spacing or background still defines membership. Check the layout with long titles and without color.
- **Scanning breaks:** use a limited text hierarchy and consistent line-height; align repeated labels and values; avoid centered multi-line operational content. Use tabular numerals for comparable numeric columns. Check 200% text zoom and truncation disclosure.

## Dashboards
- **Metric wallpaper:** map each summary to a decision, not an arbitrary KPI slot. Put the urgent exception and its action before routine totals. Keep trends contextual: range, unit, baseline and freshness. Test whether the primary question can be answered without opening every card.
- **Charts need decoding:** label series near data where feasible, reduce unnecessary gridlines, retain units and accessible text summaries. Color is not the only differentiator. Check zero, negative, sparse and missing data. Do not invent precision or hide an important baseline to exaggerate a change.
- **Controls scattered:** group page-scoped filters near the page summary; put widget-only controls on the widget. Show active scope, applied filters and a reset. Verify that displayed totals and rows use the same scope.

## Tables and dense lists
- **Wrong structure:** choose a table when people compare the same attributes across items; choose a list/card when each item needs variable narrative or media. Avoid converting a comparison task into tall cards merely to look modern.
- **Slow comparison:** anchor identity at the start, put high-value comparison columns next, and move rare attributes into details. Right-align numeric measures, preserve units, use consistent date formats. Sort indicators describe current order, not just affordance. Test realistic row counts and repeated similar names.
- **Ambiguous actions:** distinguish row navigation, selection and destructive actions. Put selection in a dedicated control, expose primary action consistently, and keep overflow discoverable. Test keyboard navigation and nested click targets.
- **Dense but unreadable:** adjust row padding by density token while keeping pointer targets adequate. Prefer subtle separators or banding only when they aid tracking. Test long names, missing cells, wrapped content and high zoom before deciding on truncation.
- **Mobile overflow:** prioritize columns or provide deliberate horizontal scrolling with clear context. Preserve identity and access to every essential value; do not silently hide decision-critical columns. Verify sticky regions do not obscure content or focus. Where horizontal scrolling is necessary, provide an observable overflow cue (for example a clipped next column with a safe fade or a concise visible scroll hint) and test reaching the last column by touch and keyboard; an ARIA region name alone is not a sighted discoverability cue.
- **Bulk-action surprise:** show selection count and exact scope (“this page” versus “all matching”). Preview affected items and provide reversibility/confirmation appropriate to risk. Stub destructive operations in demos.

## Cards and columns
- **Card soup:** use cards for meaningful independent objects or groups, not every label. Align repeated title, metadata, body and action zones. Let content determine height when equal heights produce large empty areas; compare both with realistic content.
- **Columns feel unrelated:** align shared header and content baselines; give each column a clear role and consistent status/count language. Use a detail pane for the selected item when the task is browsing then inspecting, not as an ornamental third column.
- **Kanban drag-only:** show status and count, allow accessible non-drag movement, and specify empty/overflow states. Test moving an item to an unavailable state and recovering from failure.
- **Competing CTAs:** reserve the strongest treatment for the next likely task action; keep secondary actions visible but lower-emphasis. Destructive intent stays explicit. Do not hide common actions solely to achieve minimalism.

## Forms, settings and detail pages
- **Long undifferentiated form:** group fields by the user's mental steps, place labels and help adjacent, and distinguish optional fields consistently. Keep related short inputs on one row only when narrow widths and long labels still work.
- **Error without recovery:** preserve entered values, attach an error to the relevant field, explain how to fix it, and link a summary to errors on long forms. Distinguish client validation from server failure. Test keyboard focus and resubmission.
- **Saving unclear:** distinguish auto-save from explicit Save, show pending/saved/failed state, and define cancel/undo behavior. Warn about leaving only when real unsaved changes exist. Simulate failures without real external mutations.
- **Detail overwhelms:** lead with identity, status, primary action and the most decision-relevant facts. Place history and rare configuration after the core task. Expand contextual details without losing the item's identity or the user's place.

## Navigation, states and responsive layout
- **Lost context:** make selected navigation, page title and breadcrumbs consistent. Preserve filters/scroll where returning users expect it. Verify back navigation and deep links.
- **Empty state dead-end:** distinguish first use, no filter matches, lack of permission and retrieval error. Give the appropriate next action, not the same cheerful illustration for every case.
- **Loading jumps:** reserve predictable space or show representative placeholders; announce meaningful progress without repeated distracting animation. Keep retry/error actions available when loading fails.
- **Responsive collapse:** prioritize the task before choosing breakpoints. Test the narrowest supported viewport, typical desktop, text zoom, long strings, and mixed-density content. Keep actions reachable without overlay collisions.

## Containers, color and feedback (transcript-informed synthesis)
- **Wrong interaction container:** use a popover for a small bounded choice with useful surrounding context; consider a modal for a bounded multi-step or complex task; use a page when context, deep linking or prolonged work must persist. These are decision prompts, not fixed laws. Test focus return, dismissal and unsaved-work behavior.
- **Optimistic success hides failure:** show the immediate provisional result only when recovery is defined. On failure restore prior state or clearly identify the unsaved change, retain user work and offer retry. Exercise the rollback path in a stubbed demo.
- **Color hierarchy is ornamental:** assign semantic background, border, text, action and status tokens. Tune dark mode separately rather than inverting colors. Verify contrast and noncolor meaning; a fixed palette percentage is not an acceptance criterion.
- **Timeline buried in a table:** when the task is understanding event order rather than comparing attributes, try chronological activity with clear timestamps and a detail drawer. Keep frequent actions in the primary surface and use search when a selection list becomes long.
- **Pricing lacks context:** keep currency, actual amount, billing interval and recurring commitment together. Show applicable totals and conditions rather than emphasizing a decontextualized small number. Use known costs only; label unknowns.

## Status chips
- **Every status shouts:** first identify which categories change the user's next action. Keep explicit labels for decision-relevant status; reserve strong emphasis for meaningful urgency rather than saturating every chip. Use the system's semantic tokens, and distinguish states through text or other noncolor cues. If a chip merely repeats adjacent information, test plain text or removal while retaining necessary context. Check contrast, similar statuses, color-vision differences and task completion before accepting the quieter treatment.
