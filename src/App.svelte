<script>
  import { onDestroy } from 'svelte';
  let resetTimer;
  let mounted = true;
  onDestroy(() => { mounted = false; clearTimeout(resetTimer); });
  const repository = 'galangster/product-design-craft';
  const command = `npx skills add ${repository}`;
  let status = $state('');
  let failed = $state(false);
  let copying = $state(false);
  let pressed = $state(false);
  let copied = $state(false);
  let animate = $state(false);
  async function copyCommand(event) {
    if (copying) return;
    copying = true;
    status = 'Copying…';
    failed = false;
    animate = event.detail !== 0;
    clearTimeout(resetTimer);
    try {
      await navigator.clipboard.writeText(command);
      if (!mounted) return;
      copied = true;
      resetTimer = setTimeout(() => { copied = false; status = ''; }, 1800);
      status = 'Copied to clipboard.';
    } catch {
      if (!mounted) return;
      copied = false;
      failed = true;
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
      <button class:pressed class:copied class:animate onpointerdown={() => pressed = true} onpointerup={() => pressed = false} onpointerleave={() => pressed = false} onpointercancel={() => pressed = false} onclick={copyCommand} disabled={copying} aria-label={copying ? 'Copying command' : copied ? 'Command copied' : 'Copy install command'} title={copied ? 'Copied' : 'Copy command'}>
        <span class="icons" aria-hidden="true">
          <svg class="copy-icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="8" y="8" width="12" height="12" rx="2" /><path d="M16 8V4a1 1 0 0 0-1-1H4a1 1 0 0 0-1 1v11a1 1 0 0 0 1 1h4" /></svg>
          <svg class="check-icon" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="m5 12 4 4L19 6" /></svg>
        </span>
      </button>
    </div>
    <p class="status" class:sr-only={!failed} role="status">{status}</p>
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
  :global(html) { background: #faf9f6; color: #252522; font-family: 'Geist Mono', ui-monospace, monospace; -webkit-text-size-adjust: 100%; text-size-adjust: 100%; }
  :global(body) { margin: 0; }
  main { width: min(100% - 40px, 640px); margin: 0 auto; padding: clamp(64px, 25vh, 220px) 0 48px; }
  h1 { font: inherit; font-size: 13px; line-height: 1.7; font-weight: 400; margin: 0 0 20px; color: #64645d; }
  .install { display: flex; align-items: center; gap: 16px; border: 1px solid #cfcec8; padding: 8px 8px 8px 16px; }
  code { flex: 1; min-width: 0; font: inherit; font-size: 14px; line-height: 1.7; overflow-wrap: anywhere; user-select: all; }
  button { font: inherit; font-size: 13px; display: grid; place-items: center; width: 44px; min-width: 44px; flex: 0 0 44px; min-height: 44px; border: 1px solid #252522; background: #060606; color: #ffffff; cursor: pointer; padding: 0; transition: transform 160ms cubic-bezier(0.23, 1, 0.32, 1), background-color 160ms cubic-bezier(0.4, 0, 0.6, 1); }
  .icons { position: relative; display: block; width: 18px; height: 18px; }
  .icons svg { display: block; transform: scale(1); opacity: 1; }
  .animate .icons svg { transition: transform 240ms cubic-bezier(0.25, 0.1, 0, 1), opacity 240ms cubic-bezier(0.25, 0.1, 0, 1); }
  .check-icon { position: absolute; inset: 0; }
  .icons .check-icon, .copied .copy-icon { transform: scale(0.3); opacity: 0; }
  .copied .check-icon { transform: scale(1); opacity: 1; }
  @media (prefers-reduced-motion: reduce) { .animate .icons svg { transition: none; } }
  button.pressed { transform: scale(0.98); background: #181818; transition-duration: 90ms; }
  @media (hover: hover) and (pointer: fine) { button:hover { background: #181818; } }
  @media (prefers-reduced-motion: reduce) { button { transition: none; } button.pressed { transform: none; } }
  button:disabled { cursor: wait; }
  button:focus-visible, a:focus-visible { outline: none; }
  button:focus-visible:active:not(.pressed) { background: #181818; transition: none; }
  button:focus-visible .icons::after { content: ''; position: absolute; left: 0; right: 0; bottom: -5px; height: 2px; background: currentColor; }
  a:focus-visible { color: #060606; text-decoration-color: #060606; text-decoration-thickness: 2px; }
  @media (forced-colors: active) { button:focus-visible { border-color: Highlight; } button:focus-visible .icons::after { background: Highlight; } a:focus-visible { color: LinkText; text-decoration-color: Highlight; } }
  .sr-only { position: absolute; width: 1px; height: 1px; padding: 0; margin: -1px; overflow: hidden; clip-path: inset(50%); white-space: nowrap; border: 0; }
  .status { margin: 12px 0 0; font-size: 13px; line-height: 1.7; color: #64645d; }
  .note { margin: 12px 0 0; color: #64645d; font-size: 13px; line-height: 1.7; }
  footer { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; }
  a { color: #64645d; font-size: 12px; line-height: 1.7; text-underline-offset: 4px; padding: 10px 0; }
  a:hover { color: #252522; }
  @media (max-width: 420px) { .install { gap: 12px; padding-left: 12px; } code { font-size: 13px; } }
</style>
