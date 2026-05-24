# Navigation And Link Audit - 2026-05-22

Scope reviewed:

- `README.md`
- `index.md`
- GitHub Pages-related files in repository root
- `.github/ISSUE_TEMPLATE/`
- `docs/` if present

Repository state reviewed:

- GitHub Pages entry file: `index.md`
- Additional Pages-readable document: `CLAIM_BOUNDARY.md`
- `docs/`: not present
- `_config.yml`: not present
- `index.html`: not present
- Issue templates present:
  - `.github/ISSUE_TEMPLATE/report-result.yml`
  - `.github/ISSUE_TEMPLATE/reproducibility-issue.yml`

## Link Integrity

Checked public targets on 2026-05-22. All checked links returned HTTP 200.

| Link target | Role | Status |
| --- | --- | --- |
| `https://onsenojisan.github.io/omega-library/` | GitHub Pages entry | no action |
| `https://thepleasureorder.wordpress.com/` | background site | no action |
| `https://zenodo.org/records/19159664` | reproducibility package | no action |
| `https://zenodo.org/records/18296691` | canonical overview | no action |
| `https://zenodo.org/records/20107274` | reference guide | no action |
| `https://github.com/onsenojisan/omega-repro` | runnable notebook workspace | no action |
| `https://github.com/onsenojisan/omega-repro/issues` | executable/result issue routing | no action |
| `https://github.com/onsenojisan/omega-library` | library repository | no action |
| `https://github.com/onsenojisan/omega-library/issues` | navigation/documentation issue routing | no action |
| `https://colab.research.google.com/drive/1FGu7_G1avub-0PUV6cpdox8cojuOvY9C` | 30 sec Colab / fixed runnable entry | no action |
| `https://colab.research.google.com/github/onsenojisan/omega-repro/blob/main/templates/omega_minimal_template/omega_minimal_template.ipynb` | custom CSV template notebook | no action |
| `CLAIM_BOUNDARY.md` via Pages | claim boundary document | no action |

Finding: no broken external links were found.

Severity: no action.

## Navigation Consistency

The public `index.md` separates the main roles clearly:

- 30 sec Colab: immediate runnable entry.
- Reproducibility package: Zenodo archived public package.
- Run your own CSV: omega-repro template notebook.
- Canonical Overview / Reference Guide / Claim Boundary: orientation and boundary materials.
- GitHub Reporting: issue routing.

Finding: the current top-level navigation is understandable and role-labeled.

Severity: no action.

## Duplicate Or Conflicting CTAs

The following repeated CTAs are present:

- `Run 30 sec Colab` appears near the top and in `Run First`.
- `Run your own CSV` appears near the top and in `Use Your Own CSV`.
- `Reproducibility package` appears near the top, in `Reproduce`, and in `Canonical Resources`.

Finding: these repetitions are not currently conflicting because each repeated link keeps the same role and target.

Severity: no action.

Optional patch if the page becomes longer:

```diff
- [Reproducibility package](https://zenodo.org/records/19159664)
- [Run your own CSV](https://colab.research.google.com/github/onsenojisan/omega-repro/blob/main/templates/omega_minimal_template/omega_minimal_template.ipynb)
+ Quick links:
+ - [Reproducibility package](https://zenodo.org/records/19159664)
+ - [Run your own CSV](https://colab.research.google.com/github/onsenojisan/omega-repro/blob/main/templates/omega_minimal_template/omega_minimal_template.ipynb)
```

## Role Clarity

Current role separation in `index.md`:

- Zenodo is named as the canonical archive and public record.
- GitHub Pages is named as the execution and navigation hub.
- omega-repro is used for runnable notebooks, custom CSV execution, executable reproduction issues, notebook/Colab issues, CSV template issues, and result discussions.
- omega-library is used for navigation, broken links, artifact placement, documentation structure, and Ω Library architecture issues.
- Reference Guide is labeled as navigation/reference for the Ω Library.
- Claim Boundary is labeled as operational claim boundary for interpretation.

Finding: page-level role separation is clear.

Severity: no action.

## Issue Template Routing Conflict

The current `index.md` and `README.md` route executable reproduction results, notebook/Colab issues, CSV template issues, and result discussions to `omega-repro`.

However, this repository still contains issue templates named and described for:

- `Report Ω test result`
- `Report reproducibility issue`

These templates are not linked from `index.md`, but they can still appear in the GitHub issue creation flow for `omega-library`. That can conflict with the stated routing and can pull executable/result reports back into the library repository.

Finding: issue templates are the main remaining role-clarity risk.

Severity: required.

Recommended patch:

```diff
*** Delete File: .github/ISSUE_TEMPLATE/report-result.yml
*** Delete File: .github/ISSUE_TEMPLATE/reproducibility-issue.yml
```

Alternative if templates should not be deleted yet:

```diff
*** Add File: .github/ISSUE_TEMPLATE/config.yml
+blank_issues_enabled: false
+contact_links:
+  - name: Executable reproduction result / notebook issue
+    url: https://github.com/onsenojisan/omega-repro/issues
+    about: Report executable reproduction results, notebook/Colab issues, CSV template issues, or result discussions.
+  - name: Navigation / documentation issue
+    url: https://github.com/onsenojisan/omega-library/issues
+    about: Report navigation problems, broken links, artifact placement, documentation structure, or Ω Library architecture issues.
```

Do not apply both patches at once. Deleting the conflicting templates is cleaner if `omega-library` should not accept result or reproduction reports directly.

## Mobile Markdown Structure

Current mobile-friendly structures:

- `Canonical Resources` uses a list.
- `GitHub Reporting` uses a list.
- Long issue-routing explanation appears as one paragraph in `index.md`.

Finding: the link lists are mobile-friendly. The issue-routing paragraph is acceptable but could be split if future wording grows.

Severity: optional.

Optional patch:

```diff
- Executable reproduction results, notebook/Colab issues, CSV template issues, and result discussions belong in omega-repro. Navigation, broken links, artifact placement, documentation structure, and Ω Library architecture issues belong here.
+ Routing:
+ - Executable reproduction results, notebook/Colab issues, CSV template issues, and result discussions belong in omega-repro.
+ - Navigation, broken links, artifact placement, documentation structure, and Ω Library architecture issues belong here.
```

## Over-Centralization Risk

Several paths intentionally lead to `omega-repro`:

- custom CSV template notebook;
- runnable notebooks;
- executable reproduction / notebook issue reporting;
- null-result reporting.

Finding: this is not currently over-centralized because `omega-repro` is the correct execution workspace. The risk is controlled by keeping Zenodo canonical records and omega-library navigation separate.

Severity: no action.

## Summary

Required:

- Resolve the remaining issue-template routing conflict in `omega-library`.

Optional:

- Convert the issue-routing paragraph in `index.md` into two bullets if mobile readability needs further tightening.
- Convert top quick links into bullets if more top-level links are added later.

No action:

- External link integrity.
- Current Pages entry structure.
- Current Zenodo / Reference Guide / Claim Boundary / omega-repro role labels.
- Current repeated CTAs, because they are consistent and role-aligned.
