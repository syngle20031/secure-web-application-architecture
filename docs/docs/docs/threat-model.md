# Threat Model

## Purpose

This threat model identifies potential threats to the secure web application architecture and the controls used to reduce their impact.

## Assets

The main assets include:

- Public web application
- Web server
- Internal systems
- Administrative systems
- Application data
- Network infrastructure

## Threat 1: Unauthorized Internet Access

### Threat

An attacker may attempt to access services that should not be publicly available.

### Mitigation

The external firewall should restrict inbound traffic to approved public services.

## Threat 2: Web Server Compromise

### Threat

An attacker may exploit a vulnerability in the public-facing web application or server.

### Mitigation

The web server is isolated inside a DMZ rather than being placed directly inside the internal network.

Additional protections could include:

- WAF
- IDS/IPS
- Security patching
- Vulnerability scanning
- Server hardening

## Threat 3: Lateral Movement

### Threat

After compromising the web server, an attacker may attempt to move into the internal network.

### Mitigation

An internal firewall separates the DMZ from internal systems.

DMZ-to-internal traffic should be restricted to required application flows.

## Threat 4: Excessive Access

### Threat

A compromised system may have more network access than necessary.

### Mitigation

Use least-privilege firewall rules and restrict communication between security zones.

## Threat 5: Data Exposure

### Threat

Sensitive internal data could be exposed if internal resources are directly reachable from the Internet.

### Mitigation

Internal resources remain behind the internal firewall and are not directly exposed to external users.

## Security Approach

The architecture uses:

- Network segmentation
- DMZ isolation
- Defense in depth
- Least privilege
- Restricted traffic flows
- Multiple security boundaries
