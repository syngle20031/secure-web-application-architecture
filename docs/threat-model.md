# Threat Model

## Purpose

This threat model identifies potential threats to the secure web application architecture and the controls used to reduce their impact.

## Assets

- Public web application
- Web server
- Internal systems
- Administrative systems
- Application data
- Network infrastructure

## Unauthorized Internet Access

**Threat:** An attacker may attempt to access services that should not be publicly available.

**Mitigation:** The external firewall should restrict inbound traffic to approved public services.

## Web Server Compromise

**Threat:** An attacker may exploit a vulnerability in the public-facing web application or server.

**Mitigation:** The web server is isolated inside a DMZ. Additional protections could include WAF, IDS/IPS, patching, vulnerability scanning, and server hardening.

## Lateral Movement

**Threat:** After compromising the web server, an attacker may attempt to move into the internal network.

**Mitigation:** An internal firewall separates the DMZ from internal systems, with DMZ-to-internal traffic restricted to required application flows.

## Excessive Access

**Threat:** A compromised system may have more network access than necessary.

**Mitigation:** Use least-privilege firewall rules and restrict communication between security zones.

## Data Exposure

**Threat:** Sensitive internal data could be exposed if internal resources are directly reachable from the Internet.

**Mitigation:** Internal resources remain behind the internal firewall and are not directly exposed to external users.

## Security Approach

The architecture uses:

- Network segmentation
- DMZ isolation
- Defense in depth
- Least privilege
- Restricted traffic flows
- Multiple security boundaries
