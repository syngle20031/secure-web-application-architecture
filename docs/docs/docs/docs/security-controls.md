# Security Controls

This document describes the main security controls represented in the architecture.

## External Firewall

The external firewall provides the first security boundary between untrusted Internet users and the organization's infrastructure.

It should allow only required traffic to publicly exposed services. HTTPS over TCP port 443 is the primary expected public service.

## DMZ

The public-facing web server is placed in a DMZ (Demilitarized Zone).

The DMZ isolates Internet-facing services from the trusted internal network.

## Internal Firewall

A second firewall separates the DMZ from the internal zone.

Traffic moving from the DMZ toward internal systems should be restricted according to application requirements.

## Network Segmentation

The architecture separates systems into:

- External / untrusted zone
- DMZ / limited-trust zone
- Internal / trusted zone

## Least-Privilege Access

Firewall rules should permit only necessary traffic and services. The web server should not have unrestricted access to internal systems.

## Defense in Depth

The design uses multiple layers:

1. External firewall
2. DMZ isolation
3. Internal firewall
4. Restricted traffic flows
5. Internal network segmentation

## Future Enhancements

A production deployment could add:

- Web Application Firewall (WAF)
- IDS/IPS
- Centralized logging
- SIEM
- Vulnerability scanning
- Network monitoring
- MFA
- Server hardening
- TLS certificate management
