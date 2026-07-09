\# Task 2 - Secure CI/CD Pipeline \& Supply Chain Security



\## Overview



Implemented a secure GitHub Actions CI/CD pipeline for ledger-api.



The pipeline builds, scans, signs and verifies the container image.



\---



\# Implemented Controls



\## 1. Docker Image Build



Application:

ledger-api





Dockerfile:





ledger-api-assignment/app/Dockerfile





Image:





ghcr.io/dheeraj1703/ledger-api





Evidence:



!\[Docker Image](screenshots/task2-03-docker-image.png)





\---



\# 2. SAST Security Scan



Tool:



Semgrep





Purpose:



\- Detect insecure coding patterns

\- Identify application security issues





Evidence:



!\[Semgrep](screenshots/task2-05-semgrep.png)





\---



\# 3. Container Vulnerability Scan



Tool:



Trivy





Checks:



\- OS packages

\- Application dependencies

\- HIGH and CRITICAL vulnerabilities





\---



\# 4. Secret Detection



Tool:



Gitleaks





Purpose:



Prevent credentials from being committed.





Result:



No secrets detected.





Evidence:



!\[Gitleaks](screenshots/task2-06-gitleaks.png)





\---



\# 5. GitHub Container Registry



Image pushed to:





ghcr.io/dheeraj1703/ledger-api







\---



\# 6. Container Signing



Tool:



Cosign





Implemented:



Keyless signing using GitHub OIDC.





Verification:





cosign verify







Evidence:



!\[Cosign](screenshots/task2-slsa-attestation.png)





\---



\# 7. SLSA Provenance



Implemented:



GitHub Artifact Attestation





Provides:



\- Build traceability

\- Supply chain verification

\- Artifact integrity





Evidence:



!\[SLSA](screenshots/task2-slsa-attestation.png)





\---



\# Pipeline Result



GitHub Actions workflow completed successfully.





Evidence:



!\[Pipeline Success](screenshots/task2-pipeline-success.png)





\---



\# Security Gate Policy



| Tool | Purpose | Policy |

|---|---|---|

| Semgrep | SAST | Review findings |

| Trivy | Vulnerability scanning | HIGH/CRITICAL review |

| Gitleaks | Secret detection | Block leaked secrets |

| Cosign | Image signing | Required |

| SLSA | Provenance | Required |





\---



\# Technologies



\- GitHub Actions

\- Docker

\- GHCR

\- Semgrep

\- Trivy

\- Gitleaks

\- Cosign

\- SLSA

