# BatCAT Handle Record Profile (v0.1)

**Purpose.** Define the minimal, machine-actionable attributes (PID Kernel Information) required in every BatCAT Handle record. The authoritative, domain-rich metadata remains on the landing page/platform.

---

## Required (MUST)

- **21.T11966/FdoProfile** — PID of the BatCAT Handle Record Profile (v0.1).  
- **0.TYPE/URL or 10320/loc** — Landing-page URL.  
- **21.11172/dateCreated** — ISO 8601 creation timestamp.  
- **21.11172/versionId** — Opaque 160bit version identifier (or longer).  
- **21.11172/digitalObjectPolicy** — Link/PID to the policy covering lifecycle rules (embargo, retention, access, tombstoning).  

---

## Recommended (SHOULD, if applicable)

- **21.11172/license** — Link/PID to license (in case of publicly available data).  
- **21.11172/dateModified** — ISO 8601 timestamp of last modification.  
- **21.11172/authors** — List of attributable authors of the data (not publishers or curators).  
- **21.11172/citation** — Recommended citation of this dataset.  
- **21.11172/keywords** — List of keywords.  
- **21.11172/provenance** — Link/PID to provenance information.  
- **21.11172/versionTag** — SemVer 2.0.0 compliant version tag.  

---

## Rules

- **Authoritative source.** The meaning and classification of the object (including type) live in the platform/landing-page metadata. Handle values must match the authoritative metadata.  
- **Validation.** A Handle record is valid only if all Required keys are present and correctly typed/formatted.  

---

