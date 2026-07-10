@'
# Task 4 - Part B: Application Security Assessment

## Objective
Perform a security assessment of the provided Ledger API application and identify security vulnerabilities.

## Target
Local Docker deployment of Ledger API

## Setup

### Build Image
docker build -t ledger-api .

### Run Container
docker run --rm -p 8080:8080 ledger-api

### Verify Application
curl http://localhost:8080/health

## Assessment Methodology

1. Source Code Review
2. Local Application Testing
3. Dependency Review
4. Vulnerability Validation

## Evidence Collected

### Screenshots
- 01-app-running.png
- 02-transactions.png
- 03-fetch-ssrf.png
- 04-tokenize.png
- 05-yaml-load.png
- 06-fetch-code.png
- 07-hardcoded-pan.png

## Findings Summary

| ID | Finding | Severity |
|----|----------|----------|
| F-01 | Sensitive Data Exposure | High |
| F-02 | Server Side Request Forgery | High |
| F-03 | Unsafe YAML Deserialization | Medium |
| F-04 | Outdated Dependencies | Medium |

## Conclusion

Multiple security issues were identified through source code review and local testing. No intrusive exploitation was performed.
