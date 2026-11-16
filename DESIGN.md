# Design

Nick requested ULTRA MINIMAL, Geist Mono and a copy-first hierarchy on November 16, 2026.

Warm white, near-black type and one narrow column. All type is 12–14px. The installation command and Copy button are primary. A small product identifier, Node prerequisite and two source links support that action. No display headline, eyebrow, tagline, cards, gradient, badges or illustration.

Motion uses bounded state feedback: pointer press at 90ms and release at 160ms on the canonical easing, scale .98; persistent layered copy/check icons cross-fade and scale over 240ms with a firm ease-out. Keyboard activation remains immediate. Reduced motion removes the transition and scale. No entrance sequence, bouncing icon, spinner or layout animation. Copy uses a familiar duplicate-sheets icon and switches to a checkmark after clipboard success. Its accessible name and live status confirm the outcome without permanent explanatory copy. Clipboard failure displays recovery instructions. Supporting directions match the 13px product identifier; text-size-adjust prevents mobile paragraph inflation. The button has a fixed 44px footprint. Recopy keeps the check visible while pending; one owned 1800ms reset timer restarts on success and is cleared before another attempt and on unmount. Keyboard activation and reduced motion disable icon transitions. No initial animation.


## Focus and press update

Based on the current Merlin 3 working candidate (3.0.0, source commit 70ec35d), following ratified decisions rather than stale prototype CSS. No package dependency or broad restyle was introduced.

Focus changes the control itself, instantly, without an external ring. The filled icon button uses a short white underline beneath its glyph (the icon-only adaptation of the filled-label underline); text links darken to ink with a stronger underline. Forced colors use system Highlight. Press is scale .98 with ink fill #181818, 90ms in and 160ms release on the canonical easing. Reduced motion removes scaling and transitions; keyboard copy stays immediate. Existing stable clipboard state and icon feedback are unchanged.
