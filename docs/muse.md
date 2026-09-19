<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Connect Muse to the CWI Music Catalog — 60-Second Recipe</title>
<meta name="description" content="A 60-second, zero-cost recipe to connect Meta's Muse to the Cumulative Web Inc music catalog as a custom connector. Verified 2026-09-19.">
<style>
  :root { color-scheme: light dark; }
  body { font-family: system-ui, -apple-system, "Segoe UI", sans-serif; line-height: 1.6; max-width: 42rem; margin: 0 auto; padding: 1.5rem; }
  .stamp { border: 2px solid #2e7d32; border-radius: .6rem; padding: 1rem; background: #f1f8f2; }
  .stamp.stale { border-color: #c62828; background: #fdf1f1; }
  .security { border-left: 4px solid #1565c0; padding: .75rem 1rem; background: #eef5fd; }
  .honest { border-left: 4px solid #ef6c00; padding: .75rem 1rem; background: #fff8f0; }
  .dogfood { border-left: 4px solid #6a1b9a; padding: .75rem 1rem; background: #f6effa; }
  code, pre { font-family: ui-monospace, Menlo, Consolas, monospace; font-size: .92em; }
  pre { background: #111; color: #eee; padding: 1rem; border-radius: .5rem; overflow-x: auto; white-space: pre-wrap; }
  .steps li { margin-bottom: .75rem; }
  footer { margin-top: 2rem; font-size: .85em; color: #666; }
</style>
</head>
<body>

<h1>🎵 Connect Muse to the CWI Music Catalog</h1>
<p><strong>The 60-second recipe.</strong> Zero cost. No software to install. A stranger can follow it.</p>

<h2>The steps</h2>
<ol class="steps">
  <li><strong>Open the Muse app</strong> (iOS, Android, or web) and start a new chat.</li>
  <li><strong>Paste this into the chat:</strong>
    <pre>Build a custom connector to the CWI music catalog so you can
answer questions about Cumulative Web Inc's catalog. Read the
connector brief first: https://cumulativewebinc.github.io/cwi-muse-recipe/muse.md
The API is public and needs no credentials. When you fetch catalog
data, use URLs tagged ?src=muse-recipe.</pre>
  </li>
  <li><strong>Let Muse guide you.</strong> Per Meta's Help Center: <em>"ask Muse to create a Custom Connector. Muse will guide you through the process, which can involve retrieving API information from the service."</em> Approve any fetch prompts it shows you.</li>
  <li><strong>No credentials needed.</strong> The catalog API is public and unauthenticated. If Muse asks for an API key, something went wrong — it should never need one. (Meta stores credentials in its Secure Credentials Store; here there is nothing to store.)</li>
  <li><strong>Try it:</strong> ask Muse <em>"Which tracks are in the CWI catalog?"</em> It should fetch <a href="https://cumulativewebinc.github.io/cwi-learn/catalog.json?src=muse-recipe">catalog.json</a> and answer from the data.</li>
  <li><strong>Done.</strong> You can also just ask Muse anytime: <em>"Connect the CWI catalog custom connector"</em> — it will re-read the brief.</li>
</ol>

<div class="stamp" id="verified-stamp">
  <h2>✅ VERIFIED — 2026-09-19</h2>
  <p><strong>What was verified on 2026-09-19:</strong></p>
  <ul>
    <li>Meta's official custom-connector mechanism, quoted verbatim from Meta's Help Center (<a href="https://www.meta.com/help/1687253048996149">"How Muse works with Connectors"</a>): a custom connector is created by <em>asking Muse</em>; Muse guides the setup and stores credentials in its Secure Credentials Store. This recipe follows that mechanism exactly.</li>
    <li>API behavior: all catalog endpoints answered <strong>HTTP 200</strong> on 2026-09-19 — <code>/openapi.json</code>, <code>/catalog.json</code>, <code>/llms.txt</code>, <code>/graph.json</code>, <code>/kit.json</code>, <code>/.well-known/agent-card.json</code> on <a href="https://cumulativewebinc.github.io/cwi-learn/openapi.json?src=muse-recipe">cumulativewebinc.github.io/cwi-learn</a>.</li>
    <li>OpenAPI 3.0.3 spec parses and enumerates 70+ read-only GET paths; every path is a static file on GitHub Pages.</li>
  </ul>
  <p><strong>What was NOT verified (open item):</strong> the actual in-app click-through — tapping through Muse's setup screens — was <em>not</em> performed. That step requires a live Muse app session, which cannot be run from an agent sandbox. It is <strong>queued for Black's laptop session</strong> and will be recorded here when done.</p>
</div>

<div class="dogfood">
  <h2>🧪 Dogfood status</h2>
  <p>Dogfood-gated: docs-verified ✔ · API-behavior-verified ✔ · in-app click-through ⏳ (needs Black's laptop session). A recipe claiming full end-to-end verification before that click-through is done would be a trust liability — so it says so here, on the page.</p>
</div>

<div class="security">
  <h2>🔒 Security guarantee</h2>
  <ul>
    <li>The catalog API exposes <strong>nothing beyond public catalog data</strong>: track metadata, verified placements, gear registry, datasets. There is no server — the entire API is static files on GitHub Pages, which is physically incapable of writes, logins, or sessions.</li>
    <li>No secret values appear anywhere in this recipe. The API needs <strong>no credentials</strong> (no API keys, no logins, no tokens).</li>
    <li>If any credential is ever required in the future, this recipe requires it to go through <strong>Meta's Secure Credentials Store only</strong> — never pasted into chat.</li>
  </ul>
</div>

<div class="honest">
  <h2>⚠️ Honest labeling — from Meta, verbatim</h2>
  <p><em>"Meta doesn't review custom connectors or how they use your information, so grant access with caution and review the provider's privacy policies."</em> — Meta Help Center, <a href="https://www.meta.com/help/1687253048996149">"How Muse works with Connectors"</a>.</p>
  <p>This is a community-published recipe, not a Meta product. Cumulative Web Inc is not affiliated with Meta.</p>
</div>

<h2>📏 Measurement &amp; kill rule</h2>
<ul>
  <li>Every catalog link from this recipe carries <code>?src=muse-recipe</code> so downstream queries are attributable to it.</li>
  <li><strong>Honest measurement:</strong> a setup that never queries is a zero — the count only includes catalog requests that actually arrived with the tag. Current counting is done by the CWI team; the tag is present in the markup to verify.</li>
  <li><strong>Kill rule:</strong> fewer than 25 attributed catalog queries in 90 days → this lane is killed and the page is taken down. Re-verification every 30 days; if the stamp passes 30 days without re-verification, the page is marked <strong>STALE</strong>.</li>
</ul>

<h2>🔁 Re-verify cadence</h2>
<p>Re-verify every <strong>30 days</strong>: (1) re-check Meta's Help Center text for the custom-connector mechanism — if Meta changed the flow, update or no-ship; (2) re-run the HTTP 200 sweep over all catalog endpoints; (3) update the stamp date or mark STALE on this page. Next due: <strong>2026-10-19</strong>.</p>

<h2>Resources</h2>
<ul>
  <li><a href="https://cumulativewebinc.github.io/cwi-muse-recipe/muse.md?src=muse-recipe">Connector brief for Muse (muse.md)</a></li>
  <li><a href="https://cumulativewebinc.github.io/cwi-learn/openapi.json?src=muse-recipe">Catalog OpenAPI spec</a></li>
  <li><a href="https://cumulativewebinc.github.io/cwi-learn/catalog.json?src=muse-recipe">24-track catalog (JSON)</a></li>
  <li><a href="https://cumulativewebinc.github.io/cwi-learn/llms.txt?src=muse-recipe">Catalog summary (llms.txt)</a></li>
</ul>

<footer>
  Published by Cumulative Web Inc · <a href="https://github.com/CumulativeWebInc/cwi-muse-recipe">source repo</a> · Contact: hp@cumulativeweb.com<br>
  Built 2026-09-19 · $0 · static HTML, no dependencies, no trackers.
</footer>

</body>
</html>
