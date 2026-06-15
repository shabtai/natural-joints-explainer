# Clinical Data — visual assets

Two deliverables in this folder:

- **`index.html`** — the animated, self-advancing **video** (10 slides, screen-record it). Details below.
- **`explainer.html`** — a single-page **illustrated explainer** with hand-drawn diagrams
  (whiteboard/sketch style) that walks the whole solution: messy tabular data →
  the natural-join semantic layer (algorithmic linkage + research semantics) → an AI agent
  emits OMOP/FHIR → research-ready output. (Other modalities go through optional
  transformers → tabular first, shown as an add-on.) One scrollable page.
  - **Export as one image / PDF:** open in Chrome → `Cmd+P` → *Save as PDF* (or use a
    full-page screenshot extension). It's print-styled (animations freeze, white background).

---

# Clinical Data — Capability Brief (animated video)

A self-advancing, customer-facing presentation about your clinical-data practice:
FHIR & OMOP interoperability, data anonymization (structured / tabular),
big-data clinical-research data preparation, data stewardship, and the on-premise
big-data platform.

## Run it
Open `index.html` in any modern browser (Chrome/Edge recommended for recording).
It auto-advances every 10s and loops.

- **→ / ←** next / previous slide
- **Space** play / pause
- **dots** jump to a slide

## The through-line: the **natural join (⋈)**
The whole story is built around one idea: clinical data fails to join because every
source uses different identifiers and code systems. All the work — FHIR/OMOP mapping,
the terminology layer, consistent de-identification — exists so records share keys and
vocabularies and a `NATURAL JOIN` "just works" across sources. Each slide ties back to it.

## Slides (10)
1. Cover — Clinical data, engineered for discovery (joins by design)
2. **The problem** — same patient, three islands, no common key (the join fails)
3. **The idea** — make data *naturally joinable*: shared `person_id` + standard concepts → `NATURAL JOIN`
4. **How the layer is built** *(the pipeline)* — many tabular sources → **NJ builds the semantic layer** (algorithmic linkage + research semantics) → **an AI agent emits OMOP CDM & FHIR**. Text/imaging go through **optional transformers → tabular** first (an add-on, not part of NJ)
5. Interoperability — FHIR & OMOP give every record the same shape (the join key); Clalit work groups
6. Privacy by design — de-identification built for tabular data (direct IDs · quasi-identifiers · stable keys), so private data still joins
7. Data preparation — the terminology layer is the join vocabulary (map → terminology → engineer & govern)
8. Data stewardship — one source of truth behind every join (keys, sources, lineage)
9. Platform — where the joins run, at scale (on-premise: roadmap → orchestrate → resources)
10. Closing — clinical data that joins by design (partner CTA)

Total runtime ≈ 100s at the default 10s/slide.

## Turn it into an MP4

**Easiest — screen record:**
- macOS: `Cmd+Shift+5` → record the browser window. Press Play, let it run one loop, stop.
  (For 1080p: make the browser window large; the deck is a 16:9 stage that letterboxes to fit.)
- Then trim in QuickTime if needed.

**Cleaner / scriptable — headless capture (no audio):**
```bash
# needs Node + Playwright: npm i -D playwright && npx playwright install chromium
```
Record one full loop by capturing the window during playback, or use a screen-capture
tool (OBS Studio) pointed at a borderless browser window for the crispest result.

## Tweak
- **Pace:** change `--slide-ms` (CSS) **and** `DURATION` (JS) together — keep them equal.
- **Wording / slides:** edit the `<section class="slide">` blocks in `index.html`.
- **Colors:** the `:root` CSS variables (`--aqua` is the accent, `--signal` the amber).
- **Branding:** edit the `.brandmark` text top-right and the closing CTA.
