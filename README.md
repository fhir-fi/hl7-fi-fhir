# hl7-fi-fhir

The contents of the root folder for the FHIR implementation guides published by HL7 Finland.

## Description

This repository is the publication directory for FHIR Implementation Guides (IG) maintained by HL7 Finland. It is a static website (no executable code) that lists the IGs published by HL7 Finland, including Finnish Base Profiles, Finnish SMART App Launch, and Finnish Scheduling.

## Technologies

- Static HTML/CSS/JS website
- FHIR R4 packages
- IG publisher output (package feeds, registry)

## Packages published

| Package | ID | Canonical | Latest version |
|---|---|---|---|
| Finnish Base Profiles | hl7.fhir.fi.base | https://hl7.fi/fhir/finnish-base-profiles | 1.0.0-rc17 |
| Finnish SMART App Launch | hl7.fhir.fi.smart | https://hl7.fi/fhir/finnish-smart | 1.0.0-rc9 |
| Finnish Scheduling | hl7.fhir.fi.scheduling | https://hl7.fi/fhir/finnish-scheduling | 0.1.0 |

## Structure

- `web-root/` — published website
  - `index.html` — IG directory page
  - `package-feed.xml` — RSS feed of published packages
  - `package-registry.json` — registry of packages with canonical URLs
  - `publication-feed.xml` — publication feed
  - `publish-setup.json` — publication configuration
  - `assets/` — static assets (CSS, JS, images)

## License

CC0 1.0 Universal (see LICENSE).
