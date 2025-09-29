# BatCAT Minimum metadata Kernel (v0.1)

**Status:** draft | **Updated:** 2025-09-29  
**specifications:** [`metadata-kernel-v0.1.yaml`]

This kernel defines the **mandatory** fields that MUST appear on every landing page that a PID resolves to, plus a small set of **recommended** fields.  
The landing page holds the **authoritative (rich) metadata**; the Handle (PID) record stays **minimal**.

## Required fields (with RDF alignment)

| Field        | Purpose (human)                                   | RDF term             |
|--------------|----------------------------------------------------|----------------------|
| title        | Human-readable name                                | `dct:title`          |
| creator      | Person/org responsible (ORCID/ROR if available)    | `dct:creator`        |
| dateCreated  | Creation/issue timestamp (ISO 8601)                | `dct:issued`         |
| version      | Ordered version string (e.g., 1.0.0)               | `dct:hasVersion`     |
| license      | Licence IRI (SPDX preferred)                       | `dct:license`        |
| landingPage  | Stable HTTPS URL of this page                      | `dcat:landingPage`   |
| identifiers  | List of IDs; MUST include the Handle PID           | `dct:identifier`     |

**Recommended:** `description (dct:description)`, `format (dct:format)`, `relatedPIDs (prov/dct)`, `provenance (prov:*)`.

> For datamodel details (cardinality, datatypes, exact RDF properties), see the YAML.

## Rationale

- **Separation of concerns:** a thin **PID kernel** in the Handle record for resolution & automation; **rich, authoritative metadata** on the landing page for humans and interoperability.  
- **Standards alignment:** fields map to **Dublin Core Terms (dct)** and **W3C DCAT (dcat)**; provenance uses **PROV-O (prov)**.  

> Changes to this kernel follow the project’s metadata-change workflow and are logged.
