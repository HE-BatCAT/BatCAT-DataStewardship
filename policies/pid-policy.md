# BatCAT PID & Landing-Page Policy (v0.1)

**Scope.** Applies to versioned BatCAT digital objects (initially **Dataset** and **Model**; additional types may follow the same pattern).

## PID scheme and persistence
- **Registry:** Handle.net.
- **One PID per versioned object.** Older PIDs remain resolvable.
- **`version`** is an ordered string (e.g., `1.0.0`) recorded in the Handle record and on the landing page.

## Landing page
Each PID MUST resolve via HTTPS to a human-readable landing page that provides at least:
- title/name; owner/creator; creation date; **version**;
- licence; citation; links to **authoritative metadata** (e.g., JSON-LD export) and to **related PIDs** (e.g., previous/next, inputs/outputs);
- access information and contact where applicable.

Authoritative, domain-rich metadata lives on the landing page/platform. The Handle record remains minimal.

## Tombstoning (withdrawals)
PIDs never return “not found.” If an object (or a version) is withdrawn, resolution MUST return a **tombstone** landing page stating:
- identifier/title; **status = withdrawn**; **withdrawal date/time**; brief context (where appropriate);
- **successor PID** if available.

Descriptive metadata remains accessible to preserve citability and provenance.

## Minimal PID kernel (Handle record)
A valid BatCAT Handle record **MUST** include:
- `0.PROFILE` — URL of the **BatCAT Handle Record Profile** (this repository, later will replaced by PID ).
- `0.TYPE` — object type IRI (copied from the authoritative metadata).
- `URL` — landing-page URL (HTTPS).
- `dateCreated` — ISO 8601 timestamp.
- `version` — ordered string (e.g., `1.0.0`).
- `digitalObjectPolicy` — URL of this policy.

**Recommended (if applicable):** `dateModified` (ISO 8601) and qualified provenance links (PROV-O) such as `wasRevisionOf`, `wasDerivedFrom`, `hadPrimarySource`, `alternateOf`.

## Source of truth & allowed types
The platform/landing metadata is the **single source of truth**. Type value (0.TYPE). The object type is maintained in the authoritative metadata (LinkAhead) and is copied verbatim into the Handle record as 0.TYPE.
For v0.1, 0.TYPE is a text label (string) and MUST match the LinkAhead record’s type field exactly.
If the consortium later publishes a type vocabulary (e.g., SKOS with IRIs), 0.TYPE MAY be expressed as an IRI with a backward-compatible mapping.

## Versioning (and referencing parts)
BatCAT uses a **flexible, context-dependent** approach:
- For iterative/minor updates, a **single PID with internal version tracking** may be used.
- When revisions substantially alter a dataset or instrument (e.g., scope, structure, interpretation), a **new PID** is assigned for that version.
- Where clearer citation is helpful, **PID version suffixes** (e.g., `.v1`, `.v2`) or content-based hashes may be used in addition to the `version` field.

When it is necessary to cite a **well-defined part** of a larger object (e.g., a time slice or parameter subset), BatCAT **may** enable Handle.net **Template Handles** (one base PID with a short suffix separated by a delimiter such as `@`) to reference parts without minting many additional PIDs. This does **not** replace the rule that materially new versions receive a **new PID**.
