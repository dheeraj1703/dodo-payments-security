\# Task 1 - Deploy \& Harden Ledger API



\## Overview



The objective of Task 1 was to transform the insecure ledger-api workload into a production-grade Kubernetes deployment.



Security improvements implemented:



\- Kubernetes Deployment

\- Kubernetes Service

\- ConfigMap support

\- Dedicated ServiceAccount

\- Least privilege RBAC

\- Kubernetes Secrets

\- Non-root container execution

\- Read-only filesystem

\- Dropped Linux capabilities

\- Seccomp RuntimeDefault

\- Resource requests and limits

\- Liveness and readiness probes





\---



\# Architecture



User
|
Ingress
|
Service
|
Ledger API Deployment
|
Pods
|
ServiceAccount + RBAC
|
Secrets

---

# Security Hardening

## Container Security Context

Implemented:

```yaml
runAsNonRoot: true
allowPrivilegeEscalation: false
readOnlyRootFilesystem: true
capabilities:
  drop:
    - ALL
seccompProfile:
  type: RuntimeDefault

  Benefits:

Prevents root container execution
Reduces container escape risk
Removes unnecessary Linux privileges
Secret Management

Before:

Secrets were stored inside deployment manifests.

After:

Secrets are stored separately using Kubernetes Secret objects.

Example:

secret.yaml

Contains:

STRIPE_API_KEY
DB_PASSWORD

Deployment consumes secrets using:

secretKeyRef
Service Account

Created dedicated service account:

ledger-api-sa

The default Kubernetes service account is not used.

RBAC

Implemented namespace scoped RBAC.

Resources:

Role
RoleBinding

Principle:

Least privilege access only.