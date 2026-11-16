<script>
  const repository = 'galangster/product-design-craft';
  const command = `npx skills add ${repository}`;
  let status = $state('Paste into your terminal, or ask your agent to run it.');
  let copying = $state(false);
  let pressed = $state(false);
  let copied = $state(false);
  async function copyCommand() {
    if (copying) return;
    copying = true;
    status = 'Copying…';
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
  <h1>product-design-craft</h1>
  <section aria-label="Install the skill">
    <div class="install">
      <code>{command}</code>
      <button class:pressed onpointerdown={() => pressed = true} onpointerup={() => pressed = false} onpointerleave={() => pressed = false} onpointercancel={() => pressed = false} onclick={copyCommand} disabled={copying}>{copying ? 'Copying…' : copied ? 'Copied' : 'Copy'}</button>
    </div>
    <p class="status" role="status">{status}</p>
    <p class="note">Requires Node.js 22.20+.</p>
  </section>
  <footer>
    <a href="/skill/SKILL.md">Read the skill</a>
    <a href={`https://github.com/${repository}`}>GitHub</a>
  </footer>
</main>

<style>
  @font-face { font-family: 'Geist Mono'; src: url('/fonts/GeistMono-Regular.woff2') format('woff2'); font-style: normal; font-weight: 400; font-display: swap; }
  :global(*) { box-sizing: border-box; }
  :global(html) { background: #faf9f6; color: #252522; font-family: 'Geist Mono', ui-monospace, monospace; }
  :global(body) { margin: 0; }
  main { width: min(100% - 40px, 640px); margin: 0 auto; padding: clamp(64px, 25vh, 220px) 0 48px; }
  h1 { font: inherit; font-size: 13px; line-height: 1.7; font-weight: 400; margin: 0 0 20px; color: #64645d; }
  .install { display: flex; align-items: center; gap: 16px; border: 1px solid #cfcec8; padding: 8px 8px 8px 16px; }
  code { flex: 1; min-width: 0; font: inherit; font-size: 14px; line-height: 1.7; overflow-wrap: anywhere; user-select: all; }
  button { font: inherit; font-size: 13px; min-width: 82px; min-height: 44px; border: 1px solid #252522; background: #252522; color: #faf9f6; cursor: pointer; padding: 10px 12px; transition: transform 120ms ease-out; }
  button.pressed { transform: scale(0.97); }
  @media (hover: hover) and (pointer: fine) { button:hover { background: #44443e; } }
  @media (prefers-reduced-motion: reduce) { button { transition: none; } button.pressed { transform: none; } }
  button:disabled { cursor: wait; }
  button:focus-visible, a:focus-visible { outline: 2px solid #252522; outline-offset: 4px; }
  .status { margin: 12px 0 0; min-height: 42px; font-size: 12px; line-height: 1.7; color: #64645d; }
  .note { margin: 0; color: #64645d; font-size: 12px; line-height: 1.7; }
  footer { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; }
  a { color: #64645d; font-size: 12px; line-height: 1.7; text-underline-offset: 4px; padding: 10px 0; }
  a:hover { color: #252522; }
  @media (max-width: 420px) { .install { gap: 12px; padding-left: 12px; } code { font-size: 13px; } }
</style>
