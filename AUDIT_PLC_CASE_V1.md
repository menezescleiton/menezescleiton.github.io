# PLC / Ocean Pact Case Study V1 — Editorial, Evidence and Brand Audit

## Status

**Canonical content approved by the user. Editorial, evidence-boundary, brand, responsive UX and local accessibility audits passed. The documentary-evidence restriction is disclosed and is not a publication blocker. Approved locally for publication; hosted-channel validation remains pending.**

The bilingual LinkedIn adaptation was independently reviewed by the writer and editor after revision. Both approved it without publication blockers.

## Evidence audit

### Facts represented

- independent project for Ocean Pact aboard a vessel;
- DT Marine used only as the invoicing entity;
- degraded cabinet condition and missing usable documentation;
- research in available documentation and PLC-series manuals;
- physical tracing of sensors, signals, terminals and monitored units;
- layout, cable-length and power-supply constraints;
- agreement from the vessel manager for a broader overhaul;
- reuse of verified material available aboard where appropriate;
- assistance from another team with cable-bundle organization;
- reorganization of the panel and terminal bars;
- unique terminal identification;
- printed and laminated connection map installed inside the cabinet door;
- later qualitative feedback from the chief engineer.

### Interpretations represented

- the work demonstrates investigation under uncertainty, progressive model building, systems thinking and contextual judgment;
- the map externalized knowledge that had previously been implicit;
- the reasoning pattern is relevant to software maintainability.

### Hypotheses kept outside the claims

- likely reduction in future diagnostic or maintenance effort;
- possible improvements in downtime, reliability or operational cost.

### Impact boundary

The substantiated impact is qualitative: a substantially more organized and understandable panel, documentation at the maintenance point and reported easier identification of connection origins and destinations. No quantitative operational or financial impact is claimed.

### Documentary evidence status

The factual account is user-confirmed. Photographs, the original connection map and contemporaneous records are potential supporting materials, but their existence, availability, publication rights and suitability for anonymization remain pending user confirmation. They are not represented as currently available evidence.

## Editorial audit

Passed:
- follows problem → investigation → decision → execution → result → significance;
- begins with the engineering problem rather than a biography;
- separates the immediate repair from the durable knowledge artifact;
- compresses technical detail while preserving constraints and decisions;
- English portfolio copy and the consolidated Portuguese and English LinkedIn versions preserve equivalent meaning and evidence boundaries.

## Brand audit

Passed:
- positions the author as a Software Engineer, not a PLC specialist;
- reinforces Software Evolution, contextual engineering judgment and externalization of complexity;
- avoids consultant framing, hero narrative and blame;
- does not invent technologies, responsibilities, metrics or outcomes;
- connects the case to software through reasoning patterns rather than superficial analogy.

## UX and accessibility preflight

Passed by source inspection:
- descriptive document title and description;
- one `h1` with ordered section headings;
- skip link and semantic navigation;
- accessible name and description for the conceptual diagram;
- the diagram is explicitly identified as conceptual rather than the real wiring map;
- responsive single-column section layout below the existing breakpoint;
- visible focus treatment inherited from the approved home-page system;
- no interaction depends on color alone.

Still required:
- validate the final hosted route and links.

Completed locally:
- responsive reflow was validated from `390px` through wide desktop, including an equivalent narrow viewport for enlarged-content behavior;
- keyboard focus order was verified across all eight interactive links;
- focus indicators are consistently visible;
- light-theme contrast ratios pass WCAG AA: primary text `14.70:1`, secondary text `4.51:1`, signal text `6.90:1`, and primary button `14.70:1`;
- the semantic accessibility tree exposes one page title, ordered section headings, navigation landmarks, a skip link, and the diagram's accessible name and description;
- all local pages and required assets return successfully.

## Rendered responsive audit — 2026-09-11

Status: **issue corrected and responsive validation passed**.

The case-study page was inspected in the local browser at representative widths, including the problematic intermediate range immediately above the current `55rem` breakpoint.

### Confirmed issue

- Severity: **medium** — readability and visual hierarchy.
- Affected area: section-title column in the detailed case study.
- Reproduced most clearly around `881–960px` viewport width.
- Sections `01 / Problem` and `02 / Investigation` contain words wider than the narrow first grid track.
- The title elements consequently have a `scrollWidth` greater than their available `clientWidth`; fragments paint outside the intended title column and can be perceived as overlapping or detached from the heading.
- At `900px`, the title column is approximately `170px` wide. The first two headings require approximately `173px` and `205px`, respectively.

### Cause

The two-column `.case-section` layout remains active until `55rem` (`880px`). Just above that threshold, its proportional first track can be too narrow for the display-sized headings, while the one-column layout has not yet taken effect.

### UX impact

- weakens the relationship between section index and section title;
- interrupts scanning at tablet and narrow-window sizes;
- creates the appearance of a collision even when the narrative grid track itself remains separate;
- makes the page feel less deliberate at the point where the case should communicate engineering clarity.

### Recommended correction

Move the `.case-section` transition to one column to approximately `64rem` (`1024px`) instead of waiting until `55rem`. Preserve the current two-column composition at wider desktop sizes. Also set `min-width: 0` on both grid children as a defensive containment rule.

Arbitrary word breaking is not recommended as the primary fix because it would prevent overflow by damaging title legibility.

### Correction implemented

- the case-section layout now changes to one column at `65rem` (`1040px`), covering the unstable intermediate range;
- the desktop title track now has a stronger `14rem` minimum and a more suitable column proportion;
- direct grid children use `min-width: 0` as defensive containment;
- the case-study hero receives a smaller mobile title scale, preventing the word “undocumented” from creating horizontal overflow;
- the stylesheet reference is versioned on the case page so the corrected CSS is not hidden by a stale browser cache.

### Post-correction validation

Passed at `390px`, `768px`, `900px`, `1040px`, immediately above the breakpoint, and wide desktop:

- no collision between section titles and narrative text;
- no page-level horizontal overflow;
- no overflow in the mobile case-study hero title;
- section hierarchy and reading order remain unchanged;
- the two-column desktop composition is preserved where enough space exists.

### Unaffected areas

- semantic heading order remains correct;
- the issue is unrelated to the case's evidence restriction;
- the conceptual diagram and narrative content are not the cause;
- the current mobile layout below `55rem` already uses one column and does not reproduce this specific defect.

## Final local decision

The PLC / Ocean Pact case study is **UX-reviewed, accessibility-reviewed, user-approved and ready for publication**. The absence of confirmed photographs and original documentary artifacts remains clearly stated as an evidence boundary, not represented as proof, and does not prevent publishing the current qualitative case.

After deployment, validate the public URL, resource loading, navigation targets and rendered light/dark appearance before describing the page as channel-validated.
