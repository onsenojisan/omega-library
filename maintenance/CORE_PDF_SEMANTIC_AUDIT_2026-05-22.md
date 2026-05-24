# Core PDF Semantic Audit - 2026-05-22

Scope:

- Reproducibility Package for Structural Collapse and the Ω State Variable
- Execution and Discovery Protocol for Ω-Based Collapse Analysis
- Domain Translation Guide for Ω = I × G
- Ω Reference Guide
- Canonical Overview

Method:

- Read current Zenodo descriptions for the target records.
- Extracted public PDF body text with `pypdf`.
- Compared PDF body wording against current Ω Library / omega-repro routing and claim-boundary rules.
- Did not modify PDFs, Zenodo records, README, `index.md`, issue templates, validator config, topology config, or `expected_links`.

## 1. Reproducibility Package

Record: `19159664`

PDF: `Reproducibility Package for Structural Collapse and the Ω State Variable.pdf`

Role: executable reproducibility package.

Severity: no action.

Findings:

- PDF body is consistent with executable/reproducibility role.
- PDF body frames the package as an executable specification, not a new theory.
- Zenodo description now points post-reproduction work toward alternative structural definitions, not intervention effects.
- Event threshold in the description remains independently defined from Ω.

Exact wording checked:

- PDF body: `not to introduce new theory`
- PDF body: `executable specification`
- Description: `Event threshold: 0.998 (independent of Ω)`

Issue location:

- No current issue in PDF body.
- No current issue in Zenodo description.

Recommended replacement wording:

- None.

Priority:

- No action.

## 2. Execution and Discovery Protocol for Ω-Based Collapse Analysis

Record: `19324740`

PDF: `Execution and Discovery Protocol for Ω-Based Collapse Analysis (1).pdf`

Role: execution protocol.

Severity: required.

Findings:

- Zenodo description has been corrected to avoid invalidating null results.
- PDF body still contains decision wording that conflicts with the current null-results-are-valid rule.
- PDF body also contains wording that can read like implementation tuning after observing weak results.

Exact wording creating drift:

- PDF body: `No concentration → discard`
- PDF body: `Weak concentration → modify implementation`

Current description wording:

- Description: `no concentration → no concentration observed`

Issue location:

- PDF body only.

Why this matters:

- Current project rules treat null, weak, and near-baseline outcomes as valid reportable outcomes.
- `discard` can imply that a null result invalidates the framework or should be suppressed.
- `modify implementation` can be read as an optimization loop unless framed as a future pre-registered run.

Recommended replacement wording:

```diff
- No concentration → discard
+ No concentration → report null / no-concentration result under fixed definitions
```

```diff
- Weak concentration → modify implementation (I, G only)
+ Weak concentration → report weak result; revise definitions only in a separate future run
```

Priority:

- Fix now in the next versioned PDF revision.
- Full PDF regeneration is justified only because the required contradiction remains in the PDF body.

## 3. Domain Translation Guide for Ω = I × G

Record: `19199493`

PDF: `Domain Translation Guide for Ω = I × G.pdf`

Role: domain translation / implementation guide.

Severity: required.

Findings:

- Zenodo description has been corrected to separate high-Ω state from collapse/event.
- PDF body still defines `event` directly from Ω.
- This conflicts with the current rule that collapse/event must be independently defined.

Exact wording creating drift:

- PDF body: `event = Ω > q(0.995)`

Current description wording:

- Description: `high-Ω state = Ω > q(0.995)`
- Description: `collapse defined as a single observable variable (independent of Ω)`
- Description: `q = 0.995 is shown here as a reference example`

Issue location:

- PDF body only.

Why this matters:

- The PDF body can be read as defining the event by high Ω.
- Current project rules require high-Ω state and collapse/event to remain separate.
- The description already reflects the correct separation, so the PDF body is now the drift source.

Recommended replacement wording:

```diff
- event = Ω > q(0.995)
+ high-Ω state = Ω > q(0.995)
```

Add or preserve:

```diff
+ collapse/event = independently defined observable variable
```

Recommended q-threshold wording:

```diff
- q(0.995)
+ q(0.995) as a reference example; implementation thresholds must be fixed ex ante
```

Priority:

- Fix now in the next versioned PDF revision.
- Full PDF regeneration is justified only because the required contradiction remains in the PDF body.

## 4. Ω Reference Guide

Record: `20107274`

PDF: `Ω Reference Guide-(External Navigation Reference for the Ω Library).pdf`

Role: external navigation reference.

Severity: optional.

Findings:

- PDF body is consistent with the current navigation/reference role.
- PDF body explicitly avoids prediction, intervention, causality, and universal mechanism claims.
- Zenodo description still says the document is not a canonical document; this is potentially ambiguous because the current repository treats it as a stable navigation/reference anchor, not as canonical theory.

Exact wording checked:

- PDF body: `REFERENCE DOCUMENT — PUBLIC NAVIGATION ONLY`
- PDF body: `does NOT establish`
- Description: `a canonical document`

Issue location:

- Zenodo description only.

Why this matters:

- The guide should not appear to be the canonical theory overview.
- But saying it is not canonical at all can conflict with its stable public navigation role.

Recommended replacement wording:

```diff
- a canonical document
+ a canonical theory document
```

Priority:

- Defer.
- No PDF change required.

## 5. Canonical Overview

Record: `18296691`

PDF: `The Pleasure Order — Structural Overview (Revised).pdf`

Role: canonical structural overview.

Severity: optional.

Findings:

- PDF body and description are aligned with each other as broad theory/overview material.
- The body contains broad theory language that is not appropriate for execution artifacts, but it is not itself an execution artifact.
- The main risk is reader spillover: users may import canonical overview language into reproducibility or execution claims.

Exact wording checked:

- PDF body: `scale-invariant laws`
- PDF body: `BYXCZ`
- Description: `All other materials are non-normative`

Issue location:

- PDF body and Zenodo description, but only as role-boundary risk.

Why this matters:

- Current Ω Library execution pages restrict executable claims to structural concentration only.
- The canonical overview can remain broader if it is clearly separated from execution and reproducibility artifacts.
- The description phrase about all other materials being non-normative can weaken the stated operational roles of execution standards, reference guides, and reproducibility packages.

Recommended replacement wording for description only:

```diff
- All other materials are non-normative.
+ Other materials retain their stated roles: reference, execution, reproducibility, summary, or exploratory analysis.
```

Optional boundary sentence:

```diff
+ This overview is not an execution protocol and does not by itself establish prediction, causal proof, optimization, deterministic collapse, or proof of a universal physical law.
```

Priority:

- Defer.
- Do not regenerate the PDF solely for this issue unless a broader canonical overview revision is already planned.

## q-Threshold Review

Severity: required for Domain Translation Guide; no action elsewhere.

Findings:

- Domain Translation Guide PDF body uses `q(0.995)` in the same line as `event = Ω > q(0.995)`, which is the required issue.
- Execution Protocol PDF body uses implementation-dependent threshold language and separates high Ω from collapse.
- Reproducibility Package uses a domain-specific event threshold independent of Ω.
- Current descriptions distinguish reference thresholds from implementation-dependent thresholds more clearly than the older PDF body.

Recommended action:

- Fix Domain Translation Guide PDF body as above.
- Do not normalize every artifact to one global q threshold; that would reduce domain-specific clarity.

## Conclusions / Claim Scope Review

Severity: no action, except the required PDF-body contradictions above.

Findings:

- Reproducibility Package: does not overstate beyond executable reproduction.
- Execution Protocol: description is aligned; PDF decision rule needs revision.
- Domain Translation Guide: description is aligned; PDF event/high-Ω wording needs revision.
- Reference Guide: body is aligned; description wording can be narrowed later.
- Canonical Overview: broad theory role is expected, but should not be imported into execution claims.

## Final Priority List

### Fix now

1. Domain Translation Guide PDF body:
   - replace `event = Ω > q(0.995)` with `high-Ω state = Ω > q(0.995)`.
   - explicitly keep collapse/event independently defined.

2. Execution Protocol PDF body:
   - replace `No concentration → discard`.
   - replace or qualify `Weak concentration → modify implementation`.

### Defer

1. Reference Guide Zenodo description:
   - narrow `a canonical document` to `a canonical theory document`.

2. Canonical Overview Zenodo description:
   - soften `All other materials are non-normative`.
   - add an execution-boundary sentence only if revising description text.

### No action

1. Reproducibility Package PDF body and current description.
2. Reference Guide PDF body.
3. Canonical Overview PDF body, unless a broader versioned overview revision is already planned.

Overall status:

The updated Zenodo descriptions are mostly aligned with the current Ω Library / omega-repro structure. The remaining required semantic drift is in two PDF bodies: the Domain Translation Guide and the Execution Protocol.
