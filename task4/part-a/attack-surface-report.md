# Attack Surface Report

## Executive Summary

A passive reconnaissance assessment was conducted against the publicly exposed attack surface of **dodopayments.tech**.

The assessment focused on identifying publicly accessible assets without interacting with application functionality beyond normal HTTP requests.

No active testing or exploitation was performed.

---

# Findings Summary

## Root Domain

dodopayments.tech

## Unique Subdomains

111

## Live Hosts

56

---

# Technologies Observed

The following technologies were identified during passive fingerprinting:

- Cloudflare
- Cloudflare Bot Management
- Envoy
- Vercel
- Next.js
- React
- Node.js
- SonarQube
- ClickHouse
- Google Cloud
- Google Cloud CDN
- n8n

---

# Interesting Public Assets

Examples include:

- SonarQube
- ClickHouse
- n8n
- Plunk
- Customer Portal
- Checkout
- API Endpoints
- Internal Portal
- AI Proxy
- SSR Proxy

---

# Security Observations

Positive observations:

- Extensive Cloudflare usage
- WAF/Bot protection observed
- HSTS enabled on many hosts
- Multiple services return 401 or 403 instead of exposing content

Potential observations:

- Large attack surface
- Multiple development environments publicly reachable
- Numerous internal service names exposed through DNS
- Several administrative interfaces publicly accessible

These observations are informational only and do not imply vulnerabilities.

---

# Methodology

Tools Used

- Subfinder
- Assetfinder
- HTTPX

Activities

- Passive DNS Enumeration
- Certificate Transparency Enumeration
- Live Host Verification
- Technology Fingerprinting

---

# Conclusion

The reconnaissance successfully identified publicly accessible infrastructure while remaining completely within passive reconnaissance scope.

No exploitation or intrusive testing was performed.
