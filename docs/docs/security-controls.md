# Security Controls

This document describes the main security controls represented in the architecture.

## 1. External Firewall

The external firewall provides the first security boundary between untrusted Internet users and the organization's infrastructure.

It should allow only required traffic to publicly exposed services.

For the web application, HTTPS traffic over TCP port 443 is the primary expected public service.

## 2. DMZ

The public-facing web server is placed in a DMZ (Demilitarized Zone).

The DMZ provides isolation between Internet-facing services and the trusted internal network.

If the web server is compromised, the attacker does not automatically gain direct access to internal systems.

## 3. Internal Firewall

A second firewall separates the DMZ from the internal zone.

Traffic moving from the DMZ toward internal systems should be restricted according to application requirements.

This provides an additional layer of protection against lateral movement.

## 4. Network Segmentation

The architecture separates systems according to their security requirements:

- External / untrusted zone
- DMZ / limited-trust zone
- Internal / trusted zone

Segmentation reduces the amount of the network that is exposed if one component is compromised.

## 5. Least-Privilege Access

Firewall rules should permit only the traffic and services that are necessary.

For example, the web server should not have unrestricted access to internal systems.

## 6. Defense in Depth

The design does not depend on a single security control.

Security is provided through multiple layers:

1. External firewall
2. DMZ isolation
3. Internal firewall
4. Restricted traffic flows
5. Internal network segmentation

## Future Security Enhancements

A production deployment could additionally implement:

- Web Application Firewall (WAF)
- Intrusion Detection/Prevention System (IDS/IPS)
- Centralized security logging
- SIEM
- Vulnerability scanning
- Network monitoring
- Multi-factor authentication
- Strong server hardening
- TLS certificate management
