# Task 3 - Istio Service Mesh

## Objective

Secure Kubernetes service-to-service communication by deploying the application with the Istio service mesh and configuring ingress traffic using an Istio Gateway and VirtualService.

---

## Environment

* Kubernetes: Kind
* Istio: 1.30.2
* Namespace: `payments`

---

## Steps Performed

### 1. Installed Istio

Installed the Istio demo profile using:

```bash
istioctl install --set profile=demo -y
```

Verified installation:

```bash
kubectl get pods -n istio-system
```

---

### 2. Enabled Automatic Sidecar Injection

Enabled Istio sidecar injection for the `payments` namespace.

```bash
kubectl label namespace payments istio-injection=enabled --overwrite
```

Verified:

```bash
kubectl get namespace payments --show-labels
```

---

### 3. Restarted the Deployment

Restarted the deployment so that the Envoy sidecar was automatically injected.

```bash
kubectl rollout restart deployment ledger-api -n payments
kubectl rollout status deployment ledger-api -n payments
```

---

### 4. Verified Sidecar Injection

Confirmed that the application pods contain the Istio sidecar proxy.

```bash
kubectl get pods -n payments
kubectl describe pod <ledger-api-pod> -n payments
```

The application pods are running with two containers:

* ledger-api
* istio-proxy

---

### 5. Created Istio Gateway

Created `gateway.yaml` to expose the application through the Istio Ingress Gateway.

```text
task3/manifests/gateway.yaml
```

Applied using:

```bash
kubectl apply -f task3/manifests/gateway.yaml
```

---

### 6. Created VirtualService

Created `virtualservice.yaml` to route incoming HTTP traffic to the Ledger API service.

```text
task3/manifests/virtualservice.yaml
```

Applied using:

```bash
kubectl apply -f task3/manifests/virtualservice.yaml
```

Verified:

```bash
kubectl get gateway -n payments
kubectl get virtualservice -n payments
```

---

## Verification

The following resources were successfully verified:

* Istio Control Plane
* Istio Gateway
* VirtualService
* Sidecar Injection
* Kubernetes Deployment
* Running Pods

---

## Screenshots

* 01-istio-installed.png
* 02-namespace-label.png
* 03-rollout.png
* 04-sidecar-injected.png
* 05-gateway-virtualservice.png
* 06-istio-services.png
* 07-final-verification.png
* 08-istio-sidecar.png

---

## Result

Successfully integrated the Ledger API with the Istio service mesh by enabling automatic sidecar injection, configuring an Istio Gateway and VirtualService, and verifying secure service mesh deployment.
