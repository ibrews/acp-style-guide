# Alex Coulombe Presents house style

The shared house style for every repository published by [Alex Coulombe
Presents](https://github.com/ibrews) — UnRealityKit, UnrealRenderManBridge, Forage, and
everything after them. It makes the practices already visible in those repos repeatable; it is
not a new marketing voice, and it is not owned by any one product. Covers written conventions
(attribution, README structure, voice) and, as of 2026-08-10, the one shared visual brand mark
(`branding/`) and how to bring it into a new tool — Unreal plugin or otherwise.

**Source pattern.** UnRealityKit's README and roadmap lead with a concrete architecture, runnable
paths, measured evidence, dates, and open gates. UnrealRenderManBridge uses the same pattern for
coverage, render checks, and material limitations. Existing `Things to Try` sections turn a claim
into a command, editor action, or artifact someone can inspect. This guide makes that pattern
explicit and portable across products.

## Attribution and credits

Repositories under `github.com/ibrews` credit the publisher as **Alex Coulombe Presents**. Do not
use bare "Alex Coulombe" for a repository, product, plugin listing, copyright notice, or public
documentation credit.

Use this default credits block at the end of a root README, after License / commercial terms:

```md
## Credits

Built by **Alex Coulombe Presents** ([ibrews](https://github.com/ibrews)).
```

Add one concise factual sentence beneath it only when a lineage or research predecessor matters:

```md
Distilled from the private UnrealRealityKitBridge research line.
```

For a license that requires a copyright notice, use `Copyright (c) YEAR Alex Coulombe Presents.`
Product names, individual contributors, and external licensors retain their accurate names; this
rule does not rewrite an external API, license, or a person's byline.

## Support

Repos that are real, standalone products or tools — not scratch repos, demos, forks of someone
else's project, or internal-only tooling — end with a one-line donation nudge directly above the
Credits block, pointing at the same Stripe-backed flow used sitewide on alexcoulombepresents.com:

```md
## Support

If you like seeing this kind of thing get built and shared, [donations are always welcome](https://www.alexcoulombepresents.com/support) — they buy hardware, render time, and the freedom to keep giving most of this away.

## Credits

Built by **Alex Coulombe Presents** ([ibrews](https://github.com/ibrews)).
```

Skip it on scratch/test repos, demo/sample projects, forks, and anything under the `agilelens`
org — donations are a personal-brand ask, not a studio one, and a fork shouldn't solicit money on
someone else's work.

## README order

Root READMEs use this order when each section is relevant:

1. `# Product name`
2. A one- or two-sentence outcome and the primary technical distinction.
3. A plainly labeled beta, licensing, or scope constraint if it changes whether someone should try
   the product.
4. `Why`, architecture, or layout—the minimum context needed to evaluate the result.
5. Prerequisites and Quickstart.
6. `## Things to Try`.
7. Status, known limitations, lineage, and related/shared work.
8. License / commercial terms.
9. `## Support`, on real standalone products only (see above).
10. `## Credits` using the block above.

Do not add empty headings to satisfy the template. A focused plugin README can omit architecture
or lineage; a research repository can put the private-R&D boundary directly under the summary.
Keep the executable path before deep implementation detail, and keep the credits block at the
bottom rather than interrupting the technical opening.

## Voice and evidence

- State the mechanism, scope, and observed result. Prefer "32 frames at 24 fps, verified
  2026-07-29" to "fast, production-ready animation."
- Give a number only with its unit, subject, and measurement context. Link the harness, report, or
  reproducible command when it helps a reader check the claim.
- Separate **proven**, **designed**, **open**, **blocked**, and **deferred**. A checkbox changes to
  `[x]` only after the stated gate has actually passed; a repaired defect is not a deliverable until
  its regression/verification proves it.
- Describe defects by their reproducible condition, observed signal, and verified resolution. Do
  not assert that something is "fixed" without saying what now passes or what output changed.
- Name constraints early: stock-vs-patched engine, simulator-vs-device, license/signing, and
  content limits. "Not supported yet" is more useful than an implied promise.
- Use direct, technical American English: `color`, `behavior`, `center`, `license`, and `optimize`.
  Avoid generic superlatives such as "seamless," "powerful," or "best-in-class."

## The `Things to Try` section

Place `## Things to Try` after Quickstart / prerequisites and before status or deep reference
material. It is a numbered set of independently useful checks, not a feature list.

Each item follows the established pattern:

```md
1. **Action-oriented title** — exact command or editor path; required environment or input;
   observable success signal, output artifact, or deliberate failure condition.
```

Lead with the safest useful path. State costly prerequisites (`needs RenderMan`, `no UE`, `booted
AVP simulator`) inline. Prefer an emitted verdict, log line, report, or named output over "it
works." When an item exposes a known limitation, name the expected limitation and the comparison
that demonstrates it.

## Unreal plugin listing metadata

`CreatedBy` for an ibrews plugin is exactly:

```json
"CreatedBy": "Alex Coulombe Presents"
```

Write `Description` as one or two compact, factual sentences:

1. State the user-visible outcome and product surface.
2. State the primary workflow plus stock dependencies or a material scope boundary.

Use present tense and the names users see in the editor. For example:

```text
Preview a live Unreal Editor scene in a visionOS RealityKit viewer. Export visible static meshes
and baked materials to USD, then activate stock Remote Control for live transforms; requires only
Unreal's Python, Remote Control, and USD Importer plugins.
```

Do not turn a listing description into a changelog, make performance or compatibility claims it
does not substantiate, or mention internal tooling that is not a shipped dependency.

## Visual identity

There is one ACP brand mark — a marquee sign with a spark, in a fixed gradient — and it is
square/compact by design so it survives being shrunk to a 16px menu row. Products do not design
their own icon; they take this one.

**The mark.** Rounded-square dark chip (`#07070f`), a lighter inset panel with a row of small dot
"bulbs," and a horizontal gradient pill through the center holding a four-point spark. Gradient,
left to right: `#2dd4bf` (teal) → `#a78bfa` (purple) → `#fbbf24` (amber). Canonical source: the
live favicon at [alexcoulombepresents.com](https://www.alexcoulombepresents.com) (`app/icon.svg`
in the `alexcoulombepresents` site repo) — that is the actual production mark, not a proposal.
This repo mirrors it so every product has one public, always-reachable copy to build from, whether
or not the site repo itself is reachable from wherever a given tool is being built:

```
branding/icon.svg           Source vector — regenerate any size from this, don't re-derive the design.
branding/ACPIcon_16.png     Menu-row icon size.
branding/ACPIcon_20.png     Small toolbar icon size.
branding/ACPIcon_40.png     Standard toolbar button size.
branding/ACPIcon_64.png     Mid-size UI icon.
branding/ACPIcon_128.png    Plugin-listing / large-UI icon size.
branding/ACPIcon_256.png    App-icon intermediate size.
branding/ACPIcon_512.png    App-icon intermediate size.
branding/ACPIcon_1024.png   App Store / largest app-icon size.
```

**Usage rules.**
- Never hand-scale a small PNG up — regenerate from `icon.svg` at the exact size needed
  (`rsvg-convert -w N -h N branding/icon.svg -o out.png`, or an equivalent SVG renderer).
- Never recolor the gradient, redraw the mark, or add a wordmark variant without checking with
  Alex first — this is the one house mark, the same way there is one Attribution rule above.
- A product-specific icon (e.g. a distinct app icon for a standalone macOS/iOS app) is a real,
  separate design decision, not something to improvise from this mark — raise it explicitly rather
  than silently diverging.

**Onboarding a new tool — pick the lane that matches what you're building:**

1. **Unreal Engine plugin.** Follow `acp-dist-tools`' own README, "Onboarding a new plugin" and
   "The shared ACP toolbar/menu launcher" sections (`/Users/Shared/GH/acp-dist-tools`, local-only,
   never pushed — ask Alex for access if you don't have this checkout). That repo is the full
   technical integration: ACPL2 licensing, background update-checks, and — as of 2026-08-10 — a
   shared "Alex Coulombe Presents" toolbar/menu entry point that lists every installed ACP plugin
   in one place instead of N unrelated per-plugin menus (`native/ACPMenu.h`/`.cpp` for compiled
   plugins, `python/acp_menu.py` for content-only ones). Its own `sync_dist_tools.sh` vendors the
   icon PNGs above into the plugin's `Resources/` folder as part of that same onboarding step —
   don't copy them by hand into a UE plugin; let the sync script do it so the provenance stamp
   stays accurate.
2. **Anything else — CLI, web app, editor/IDE extension, mobile app, desktop app.** There is no
   shared vendoring script for non-UE tools yet; do this by hand:
   - Pull the icon from `branding/` above at whatever size(s) your platform needs (app icon,
     favicon, tray icon, etc.) — regenerate from `icon.svg`, don't reuse a UE-sized PNG for an
     unrelated context without checking it still reads clearly at the new size.
   - Apply this guide's Attribution, README order, and Voice sections the same as any other ibrews
     repo — those rules are not UE-specific.
   - If the tool has its own "about"/settings surface, a version-with-support-link mention (in the
     spirit of `acp_update_check.py`'s background update-check, even without adopting the full
     ACPL2 machinery) keeps the experience consistent with the UE plugins' — optional, not
     required, for a non-UE tool.
   - **If the tool wants ACPL2-style paid licensing** (tiers, trials, per-recipient license
     files): that's a real gap today — `acp-dist-tools`' checker templates are Python and native
     C++ only, tied to how the UE plugins ship. A CLI in Node/TypeScript or a Swift Mac app needs
     its own checker implementing the same `ACPL2|product|licensee|email|tier|seats|expiry|
     signature` format and HMAC-SHA256 signature scheme (see `acp-dist-tools/README.md`'s "The
     ACPL2 license format" and "Checker contract" sections for the exact contract to port), not a
     direct vendor of the existing templates. Flag this to whoever's extending `acp-dist-tools`
     rather than inventing a parallel licensing scheme per product.

## Things to Try

1. **Check a repo's attribution** — `grep -rn "Alex Coulombe" <repo> | grep -v "Alex Coulombe Presents"`
   in any `ibrews` repo. A hit is a violation of the Attribution section above; fix it in place.
2. **Check a README's section order** — open any `ibrews` repo's root `README.md` and compare its
   heading order against the README order list above. A `## Credits` block anywhere but the very
   end is a violation.
3. **Audit a UE plugin listing** — open the `.uplugin` file and confirm `CreatedBy` is exactly
   `"Alex Coulombe Presents"` and `Description` follows the two-sentence pattern above, not a
   changelog or an unsubstantiated claim.
4. **Point a new repo at this guide** — add a line like `Docs written to
   [Alex Coulombe Presents house style](https://github.com/ibrews/acp-style-guide).` to a new
   product's `CONTRIBUTING.md` or docs index rather than forking this content.
5. **Check a repo's Support section** — for a real standalone product repo (not scratch, demo,
   fork, or internal-only), confirm it has the `## Support` block directly above Credits, linking
   to https://www.alexcoulombepresents.com/support. Skip this check for `agilelens`-org repos.
6. **Regenerate an icon size and eyeball it small** — `rsvg-convert -w 16 -h 16 branding/icon.svg
   -o /tmp/acp16.png`, then open it at 100%. If the mark reads as a muddy blob rather than a
   recognizable dark chip with a bright center, something about the target context (a busy toolbar,
   a dark-on-dark theme) needs a different size from this list, not a redrawn mark.
7. **Diff a vendored icon against the canonical one** — for any product that copied `branding/`
   into its own repo (rather than depending on `acp-dist-tools`' sync script to do it), confirm its
   copy is byte-identical: `shasum branding/ACPIcon_128.png` here vs. the same command in the
   product repo. A silent divergence means someone hand-edited or regenerated it differently.

## Adoption

This is the single shared source — every `ibrews` product links here rather than forking or
duplicating this content. Product-specific facts (architecture, prerequisites, licensing terms)
stay in each product's own repository; only the cross-product conventions live here. If a
product's needs genuinely diverge from this guide, that's a signal to open an issue/PR here and
update the guide for everyone, not to quietly drift in one repo.

## Credits

Built by **Alex Coulombe Presents** ([ibrews](https://github.com/ibrews)).
