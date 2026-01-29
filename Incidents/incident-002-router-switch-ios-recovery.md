# Router & Switch Recovery + IOS Lifecycle Lab

## Overview

NOC-style walkthrough covering factory reset, config persistence, password recovery, config + IOS backups, ROMMON IOS recovery (TFTP), and switch IOS upgrade. Evidence files are linked under each step.

---

## Environment
- Router: Cisco 2911 (IOS 15.1(4)M4)
- Switch: Catalyst 2960 (12.2(25)FX → 15.0(2)SE4)
- TFTP Server: 10.10.10.10
- Router LAN: 10.10.10.0/24 (R1 G0/0 = 10.10.10.1)

---

## Topology
![Topology](../diagrams/incident-002-topology.png)

---

## Step 1: Pre-Reset Configuration Check
### Goal
Confirm hostname + interface config exist before reset
  
### Commands
- `show running-config`

### Evidence
- [show-running-config.txt](../Evidence/incident-002-show-running-config.txt)

---


  
