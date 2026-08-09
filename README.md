# Alex Coulombe Presents house style

The shared house style for every repository published by [Alex Coulombe
Presents](https://github.com/ibrews) — UnRealityKit, UnrealRenderManBridge, Forage, and
everything after them. It makes the practices already visible in those repos repeatable; it is
not a new marketing voice, and it is not owned by any one product.

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
9. `## Credits` using the block above.

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

## Adoption

This is the single shared source — every `ibrews` product links here rather than forking or
duplicating this content. Product-specific facts (architecture, prerequisites, licensing terms)
stay in each product's own repository; only the cross-product conventions live here. If a
product's needs genuinely diverge from this guide, that's a signal to open an issue/PR here and
update the guide for everyone, not to quietly drift in one repo.

## Credits

Built by **Alex Coulombe Presents** ([ibrews](https://github.com/ibrews)).
