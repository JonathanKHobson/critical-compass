# Claude Artifact Builder Prompt

Use this when you want Claude to create a shareable Critical Compass web Artifact that mirrors the public landing page.

## Copy-paste prompt for Claude

Copy everything from `BEGIN PROMPT` through `END PROMPT` into Claude.

```text
BEGIN PROMPT

Create a single HTML Artifact for Critical Compass using the artifact source below. Produce the Artifact directly and keep any explanation outside the Artifact minimal.

Purpose:
Critical Compass is a Claude AI plugin that helps nonprofits, advocacy teams, and grant writers pressure-test writing before it goes out.

Download URLs:
- Plugin zip: https://github.com/JonathanKHobson/critical-compass/releases/download/v0.1.0-beta.4/critical-compass-plugin.zip
- Claude Desktop extension: https://github.com/JonathanKHobson/critical-compass/releases/download/v0.1.0-beta.4/critical-compass-0.1.0.mcpb
- Skill: https://github.com/JonathanKHobson/critical-compass/releases/download/v0.1.0-beta.4/critical-compass.skill
- Skill zip: https://github.com/JonathanKHobson/critical-compass/releases/download/v0.1.0-beta.4/skill.zip
- Full release notes: https://github.com/JonathanKHobson/critical-compass/releases/tag/v0.1.0-beta.4

Terminology lock:
- Use "plugin", "plugin zip", "extension", "skill", and "skill / offline fallback".
- Do not use "add-on", "reference file", or "offline reference".
- Do not invent install support for Codex. Keep Codex as a status note only: "Codex support is being confirmed."

Artifact requirements:
- Create a single HTML Artifact.
- Use the exact HTML source below as the Artifact source.
- Preserve the hero, What is Critical Compass section, download cards, decision table, install guide, FAQ, Advanced section, diagnostics prompt, tabs, hash routing, card borders, spacing, and responsive behavior.
- Keep all download buttons linked to the GitHub Release URLs above. Do not change them to local paths.
- Do not add frameworks or external runtime dependencies.

QA checklist:
- Four download actions are visible near the top: plugin, extension, skill, and skill zip.
- The decision table filenames are clickable.
- The skill card includes both critical-compass.skill and skill.zip.
- Codex does not appear as a supported install row or install flow.
- The Advanced download verification section stays collapsed by default.
- The terminology lock is followed.

Artifact source:
BEGIN ARTIFACT SOURCE
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Download Critical Compass</title>
  <link rel="icon" href="data:image/svg+xml,%3Csvg xmlns=%27http://www.w3.org/2000/svg%27 viewBox=%270 0 64 64%27%3E%3Crect width=%2764%27 height=%2764%27 rx=%278%27 fill=%27%23f8fbf9%27/%3E%3Ccircle cx=%2732%27 cy=%2732%27 r=%2723%27 fill=%27none%27 stroke=%27%230f766e%27 stroke-width=%275%27/%3E%3Cpath d=%27M39 14 33 35 15 42l16-14z%27 fill=%27%23d95f43%27/%3E%3C/svg%3E">
  <style>
    :root {
      color-scheme: light;
      --ink: #17211f;
      --muted: #54615e;
      --paper: #f8fbf9;
      --line: #cbd8d3;
      --teal: #0f766e;
      --coral: #d95f43;
      --leaf: #527a39;
      --gold: #b7791f;
    }
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      background: var(--paper);
      color: var(--ink);
      line-height: 1.55;
      letter-spacing: 0;
    }
    header, main, footer { width: min(1040px, calc(100% - 32px)); margin: 0 auto; }
    header { padding: 44px 0 22px; display: grid; gap: 20px; }
    .brand { display: flex; align-items: center; gap: 16px; }
    .brand img { width: 76px; height: 76px; border-radius: 8px; border: 1px solid var(--line); }
    h1 { margin: 0; font-size: 2.25rem; line-height: 1.1; }
    h2 { margin: 0 0 10px; font-size: 1.35rem; }
    p { margin: 0 0 12px; }
    .lead { max-width: 760px; color: var(--muted); font-size: 1.08rem; }
    .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; }
    .card { border: 1px solid var(--line); border-left: 4px solid var(--teal); border-radius: 8px; padding: 20px; background: #fff; }
    .tag { display: inline-block; color: #fff; background: var(--teal); border-radius: 8px; padding: 4px 8px; font-size: .85rem; }
    .button {
      display: inline-block;
      margin: 6px 8px 0 0;
      padding: 10px 13px;
      border-radius: 8px;
      background: var(--teal);
      color: #fff;
      text-decoration: none;
      font-weight: 700;
    }
    .button.secondary { background: var(--coral); }
    .button.ghost { background: var(--leaf); }
    section { padding: 20px 0; }
    ol, ul { padding-left: 22px; }
    code { overflow-wrap: anywhere; }
    details { margin: 12px 0; }
    summary { cursor: pointer; font-weight: 700; }
    table { width: 100%; border-collapse: collapse; font-size: .88rem; }
    td { border-top: 1px solid var(--line); padding: 8px 6px; vertical-align: top; }
    textarea {
      width: 100%;
      min-height: 220px;
      border: 1px solid var(--line);
      border-radius: 8px;
      padding: 12px;
      font: inherit;
      font-size: .9rem;
      resize: vertical;
    }
    .tab-nav {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      padding: 4px 0 14px;
    }
    .tab-nav button {
      border: 1px solid var(--line);
      border-radius: 8px;
      background: #fff;
      color: var(--ink);
      cursor: pointer;
      font: inherit;
      font-weight: 700;
      padding: 9px 12px;
    }
    .tab-nav button[aria-selected="true"] {
      background: var(--teal);
      border-color: var(--teal);
      color: #fff;
    }
    .tab-panel[hidden] { display: none; }
    .tab-panel > .card, .tab-panel > details.card { margin: 0 0 18px; }
    footer { padding: 28px 0 44px; color: var(--muted); }
    .notice { border-left: 4px solid var(--gold); }
  </style>
</head>
<body>
  <header>
    <div class="brand">
      <img alt="Critical Compass badge" src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 120 120'%3E%3Crect width='120' height='120' rx='16' fill='%23f8fbf9'/%3E%3Ccircle cx='60' cy='60' r='44' fill='none' stroke='%230f766e' stroke-width='8'/%3E%3Cpath d='M72 28 62 66 28 78l30-26z' fill='%23d95f43'/%3E%3Cpath d='M48 92 58 54l34-12-30 26z' fill='%23527a39'/%3E%3Ccircle cx='60' cy='60' r='7' fill='%2317211f'/%3E%3C/svg%3E">
      <div>
        <span class="tag">Critical Compass 0.1.0-beta.4</span>
        <h1>Download Critical Compass</h1>
      </div>
    </div>
    <p class="lead">A Claude AI plugin that helps nonprofits, advocacy teams, and grant writers pressure-test their writing before it goes out.</p>
  </header>
  <main>
    <nav class="tab-nav" role="tablist" aria-label="Critical Compass download sections">
      <button id="tab-get-started" role="tab" aria-controls="get-started" aria-selected="true" data-tab-target="get-started">Get Started</button>
      <button id="tab-faq" role="tab" aria-controls="faq" aria-selected="false" data-tab-target="faq">About &amp; FAQ</button>
      <button id="tab-install" role="tab" aria-controls="install" aria-selected="false" data-tab-target="install">Install Guide</button>
      <button id="tab-example" role="tab" aria-controls="example" aria-selected="false" data-tab-target="example">Example</button>
      <button id="tab-advanced" role="tab" aria-controls="advanced" aria-selected="false" data-tab-target="advanced">Advanced</button>
    </nav>

    <section id="get-started" class="tab-panel" role="tabpanel" aria-labelledby="tab-get-started">
      <div class="card">
        <h2>What is Critical Compass?</h2>
        <p>Critical Compass adds a critical thinking layer to Claude. Paste in a draft, a grant narrative, a public statement, or advocacy copy, and it will flag weak claims, assumptions, and language that could undermine your credibility. No API key, no Google account, no technical setup required beyond the one-time install.</p>
      </div>

      <section class="grid">
        <div class="card">
          <h2>Claude Cowork Plugin</h2>
          <p>Best for Claude Cowork or Claude Code. This is the main plugin zip for most users.</p>
          <p><span class="tag">v0.1.0-beta.4</span></p>
          <a class="button" href="https://github.com/JonathanKHobson/critical-compass/releases/download/v0.1.0-beta.4/critical-compass-plugin.zip" download>Download Plugin</a>
          <p><a href="#install-cowork">&rarr; How to install</a></p>
        </div>
        <div class="card">
          <h2>Claude Desktop Extension</h2>
          <p>Best if you use the Claude Desktop app and install extensions through Settings.</p>
          <p><span class="tag">v0.1.0-beta.4</span></p>
          <a class="button secondary" href="https://github.com/JonathanKHobson/critical-compass/releases/download/v0.1.0-beta.4/critical-compass-0.1.0.mcpb" download>Download Extension</a>
          <p><a href="#install-desktop">&rarr; How to install</a></p>
        </div>
        <div class="card">
          <h2>Skill / Offline Fallback</h2>
          <p>Use this if the plugin or extension is not available in your Claude setup.</p>
          <p><span class="tag">v0.1.0-beta.4</span></p>
          <a class="button ghost" href="https://github.com/JonathanKHobson/critical-compass/releases/download/v0.1.0-beta.4/critical-compass.skill" download>Download Skill</a>
          <a class="button ghost" href="https://github.com/JonathanKHobson/critical-compass/releases/download/v0.1.0-beta.4/skill.zip" download>Download Skill Zip</a>
          <p><a href="#install-skill">&rarr; How to install</a></p>
        </div>
      </section>

      <div class="card">
        <h2>Start Here: Pick Your Path</h2>
        <table>
          <tr><td><strong>I use Claude Cowork or Claude Code</strong></td><td>Download <a href="https://github.com/JonathanKHobson/critical-compass/releases/download/v0.1.0-beta.4/critical-compass-plugin.zip" download><code>critical-compass-plugin.zip</code></a></td></tr>
          <tr><td><strong>I use Claude Desktop</strong></td><td>Download <a href="https://github.com/JonathanKHobson/critical-compass/releases/download/v0.1.0-beta.4/critical-compass-0.1.0.mcpb" download><code>critical-compass-0.1.0.mcpb</code></a></td></tr>
          <tr><td><strong>I only want the skill / offline fallback</strong></td><td>Download <a href="https://github.com/JonathanKHobson/critical-compass/releases/download/v0.1.0-beta.4/critical-compass.skill" download><code>critical-compass.skill</code></a> or <a href="https://github.com/JonathanKHobson/critical-compass/releases/download/v0.1.0-beta.4/skill.zip" download><code>skill.zip</code></a></td></tr>
        </table>
        <p><strong>You only need one file.</strong> Pick the row that matches how you use Claude.</p>
        <p>Using Codex? See the FAQ tab for status.</p>
      </div>
    </section>

    <section id="example" class="tab-panel" role="tabpanel" aria-labelledby="tab-example" hidden>
      <div class="card">
        <h2>Example</h2>
        <p>See what a finished Critical Compass audit can look like.</p>
        <p>This public example is redacted to protect unpublished source material.</p>
      </div>
      <div class="card">
        <h2>Finished Audit Snapshot</h2>
        <p><strong>Verdict:</strong> Moderate Integrity · <strong>Score:</strong> 71/100</p>
        <p>The example shows how Critical Compass turns a draft into a reader-ready pressure test: plain-language risk summary, evidence gaps, missing voices, assumptions, reasoning traps, and concrete next steps.</p>
        <ul>
          <li>Flags claims that need stronger evidence before publication.</li>
          <li>Names missing stakeholder perspectives and framing limits.</li>
          <li>Separates check-worthy claims from claims that are actually false.</li>
          <li>Gives revision prompts that help strengthen the text without flattening its purpose.</li>
        </ul>
        <a class="button" href="examples/critical-compass-example-report.html" target="_blank" rel="noopener">Open HTML Example (new tab)</a>
        <a class="button secondary" href="examples/critical-compass-example-report.pdf" download>Download PDF Example</a>
        <a class="button ghost" href="examples/critical-compass-example-report.md" target="_blank" rel="noopener">View Markdown Example (new tab)</a>
      </div>
    </section>

    <section id="install" class="tab-panel" role="tabpanel" aria-labelledby="tab-install" hidden>
      <details id="install-cowork" class="card">
        <summary>Claude Cowork or Claude Code</summary>
        <ol>
          <li>Download <code>critical-compass-plugin.zip</code>.</li>
          <li>Open Claude Cowork or Claude Code.</li>
          <li>Click <strong>Customize</strong> in the left sidebar.</li>
          <li>Under <strong>Personal Plugins</strong>, click the <strong>+</strong> button.</li>
          <li>Hover over <strong>Create Plugin</strong>, then click <strong>Upload Plugin</strong>.</li>
          <li>Drag the zip file into the upload area.</li>
          <li>Done. Critical Compass is now active in your session.</li>
        </ol>
      </details>

      <details id="install-desktop" class="card">
        <summary>Claude Desktop</summary>
        <ol>
          <li>Download <code>critical-compass-0.1.0.mcpb</code>.</li>
          <li>Open the Claude Desktop app.</li>
          <li>Go to <strong>Settings</strong> &rarr; <strong>Extensions</strong>.</li>
          <li>Drag the downloaded file into the Extensions panel.</li>
          <li>A security warning will appear. This is expected; see the FAQ tab for why.</li>
          <li>Done.</li>
        </ol>
      </details>

      <details id="install-skill" class="card">
        <summary>Skill / Offline Fallback</summary>
        <ol>
          <li>Download <code>critical-compass.skill</code> or <code>skill.zip</code>. Either works.</li>
          <li>Open Claude or Claude Code.</li>
          <li>Go to <strong>Skills</strong>, then click the <strong>+</strong> button.</li>
          <li>Hover over <strong>Create Skill</strong>, then click <strong>Upload Skill</strong>.</li>
          <li>Drag in your downloaded file.</li>
          <li>Done. Use this if the plugin or extension is not available.</li>
        </ol>
      </details>

      <section class="card notice">
        <h2>If Install Fails</h2>
        <p>Use the diagnostics prompt in the Advanced tab before editing any files manually.</p>
      </section>
    </section>

    <section id="faq" class="tab-panel" role="tabpanel" aria-labelledby="tab-faq" hidden>
      <div class="card">
        <h2>What does Critical Compass actually do?</h2>
        <p>Critical Compass is a reasoning layer, not a spell-checker. It asks the hard questions your reader may ask about evidence quality, claim strength, hidden assumptions, framing bias, missing voices, and language that could overstate your case.</p>
      </div>
      <div class="card">
        <h2>Who is it for?</h2>
        <p>It is for nonprofits, grant writers, advocacy communicators, policy teams, public affairs staff, and anyone who submits, publishes, or presents written work that needs to hold up under scrutiny.</p>
      </div>
      <div class="card">
        <h2>Do I need to install all three files?</h2>
        <p>No. Install one. The Claude Cowork plugin, the Claude Desktop extension, and the skill are three delivery methods for the same tool. Pick the one that matches your Claude setup.</p>
      </div>
      <div class="card">
        <h2>Does this work with Codex?</h2>
        <p>Codex support is being confirmed. We're verifying the install path before publishing instructions. Check back soon or open a GitHub issue to be notified.</p>
      </div>
      <div class="card">
        <h2>Why does Claude show a warning during install?</h2>
        <p>Claude flags locally distributed plugins as unverified because they are not listed in an official marketplace. This is expected behavior for developer-distributed tools. Install only if you trust the source.</p>
      </div>
      <div class="card">
        <h2>Do I need a GitHub account to download?</h2>
        <p>No. The download buttons go directly to the files. GitHub is only where the files are hosted.</p>
      </div>
    </section>

    <section id="advanced" class="tab-panel" role="tabpanel" aria-labelledby="tab-advanced" hidden>
      <div class="card">
        <h2>Advanced</h2>
        <p>This section is for IT reviewers, security-conscious users, and anyone troubleshooting installation.</p>
        <p><a class="button" href="https://github.com/JonathanKHobson/critical-compass/releases/tag/v0.1.0-beta.4">View full release notes</a></p>
        <p><a class="button ghost" href="claude-artifact-builder-prompt.md">Create a Claude Artifact version</a></p>
        <details>
          <summary>Advanced: Verify Download</summary>
          <p>These SHA-256 checksums help technical reviewers confirm that downloaded files match this release.</p>
          <table><tr><td>critical-compass-0.1.0.mcpb</td><td><code>46e5283f172705eee278ad1df9d6051f0e06004038423b7389b39e7ffb211ee3</code></td></tr>
<tr><td>critical-compass-plugin.zip</td><td><code>685f9fff98d193677f44a904b8788a6316bbef1036053b4c735fd4a1cb723874</code></td></tr>
<tr><td>critical-compass.skill</td><td><code>4bdcb83b25367a18cd321a81bf63c99c2b6e00f989f9921187632cf07a95f9cf</code></td></tr>
<tr><td>skill.zip</td><td><code>afcb323c8c1f015b6821411abf0ce966f3e06c1737ec748e8b1204073988f085</code></td></tr></table>
        </details>
      </div>
      <div class="card">
        <h2>Diagnostics Prompt</h2>
        <p>If installation fails, copy this prompt into Claude, Claude Code, or Codex and attach the file you tried to install.</p>
        <button class="button" type="button" id="copy-diagnostics">Copy diagnostics prompt</button>
        <textarea id="diagnostics-prompt" readonly># Critical Compass MCPB Installer / Diagnostic Prompt

Paste this into Claude, Claude Code, Codex, or another capable coding assistant when you want help installing or diagnosing Critical Compass.

```text
You are helping me install or diagnose the Critical Compass MCPB/Desktop Extension in Claude Desktop.

Goal:
- Get Critical Compass installed and visible as an MCP server/tool set.
- Do not delete or overwrite any existing Claude Desktop MCP configuration.
- Preserve unrelated MCP servers and settings.
- Prefer MCPB/Desktop Extension installation over manual JSON editing.

Context:
- The package file should be named like critical-compass-0.1.0.mcpb.
- Critical Compass is a local MCP server for pressure-testing text before use.
- It should expose tools such as get_started, critical_compass_overview, quick_scan, audit_text, claim_stress_test, factcheck_lookup, and generate_audit_report.
- factcheck_lookup is scaffold-first by default; it does not require Google, Brave, API keys, or live retrieval.

Steps:
1. Confirm Claude Desktop supports Extensions or MCPB/Desktop Extensions.
2. Help me install the .mcpb through Claude Desktop Settings &gt; Extensions.
3. Restart Claude Desktop if needed.
4. Check whether Critical Compass appears in the available MCP tools.
5. Run a small smoke prompt:
   &quot;Call get_started for Critical Compass and tell me the first five-minute path.&quot;
6. If it fails, diagnose in this order:
   - Is the .mcpb file present and not still zipped inside another archive?
   - Is Claude Desktop updated enough to show Settings &gt; Extensions?
   - Did UV dependency setup fail on first launch?
   - Are there Claude Desktop MCP logs showing a process launch error?
   - Are writable files being redirected to user app data rather than the extension folder?
   - Is any failure specific to PDF rendering or OCR rather than the core audit tools?

Safety rules:
- Do not add Google/Brave/provider keys unless I explicitly ask.
- Do not claim factcheck_lookup performed retrieval unless lookup_performed=true.
- Do not treat &quot;no match&quot; as true or false.
- Do not merge, install, or call third-party MCPs while diagnosing this install.
- If manual config inspection is needed, read the current config first and preserve all existing entries.

Expected result:
- Critical Compass is installed.
- get_started and critical_compass_overview work.
- If a feature is unavailable, explain whether it is an install issue, dependency issue, renderer/OCR limitation, or normal scaffold-first behavior.
```

</textarea>
      </div>
    </section>
  </main>
  <footer>
    <p>Fact-checking is scaffold-first by default: no Google, Brave, or provider key is required.</p>
  </footer>
  <script>
    const tabButtons = Array.from(document.querySelectorAll("[data-tab-target]"));
    const tabPanels = Array.from(document.querySelectorAll(".tab-panel"));
    const installAnchorIds = new Set(["install-cowork", "install-desktop", "install-skill"]);

    function showTab(tabId, updateHash = true) {
      const targetPanel = document.getElementById(tabId) || document.getElementById("get-started");
      tabButtons.forEach((button) => {
        const selected = button.dataset.tabTarget === targetPanel.id;
        button.setAttribute("aria-selected", String(selected));
      });
      tabPanels.forEach((panel) => {
        panel.hidden = panel.id !== targetPanel.id;
      });
      if (updateHash) {
        history.replaceState(null, "", "#" + targetPanel.id);
      }
    }

    function routeHash(updateHash = false) {
      const hash = window.location.hash.replace("#", "");
      const panelId = installAnchorIds.has(hash) ? "install" : (hash || "get-started");
      showTab(panelId, updateHash);
      if (installAnchorIds.has(hash)) {
        const target = document.getElementById(hash);
        if (target) {
          target.open = true;
          window.requestAnimationFrame(() => {
            target.scrollIntoView({ behavior: "smooth", block: "start" });
          });
        }
      }
    }

    tabButtons.forEach((button) => {
      button.addEventListener("click", () => showTab(button.dataset.tabTarget));
    });

    window.addEventListener("hashchange", () => {
      routeHash(false);
    });

    const installSteps = Array.from(document.querySelectorAll("#install details"));
    const openInstallStepsOnMobile = () => {
      const openOnMobile = window.matchMedia("(max-width: 720px)").matches;
      installSteps.forEach((details) => {
        details.open = openOnMobile;
      });
    };
    openInstallStepsOnMobile();
    routeHash(false);

    const copyButton = document.getElementById("copy-diagnostics");
    const diagnosticsPrompt = document.getElementById("diagnostics-prompt");
    if (copyButton && diagnosticsPrompt) {
      copyButton.addEventListener("click", async () => {
        diagnosticsPrompt.select();
        try {
          await navigator.clipboard.writeText(diagnosticsPrompt.value);
          copyButton.textContent = "Copied";
        } catch (_error) {
          document.execCommand("copy");
          copyButton.textContent = "Copied";
        }
      });
    }
  </script>
</body>
</html>

END ARTIFACT SOURCE

END PROMPT
```
