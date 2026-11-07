# REVERSE ENGINEERING REPORT — HL7 Finland / hl7-fi-fhir

## Original repository
- Name: hl7-fi-fhir
- URL: https://github.com/fhir-fi/hl7-fi-fhir
- Type: Static portal for FHIR Implementation Guides published by HL7 Finland
- Branch: main
- Base: d3a1d4e Add scheduling IG to index page

## Audit date
2026-11-07

## Tools used
- Git v2.49.0
- PowerShell 5.1
- gh (GitHub CLI), authenticated as admeduardovieira
- Kilo Code (static analysis of HTML/XML/JSON/markdown files)

## Identified architecture
Static repository (website) serving as the directory/publication of FHIR Implementation Guides published by HL7 Finland. Contains:
- `web-root/index.html` — IG directory page
- `web-root/package-feed.xml` — RSS feed of published packages
- `web-root/package-registry.json` — registry of packages with canonical URLs
- `web-root/publication-feed.xml` — publication feed
- `web-root/publish-setup.json` — publication configuration
- `web-root/assets/` — static assets (CSS, JS, images)

No executable code; publication definitions and static assets only.

## Technologies and dependencies
- Static HTML/CSS/JS (Bootstrap, jQuery, Prism)
- FHIR R4 packages
- No build dependencies in the repository (pre-generated static site)

## Maintenance status
- ~8 commits
- Last commit: d3a1d4e (adding scheduling IG to index)
- 0 GitHub Issues listed
- 0 GitHub PRs listed
- No automated tests, no CI

## Investigation limitations
- Not executable code project; no environment to validate build
- SUSHI/releaselabel does not apply (no sushi-config.yaml)

---

## Problems found (hl7-fi-fhir)

| ID | Sev | Status | Location | Problem | Fix applied |
|---|---|---|---|---|---|
| REA-001 | P3 | CONFIRMED | README.md | Minimal README (2 lines); no usage, build, contribution or version instructions | README expanded with purpose, technologies, packages table, structure, license |
| REA-002 | P3 | CONFIRMADO | .gitignore | Minimal `.gitignore` (only `.DS_Store`); does not ignore build/log/tmp/OS | `.gitignore` expanded with *.log, *.tmp, Thumbs.db |

## Recurring problems
None documented publicly (0 Issues/PRs). Not invented.

## Undocumented errors (new from audit)
REA-001, REA-002 have no visible public record.

## Changes implemented (Phase 2)
1. `README.md`: expanded with purpose, technologies, published packages table (hl7.fhir.fi.base, hl7.fhir.fi.smart, hl7.fhir.fi.scheduling), repository structure, CC0 1.0 license.
2. `.gitignore`: expanded with *.log, *.tmp, Thumbs.db.

## Changes NOT implemented
None — all identified problems were corrected.

## Validation performed
- Static review of HTML/XML/JSON/markdown files.
- Not executed: build (not applicable; pre-generated static site).

## Remaining risks
- External links to simplifier.net may break (older IGs published there).
- Package feed references RC (release candidate) versions — not final stable versions.

## Recommendations for future audits
- Add basic CI for external link validation.
- Add integrity tests for package-registry.json.
