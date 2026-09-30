# Architecture Overview

## Purpose

This project presents a segmented network architecture for protecting a public-facing web application while keeping internal resources separated from Internet-facing services.

## Traffic Flow

The primary traffic flow is:

External Users → External Firewall → DMZ Web Server → Internal Firewall → Internal Zone

### 1. External Users

Users access the public-facing application from an untrusted external network.

### 2. External Firewall

The external firewall provides the first security boundary. It controls which traffic is allowed to reach the public-facing service.

The architecture primarily permits HTTPS traffic to the web application.

### 3. DMZ Web Server

The web server is placed in a DMZ, or demilitarized zone.

This prevents the public-facing server from being placed directly inside the trusted internal network.

### 4. Internal Firewall

A second firewall separates the DMZ from the internal network.

Traffic from the DMZ toward internal resources should be restricted to only the connections required by the application.

### 5. Internal Zone

The internal zone contains trusted resources such as administrative systems, application services, and protected data.

## Security Principle

The architecture follows a defense-in-depth approach. Multiple security boundaries are used instead of relying on a single firewall or security control.

## Key Concepts

- Network segmentation
- DMZ architecture
- Defense in depth
- Least-privilege access
- Perimeter security
- Internal network protection
- Controlled traffic flow
