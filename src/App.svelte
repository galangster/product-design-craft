<script>
  const repository = import.meta.env.VITE_SKILL_REPOSITORY || 'galangster/product-design-craft';
  const command = `npx skills add ${repository || 'YOUR_GITHUB_USERNAME/product-design-craft'}`;
  let status = $state('');
  let copying = $state(false);
  let pressed = $state(false);
  let copied = $state(false);
  async function copyCommand() {
    if (copying) return;
    copying = true;
    status = '';
    copied = false;
    try {
      await navigator.clipboard.writeText(command);
      copied = true;
      status = 'Copied. Paste into your terminal or ask your agent to run it.';
    } catch {
      status = 'Could not copy. Select the command and copy it manually.';
    } finally {
      copying = false;
    }
  }
</script>

<main>
  <header>
    <p class="eyebrow">A skill for your coding agent</p>
    <h1>Product design<br />craft.</h1>
    <p class="intro">Make interfaces clearer.<br />Audit, create, and refine the details.</p>
  </header>
  <section aria-label="Install the skill">
    <p class="instruction">Copy. Paste into your terminal or agent.</p>
    <div class="install">
      <code>{command}</code>
      <button class:pressed onpointerdown={() => pressed = true} onpointerup={() => pressed = false} onpointerleave={() => pressed = false} onpointercancel={() => pressed = false} onclick={copyCommand} disabled={copying}>{copying ? 'Copying…' : copied ? 'Copied' : 'Copy'}</button>
    </div>
    <p class="status" role="status">{status}</p>
    <p class="note">Node.js 22.20+. Choose your agent when prompted.</p>
    {#if !repository}<p class="note">Preview only. Repository is not published yet.</p>{/if}
  </section>
  <footer>
    <a href="/skill/SKILL.md">Read the skill</a>
    <a href="/skill/references/patterns.md">The recipes</a>
    {#if repository}<a href={`https://github.com/${repository}`}>GitHub ↗</a>{/if}
  </footer>
</main>

<style>
  @font-face { font-family: 'Geist Mono'; src: url('/fonts/GeistMono-Regular.woff2') format('woff2'); font-style: normal; font-weight: 400; font-display: swap; }
  :global(*) { box-sizing: border-box; }
  :global(html) { background: #faf9f6; color: #252522; font-family: 'Geist Mono', ui-monospace, monospace; }
  :global(body) { margin: 0; }
  :global(button), :global(a) { -webkit-tap-highlight-color: transparent; }
  main { width: min(100% - 48px, 672px); margin: 0 auto; padding: clamp(64px, 15vh, 160px) 0 56px; }
  .eyebrow { font-size: 12px; line-height: 1.6; margin: 0 0 28px; color: #64645d; }
  h1 { font-size: clamp(38px, 6.6vw, 58px); font-weight: 400; letter-spacing: -0.065em; line-height: 1.08; margin: 0; }
  .intro { font-size: 15px; line-height: 1.8; margin: 28px 0 56px; color: #64645d; }
  .instruction { font-size: 12px; line-height: 1.7; margin: 0 0 12px; }
  .install { display: flex; align-items: center; gap: 16px; border-top: 1px solid #cfcec8; border-bottom: 1px solid #cfcec8; padding: 12px 0; }
  code { flex: 1; min-width: 0; font: inherit; font-size: 13px; line-height: 1.8; overflow-wrap: anywhere; user-select: all; }
  button { font: inherit; font-size: 12px; min-width: 82px; min-height: 44px; border: 1px solid #252522; background: #252522; color: #faf9f6; cursor: pointer; padding: 10px 14px; }
  button { transition: transform 120ms ease-out; }
  button.pressed { transform: scale(0.97); }
  @media (hover: hover) and (pointer: fine) { button:hover { background: #44443e; } }
  @media (prefers-reduced-motion: reduce) { button { transition: none; } button.pressed { transform: none; } }
  button:disabled { cursor: wait; }
  button:focus-visible, a:focus-visible { outline: 2px solid #252522; outline-offset: 5px; }
  .status { margin: 8px 0 0; min-height: 36px; font-size: 11px; line-height: 1.6; }
  .note { margin: 0; color: #64645d; font-size: 11px; line-height: 1.7; }
  footer { display: flex; flex-wrap: wrap; gap: 8px 24px; margin-top: 48px; }
  a { color: #64645d; font-size: 12px; line-height: 1.8; text-underline-offset: 4px; padding: 10px 0; }
  a:hover { color: #252522; }
  @media (max-width: 420px) { main { width: calc(100% - 40px); } .install { gap: 12px; } code { font-size: 12px; } }
</style>
