# Zenodo Role And Terminology Audit - 2026-05-22

> Maintenance note: This is a public maintenance audit record, not the ordinary reader path. It reflects the repository and linked-record state at the time of review. Later fixes or restructuring may have superseded specific findings. For the current public entry points, use the repository root, `README.md`, `index.md`, and `CLAIM_BOUNDARY.md`.

Scope reviewed:

- Zenodo descriptions
- Public PDFs available from reviewed Zenodo records
- Canonical Overview
- Reference Guide
- Reproducibility Package
- Architecture Map
- Cross-domain summaries
- Minimal protocol / standard form documents

Method:

- Read live Zenodo API metadata and descriptions.
- Extracted public PDF text with `pypdf` for terminology checks.
- Did not modify Zenodo records, PDFs, GitHub source files, descriptions, validator config, topology config, or `expected_links`.

## Records Reviewed

| record | title / role reviewed | status |
| --- | --- | --- |
| `18296691` | Canonical Overview | finding |
| `19159664` | Reproducibility Package | finding |
| `19199493` | Domain Translation Guide | finding |
| `19324740` | Execution Protocol | finding |
| `19492994` | Minimal Trigger / Finance Example | no action |
| `20020739` | Cross-Domain Summary | no action |
| `20045831` | Structural Concentration of Collapse Events in High-Ω Regimes | optional |
| `20046470` | Ω Minimal Standard Form v1.0 | no action |
| `20107274` | Ω Reference Guide | finding |
| `20119570` | Ω Library Architecture Map | optional |
| `20309117` | Ω Minimal CSV Template | no action |
| `17982736` | legacy Entry Point referenced by Canonical Overview | optional |

## Required Findings

### 1. Domain Translation Guide defines `event` using Ω, then requires independent collapse

Severity: required.

Record: `19199493`

Role intended: cross-domain implementation guide / translation support.

Exact wording conflict in Zenodo description:

> `event = Ω > q(0.995)`

and later:

> `collapse defined as a single observable variable (independent of Ω)`

Why this matters:

- The current operational boundary requires event definitions to be independent from Ω.
- Defining `event` as `Ω > q(0.995)` reads as circular if the same event is later evaluated against high-Ω states.
- The intended term appears to be `high-Ω state`, not `event`.

Recommended patch:

```diff
- event = Ω > q(0.995)
+ high-Ω state = Ω > q(0.995)
```

Optional supporting sentence:

```diff
+ The event or collapse label must be defined independently from Ω.
```

### 2. Reproducibility Package suggests testing intervention effects

Severity: required.

Record: `19159664`

Role intended: executable reproduction package.

Exact wording conflict in Zenodo description:

> `After reproduction: - apply Ω to your domain - test alternative Ω constructions - test intervention effects`

Why this matters:

- `test intervention effects` can read as causal or policy/intervention evaluation.
- Current boundary states structural concentration only: not causal proof, not optimization, not deterministic collapse.
- The reproduction package should stay executable/reproducibility-oriented.

Recommended patch:

```diff
- test intervention effects
+ report structurally defined event concentration under fixed definitions
```

### 3. Execution Protocol treats null results as discard

Severity: required.

Record: `19324740`

Role intended: fixed execution protocol.

Exact wording conflict in Zenodo description:

> `Decision: - concentration → structure exists - no concentration → discard`

Why this matters:

- Current GitHub Pages, Claim Boundary, and issue routing all treat null results as valid.
- `discard` can encourage suppressing null results or treating them as failed artifacts.
- Execution protocol should report null/no-concentration outcomes under fixed definitions.

Recommended patch:

```diff
- concentration → structure exists
- no concentration → discard
+ concentration → report structural concentration under fixed definitions
+ no concentration → report null / no-concentration result under fixed definitions
```

### 4. Canonical Overview description can overrun the current claim boundary

Severity: required.

Record: `18296691`

Role intended: canonical structural overview.

Exact wording conflicts in Zenodo description:

> `All other materials are non-normative.`

and:

> `identical directional laws apply continuously`

and:

> `govern matter, life, mind, and civilization`

Why this matters:

- The current Ω Library separates canonical overview, reference guide, execution standards, reproducibility packages, and summaries by role.
- `All other materials are non-normative` can be read as overriding the operational authority of execution standards and reproducibility packages.
- `identical directional laws` and `govern matter, life, mind, and civilization` can be read as stronger than the current operational claim boundary, especially the boundary against proof of a universal physical law.

Recommended patch to description role sentence:

```diff
- This document is the canonical structural overview. All other materials are non-normative.
+ This document is the canonical structural overview. Execution standards, reference guides, reproducibility packages, and empirical summaries retain their stated operational roles.
```

Recommended boundary sentence:

```diff
+ This overview does not by itself establish prediction, causal proof, optimization, deterministic collapse, or proof of a universal physical law.
```

Do not rewrite the PDF unless a versioned revision is intentionally planned.

### 5. Reference Guide says it is not canonical, while it functions as canonical navigation

Severity: required.

Record: `20107274`

Role intended: external navigation reference / canonical navigation anchor.

Exact wording conflict in Zenodo description:

> `This document is not: - a theory paper - a predictive framework - a mechanism claim - a canonical document`

Why this matters:

- The local artifact index and GitHub Pages treat the Reference Guide as the public navigation/reference anchor.
- `not a canonical document` can conflict with that role.
- The likely intended boundary is `not a canonical theory document`.

Recommended patch:

```diff
- a canonical document
+ a canonical theory document
```

or:

```diff
- a canonical document
+ the canonical structural overview
```

## Optional Findings

### 6. Two cross-domain summary-like records can blur roles

Severity: optional.

Records:

- `20020739` - `Structural Concentration Test — Cross-Domain Summary (Ω)`
- `20045831` - `Structural Concentration of Collapse Events in High-Ω Regimes`

Relevant wording:

Record `20020739`:

> `This record provides a minimal cross-domain summary artifact.`

Record `20045831`:

> `This record provides a minimal, reproducible specification and empirical demonstration of structural concentration of collapse events in high-Ω states.`

Why this matters:

- Both records summarize cross-domain empirical concentration.
- `20020739` appears to be the active Cross-Domain Summary.
- `20045831` appears more like a supplemental empirical report/specification.
- The roles are distinguishable, but not explicitly separated in public descriptions.

Recommended patch only if role confusion appears in practice:

```diff
+ Role note: this record is a supplemental empirical specification/report. The active minimal Cross-Domain Summary record is https://zenodo.org/records/20020739.
```

Do not add this link if avoiding additional cross-linking is more important than role clarification.

### 7. Architecture Map execution route is older than the current GitHub Pages entry

Severity: optional.

Record: `20119570`

Exact wording:

> `The recommended minimal execution path is: Ω Reference Guide → AAPL Minimal Test → optional orientation / canonical overview`

Current GitHub Pages route:

- Run 30 sec Colab.
- Use custom CSV template.
- Reproduce Zenodo package.
- Use Reference Guide / Claim Boundary / Canonical Overview for orientation.

Why this matters:

- The Architecture Map is still structurally valid.
- It does not yet reflect the newer GitHub Pages Execution Hub and custom CSV route as the public entry structure.

Recommended patch only if revising the Architecture Map:

```diff
- Ω Reference Guide → AAPL Minimal Test → optional orientation / canonical overview
+ GitHub Pages Execution Hub → 30 sec Colab or custom CSV template → optional Reference Guide / Canonical Overview
```

### 8. Legacy Entry Point record uses strong canonical wording

Severity: optional.

Record: `17982736`

Exact wording:

> `This record is the official structural reference of The Pleasure Order. All other materials, including entry documents, summaries, and external interpretations, are non-normative.`

Why this matters:

- This record is referenced by the Canonical Overview as an orientation entry.
- The wording can compete with the current Canonical Overview and operational artifact roles.
- It is not currently a primary GitHub Pages link, so the risk is lower.

Recommended patch only if the legacy record remains public-facing in the main path:

```diff
- All other materials, including entry documents, summaries, and external interpretations, are non-normative.
+ Other materials should be read according to their stated roles: overview, reference, execution, reproducibility, summary, or exploratory analysis.
```

## No-Action Findings

### Minimal Trigger / Finance Example

Severity: no action.

Record: `19492994`

The description clearly states:

> `The objective is not prediction, but to test structural concentration`

and:

> `This is a concentration test, not a prediction model.`

Role is consistent: fixed finance example / minimal executable trigger.

### Cross-Domain Summary

Severity: no action.

Record: `20020739`

The description includes the necessary boundaries:

> `This is not a predictive or optimization model. It is a structural concentration test.`

and:

> `Reporting does not imply endorsement of a universal law`

Role is consistent as a summary artifact.

### Minimal Standard Form

Severity: no action.

Record: `20046470`

The description clearly states:

> `This document is not a predictive model, optimization framework, or universal law claim.`

Role is consistent as a fixed minimal execution standard.

### Minimal CSV Template

Severity: no action.

Record: `20309117`

The description is aligned with the current GitHub Pages custom CSV route:

> `Minimal executable Ω template for user-provided data.`

and:

> `not prediction`

> `not optimization`

> `not causal inference`

and:

> `CSV datasets should contain at least 20 numeric rows`

Role is consistent as an executable user-provided CSV template.

## CTA Structure Review

Severity: optional.

Observed CTA patterns:

- Several records use `Start here (30 sec)` or `Quick start`.
- `19159664` points to PJM main reproduction, AAPL quick test, BTC example, Minimal CSV Template, and omega-repro issue reporting.
- `20107274` points to GitHub Pages Execution Hub, AAPL direct Colab, Minimal CSV Template, Canonical Overview, and terminology guide.
- `20119570` points to Reference Guide, AAPL direct Colab, and Canonical Overview.

Finding:

- The CTAs are mostly consistent but not fully centralized.
- This is acceptable because the records have different roles.
- Do not add more links solely for symmetry.

Recommended action:

- No immediate patch.
- If updating descriptions, keep one primary CTA per role:
  - execution hub for public navigation;
  - direct Colab only where the artifact is explicitly executable;
  - Zenodo record links only when role clarity requires them.

## Summary

Required patches:

1. `19199493`: replace `event = Ω > q(0.995)` with `high-Ω state = Ω > q(0.995)`.
2. `19159664`: replace `test intervention effects` with structurally bounded reporting language.
3. `19324740`: replace `no concentration → discard` with null-result reporting language.
4. `18296691`: soften `All other materials are non-normative` and add a claim-boundary sentence.
5. `20107274`: replace `a canonical document` with `a canonical theory document` or `the canonical structural overview`.

Optional patches:

1. Clarify the relation between `20020739` and `20045831` only if readers confuse the two cross-domain records.
2. Update `20119570` execution path only if revising the Architecture Map.
3. Reword legacy `17982736` only if it remains in the primary public path.

No action:

1. `19492994` Minimal Trigger / Finance Example.
2. `20020739` Cross-Domain Summary.
3. `20046470` Minimal Standard Form.
4. `20309117` Minimal CSV Template.

Overall status:

The Zenodo layer is broadly usable and structurally coherent. The main risks are not broken links; they are a small set of wording conflicts where older canonical/theory language or execution-decision language can override the newer operational boundary.
