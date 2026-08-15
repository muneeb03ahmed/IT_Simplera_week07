# Enterprise VPN, Firewall & Secure Access Implementation

## IT-SIMPLERA SOLUTIONS — Network Administration Internship Program

**Week:** 07  
**Project:** Enterprise VPN, Firewall, and Secure Access Implementation  
**Department:** Network Administration  
**Environment:** GNS3  
**Cisco IOS:** C3725-ADVENTERPRISEK9-M  
**Submission Date:** 15 August 2026  

---

## 📌 Project Overview

This project implements a secure enterprise network infrastructure using GNS3 and Cisco IOS. The topology represents a Head Office (HQ), Lahore Branch, Karachi Branch, ISP/WAN infrastructure, internal LANs, a DMZ server, and a centralized monitoring server.

The implementation focuses on enterprise-grade network security, including IPsec Site-to-Site VPN, AAA authentication, SSH Version 2, device hardening, secure routing, firewall security, centralized monitoring, and connectivity verification.

The project was developed as part of the **IT-SIMPLERA SOLUTIONS Network Administration Internship Program — Week 07**.

---

## 🎯 Objectives

The primary objectives of this project were:

- Implement secure Site-to-Site IPsec VPN communication.
- Configure IKE/ISAKMP Phase 1.
- Configure IPsec Phase 2 and transform sets.
- Implement Pre-Shared Key authentication.
- Configure crypto maps and interesting-traffic ACLs.
- Implement secure administrative access using SSH Version 2.
- Configure AAA authentication using a local user database.
- Disable insecure Telnet access.
- Implement Zone-Based Firewall security.
- Apply basic Cisco device hardening.
- Secure routing and management traffic.
- Implement Syslog, NTP, and SNMPv3 monitoring.
- Verify encrypted communication between enterprise networks.
- Troubleshoot network and security failures.
- Document the complete enterprise security architecture.

---

# 🏗️ Network Topology

The enterprise topology consists of four major routing domains:

1. **Head Office**
2. **Lahore Branch**
3. **Karachi Branch**
4. **ISP/WAN Infrastructure**

Additional network resources include:

- HQ LAN
- Lahore LAN
- Karachi LAN
- DMZ Server
- Monitoring Server
- Three branch/HQ switches
- Multiple VPCS clients

---

## 🌐 Topology Diagram

```text
                         ┌───────────────────┐
                         │   Lahore-Router   │
                         │                   │
                         │   LAN: 192.168.20 │
                         └─────────┬─────────┘
                                   │
                                   │
                              ┌────▼────┐
                              │SW-Lahore│
                              └────┬────┘
                                   │
                                  PC3
                           192.168.20.10


                 ┌─────────────────────────────┐
                 │          ISP-Router         │
                 │          WAN CORE           │
                 └───────┬─────────┬───────────┘
                         /           \
                        /             \
                       /               \
              ┌───────▼──────┐   ┌────▼──────────┐
              │   HQ-Router   │   │Karachi-Router │
              └───────┬───────┘   └──────┬───────┘
                      │                   │
                 ┌────▼────┐         ┌────▼─────┐
                 │  SW-HQ  │         │SW-Karachi│
                 └──┬──┬───┘         └────┬─────┘
                    │  │                  │
                   PC1 PC2                PC2
                    │
              ┌─────┴──────────┐
              │                │
        DMZ-Server      Monitoring-Server
