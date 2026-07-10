# Task 4 - Part A: Passive Reconnaissance

## Objective

Perform passive reconnaissance against the publicly exposed attack surface of **dodopayments.tech** using only publicly available information.

## Scope

Passive reconnaissance only.

No exploitation, vulnerability scanning, brute force, authentication attempts, fuzzing or denial of service activities were performed.

## Tools Used

- Subfinder
- Assetfinder
- HTTPX
- Certificate Transparency (via Subfinder/Assetfinder sources)

## Activities Performed

### 1. Subdomain Enumeration

Performed passive subdomain discovery using:

- Subfinder
- Assetfinder

Discovered approximately 111 unique subdomains.

### 2. Live Host Discovery

Verified discovered subdomains using HTTPX.

Result:

- 56 live hosts

### 3. Technology Fingerprinting

Collected:

- HTTP Status Codes
- Page Titles
- Technology Stack
- Server Fingerprints

using HTTPX.

## Output Files

output/

- subfinder.txt
- assetfinder.txt
- all-subdomains.txt
- live-hosts.txt
- httpx-tech.txt

## Screenshots

screenshots/

- 01-subfinder.png
- 01-subdomains.png
- 02-assetfinder.png
- 02-live-hosts.png
- 03-amass.png
- 03-output-files.png
- 04-httpx-tech-detection.png

## Notes

Only passive reconnaissance techniques were used throughout this assessment.

No active attacks or exploitation were performed.
