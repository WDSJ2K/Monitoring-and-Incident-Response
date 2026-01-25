# IOS Device Initial Configuration & Interface Validation (Packet Tracer)

## Objective
Bring up a small Cisco topology (R1–SW1–R2) by assigning IP addressing and switch management access, then validate connectivity, CDP neighbors, and interface behavior during shutdown + duplex/speed mismatch testing.

## Topology
-![Topology](diagrams/topology(001).png)
- SW1 Fa0/1 ↔ R1 Fa0/0
- SW1 Fa0/2 ↔ R2 Fa0/0

## Addressing
- R1 Fa0/0: `10.10.10.1/24`
- R2 Fa0/0: `10.10.10.2/24`
- SW1 VLAN 1 SVI (management): `10.10.10.10/24`
- SW1 default gateway: `10.10.10.2` (R2)

## Verification (Key Commands)
```cisco
show ip interface brief
show interfaces status
show cdp neighbors
ping 10.10.10.2

 What I Validated / Learned

-Configured router interface IPs and switch management SVI for remote management access.

-Confirmed switch-to-router connectivity using ping and interface state checks.

-Used CDP to verify directly connected neighbors and physical port mapping.

-Disabled CDP on a single switch port to prevent device discovery (per-  interface hardening).

-Observed how shutdown/no shutdown and duplex/speed changes impact link state (up/up vs down/down).
