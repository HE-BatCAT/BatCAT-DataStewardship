# BatCAT Data Stewardship – Governance Space

This repository contains the living governance framework for **Task 4.6: Data Stewardship** in the BatCAT project (EU Horizon Europe, GA 101137725).

It documents:
- Minimum metadata kernels agreed across BatCAT
- Policies for persistent identifiers (PIDs)
- Metadata change workflow
- Retention and deletion rules (including tombstoning)
- Decision log of approved changes

The purpose is to provide **simple and practical rules** that align with community recommendations (FAIR, EMMC, RDA) while being flexible for partners’ systems.

## How to Request a Change

If you propose a change to metadata kernels, PID policy, or retention rules:

1. Open a new **GitHub Issue** using the “Change Request” template.  
   *(If you cannot use GitHub, send the request by email to the SDO at NMBU.)*
2. The SDO will triage within 5 working days (minor vs. major).
3. Review, implementation, and approval follow the [Metadata Change Workflow](workflow/metadata-change.md).
4. All approved changes are logged in [/log/decision-log.md](log/decision-log.md).

## Repository Structure

- `README.md` → Overview and change request process  
- `kernels/landing-kernel-v0.1.md` → Minimum metadata kernel  
- `kernels/landing-kernel-v0.1.yaml` → Minimum metadata kernel 
- `workflow/metadata-change.md` → 7-step metadata schema change workflow  
- `policies/pid-policy.md` → PID & landing-page policy (tombstoning, versioning, minimal kernel)  
- `policies/handle-record-profile.md` → BatCAT Handle Record Profile (required PID attributes)  
- `retention/playbook.md` → Retention rules per data type  
- `log/decision-log.md` → Record of approved governance changes




This space is **open for partner input**. Contributions are welcome via pull requests or issues.


