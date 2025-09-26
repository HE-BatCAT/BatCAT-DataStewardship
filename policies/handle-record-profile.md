# BatCAT Handle Record Profile (v0.1)

**Purpose.** Define the minimal, machine-actionable attributes (PID Kernel Information) required in every BatCAT Handle record. The authoritative, domain-rich metadata remains on the landing page/platform.

## Required (MUST)
- `0.PROFILE` — URL of this profile file (will have its own PID).
- `0.TYPE` — string value copied from the platform record type value, copied verbatim from LinkAhead. **copied from the authoritative metadata**.
- `URL` — HTTPS landing-page URL.
- `dateCreated` — ISO 8601 timestamp.
- `version` — ordered string (e.g., `1.0.0`).
- `digitalObjectPolicy` — URL of the BatCAT PID & Landing-Page Policy.

## Recommended (SHOULD, if applicable)
- `dateModified` — ISO 8601 timestamp.
- Qualified provenance (PROV-O): `wasRevisionOf`, `wasDerivedFrom`, `hadPrimarySource`, `alternateOf`.

## Rules
- **Authoritative source.** The meaning and classification of the object (including type) live in the platform/landing-page metadata. Handle values **must match** the authoritative metadata.
- **Validation.** A Handle record is valid only if all **Required** keys are present and correctly typed/formatted.

## Minimal example (illustrative)
```json
{
  "0.PROFILE": "https://github.com/HE-BatCAT/BatCAT-DataStewardship/blob/main/policies/handle-record-profile.md",
  "0.TYPE": "https://batcat.info/vocab/object-type#Dataset",
  "URL": "https://batcat.example/landing/20.500.X/abc-123",
  "dateCreated": "2025-09-25T09:00:00Z",
  "version": "1.0.0",
  "digitalObjectPolicy": "https://github.com/HE-BatCAT/BatCAT-DataStewardship/blob/main/policies/pid-policy.md"
}
