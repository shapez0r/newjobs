# Week 3 Detailed Workbook: Networking Fundamentals for Data Centers

## Table of contents

- [Purpose of this workbook](#purpose-of-this-workbook)
- [Week 3 target level](#week-3-target-level)
- [Suggested weekly schedule](#suggested-weekly-schedule)
- [Day-by-day Week 3 study order](#day-by-day-week-3-study-order)
- [Required Week 3 portfolio artifacts](#required-week-3-portfolio-artifacts)
- [Part 1: Comprehensive Week 3 topics](#part-1-comprehensive-week-3-topics)
  - [1. Networking mindset for data center work](#1-networking-mindset-for-data-center-work)
  - [2. OSI model in practical terms](#2-osi-model-in-practical-terms)
  - [3. Ethernet MAC addresses and ARP](#3-ethernet-mac-addresses-and-arp)
  - [4. IP addressing subnet masks and gateways](#4-ip-addressing-subnet-masks-and-gateways)
  - [5. Practical subnetting](#5-practical-subnetting)
  - [6. DNS and DHCP](#6-dns-and-dhcp)
  - [7. Copper cabling patch panels and RJ45](#7-copper-cabling-patch-panels-and-rj45)
  - [8. Fiber optics transceivers and connector care](#8-fiber-optics-transceivers-and-connector-care)
  - [9. Switches routers firewalls and load balancers](#9-switches-routers-firewalls-and-load-balancers)
  - [10. VLANs access ports and trunk ports](#10-vlans-access-ports-and-trunk-ports)
  - [11. Link speed duplex and negotiation](#11-link-speed-duplex-and-negotiation)
  - [12. Network command evidence](#12-network-command-evidence)
  - [13. Network diagrams port maps and labels](#13-network-diagrams-port-maps-and-labels)
  - [14. Physical layer troubleshooting](#14-physical-layer-troubleshooting)
  - [15. Ticket updates escalation and safe boundaries](#15-ticket-updates-escalation-and-safe-boundaries)
- [Part 2: Week 3 questions and model answers](#part-2-week-3-questions-and-model-answers)
  - [Networking fundamentals](#networking-fundamentals)
  - [IP addressing and subnetting](#ip-addressing-and-subnetting)
  - [DNS DHCP and name resolution](#dns-dhcp-and-name-resolution)
  - [Cabling fiber and physical checks](#cabling-fiber-and-physical-checks)
  - [Switching routing and VLANs](#switching-routing-and-vlans)
  - [Troubleshooting scenarios](#troubleshooting-scenarios)
- [Part 3: Lab exercises with hints](#part-3-lab-exercises-with-hints)
  - [Lab 1: Build a practical OSI model map](#lab-1-build-a-practical-osi-model-map)
  - [Lab 2: Complete a subnetting worksheet](#lab-2-complete-a-subnetting-worksheet)
  - [Lab 3: Discover and diagram a home network](#lab-3-discover-and-diagram-a-home-network)
  - [Lab 4: Compare IP DNS DHCP and gateway failures](#lab-4-compare-ip-dns-dhcp-and-gateway-failures)
  - [Lab 5: Collect Windows network evidence](#lab-5-collect-windows-network-evidence)
  - [Lab 6: Collect Linux network evidence](#lab-6-collect-linux-network-evidence)
  - [Lab 7: Observe ARP and MAC addresses](#lab-7-observe-arp-and-mac-addresses)
  - [Lab 8: Create a rack-to-switch port map](#lab-8-create-a-rack-to-switch-port-map)
  - [Lab 9: Create a cable labeling standard](#lab-9-create-a-cable-labeling-standard)
  - [Lab 10: Build fiber handling notes](#lab-10-build-fiber-handling-notes)
  - [Lab 11: Create a two-VLAN diagram or Packet Tracer lab](#lab-11-create-a-two-vlan-diagram-or-packet-tracer-lab)
  - [Lab 12: Build a network troubleshooting flowchart](#lab-12-build-a-network-troubleshooting-flowchart)
  - [Lab 13: Write mock network ticket updates](#lab-13-write-mock-network-ticket-updates)
  - [Lab 14: Build a Week 3 mock interview script](#lab-14-build-a-week-3-mock-interview-script)
  - [Lab 15: Final Week 3 self-assessment](#lab-15-final-week-3-self-assessment)
- [Part 4: Templates to copy into the portfolio](#part-4-templates-to-copy-into-the-portfolio)
  - [Rack-to-switch port map template](#rack-to-switch-port-map-template)
  - [Cable trace checklist](#cable-trace-checklist)
  - [Network troubleshooting ticket template](#network-troubleshooting-ticket-template)
  - [Subnetting worksheet template](#subnetting-worksheet-template)
  - [DNS and DHCP evidence template](#dns-and-dhcp-evidence-template)
  - [Network escalation template](#network-escalation-template)
- [Part 5: Week 3 final exam](#part-5-week-3-final-exam)
  - [Written exam](#written-exam)
  - [Practical exam](#practical-exam)
  - [Passing standard](#passing-standard)
- [Part 6: Interview positioning for Week 3](#part-6-interview-positioning-for-week-3)
  - [Strong interview themes](#strong-interview-themes)
  - [Example answer: server has no network link](#example-answer-server-has-no-network-link)
  - [Example answer: DNS works differently from IP connectivity](#example-answer-dns-works-differently-from-ip-connectivity)
  - [Example answer: VLANs in plain English](#example-answer-vlans-in-plain-english)
- [Part 7: Week 3 completion checklist](#part-7-week-3-completion-checklist)

## Purpose of this workbook

This workbook expands **Week 3** of the Data Center Engineer / Data Center Technician study plan. It is written for a complete beginner who needs practical network confidence for data center work.

The goal is not to turn her into a network engineer in one week. The goal is to make her useful and safe around network tasks: understand what a cable or port ticket is asking, identify missing information, collect basic evidence, explain common network terms, and escalate clearly when the task requires network engineering authority.

By the end of this week, she should be able to reason from physical link to IP configuration to DNS. She should also be able to produce clean port maps, cable labels, troubleshooting notes, and interview answers that sound practical rather than memorized.

## Week 3 target level

The target is not "I watched a subnetting video." The target is:

- She can explain the OSI model as a troubleshooting tool, not just recite the layers.
- She can explain MAC addresses, ARP, IP addresses, subnet masks, gateways, DNS, and DHCP in plain English.
- She can calculate common subnets such as `/24`, `/25`, `/26`, `/27`, and `/28`.
- She can identify copper and fiber cabling types used in data centers.
- She understands why cable labels, patch panels, switch ports, and rack positions must be verified before touching anything.
- She can explain switches, routers, firewalls, load balancers, VLANs, access ports, and trunk ports at a junior level.
- She can use basic Windows and Linux network commands to gather evidence.
- She can tell the difference between link failure, IP misconfiguration, routing failure, and DNS failure in simple scenarios.
- She can write safe ticket updates for cable traces, link-down checks, and network evidence collection.
- She knows when to stop and escalate instead of changing cables or switch configuration without approval.

## Suggested weekly schedule

| Day | Focus | Main output |
|---|---|---|
| Day 1 | OSI model, Ethernet, MAC addresses, and ARP | Practical OSI map and MAC/ARP notes |
| Day 2 | IP addresses, subnet masks, gateways, and subnetting | Subnet worksheet and home network diagram |
| Day 3 | DNS, DHCP, and command-line network checks | Windows/Linux command evidence notes |
| Day 4 | Copper, fiber, patch panels, switch ports, and VLANs | Port map, cable labels, and two-VLAN diagram |
| Day 5 | Troubleshooting, ticket updates, escalation, and interview practice | Network flowchart, mock tickets, and interview script |
| Day 6 optional | Repeat subnetting and command checks without notes | Corrected worksheets and screenshots |
| Day 7 optional | Rest or catch-up | Clean Week 3 portfolio |

## Day-by-day Week 3 study order

Use this as the working order for the week. The reference sections, questions, labs, and templates remain below, but the learner should complete them in this sequence.

| Day | Study sections | Practice | Portfolio output |
|---|---|---|---|
| Day 1 | Sections 1-3: networking mindset, OSI model, Ethernet, MAC addresses, and ARP | Labs 1 and 7; Questions 1-12 | OSI troubleshooting map and MAC/ARP notes |
| Day 2 | Sections 4-5: IP addresses, subnet masks, gateways, and practical subnetting | Labs 2-3; Questions 13-24 | Subnet worksheet and home network diagram |
| Day 3 | Sections 6 and 12: DNS, DHCP, and command evidence | Labs 4-6; Questions 25-34 | DNS/DHCP comparison notes and Windows/Linux command outputs |
| Day 4 | Sections 7-11 and 13: cabling, fiber, network devices, VLANs, link speed, diagrams, and labels | Labs 8-11; Questions 35-52 | Rack-to-switch port map, cable labeling standard, and VLAN diagram |
| Day 5 | Sections 14-15: physical troubleshooting, ticket updates, safe boundaries, and escalation | Labs 12-15; Questions 53-65 | Troubleshooting flowchart, mock network tickets, interview script, and self-assessment |
| Day 6 optional | Repeat subnetting, command checks, and scenarios aloud | Rework weak labs and command notes | Corrected artifacts and screenshots |
| Day 7 optional | Rest or catch-up | Fill missing portfolio files | Ready-to-review Week 3 portfolio |

## Required Week 3 portfolio artifacts

Create a folder called `week-03-networking` and include:

```text
week-03-networking/
  README.md
  01-practical-osi-model-map.md or .drawio
  02-subnetting-worksheet.md
  03-home-network-diagram.png or .drawio
  04-dns-dhcp-gateway-failure-notes.md
  05-windows-network-command-evidence.md
  06-linux-network-command-evidence.md
  07-mac-arp-notes.md
  08-rack-to-switch-port-map.md or .csv
  09-cable-labeling-standard.md
  10-fiber-handling-notes.md
  11-two-vlan-diagram.md or .pkt
  12-network-troubleshooting-flowchart.md
  13-mock-network-ticket-updates.md
  14-week-03-interview-script.md
  15-week-03-self-assessment.md
```

---

# Part 1: Comprehensive Week 3 topics

## 1. Networking mindset for data center work

Data center technicians do not usually design the network, but they work around the network every day. A technician may be asked to trace cables, confirm link lights, identify switch ports, check management connectivity, record MAC addresses, or run basic commands for a remote engineer.

The most important mindset is: **observe and verify before changing anything**.

Network tasks can be risky because one wrong cable move can disconnect a production server, storage path, firewall uplink, or customer circuit. A junior technician should be able to collect facts, compare them with the ticket, and stop when the physical state does not match the documented plan.

### Common data center network tasks

- Trace a cable from a server NIC to a patch panel or switch port.
- Check whether link lights are on, off, or blinking.
- Confirm cable labels and port labels.
- Replace a patch cable during an approved change.
- Record MAC addresses or switch port information.
- Provide console output for IP, route, DNS, and interface checks.
- Document a rack-to-switch port map.
- Escalate to network engineers when switch configuration may be involved.

### Safe beginner boundary

A technician may physically inspect and document. A technician should not change switch configuration, move production uplinks, or disconnect ambiguous cables without explicit authorization.

## 2. OSI model in practical terms

The OSI model is useful because it helps troubleshoot in layers. She does not need to memorize textbook detail. She needs to know how to ask: where could this problem be?

| Layer | Plain meaning | Data center example |
|---|---|---|
| Layer 1 Physical | Cables, optics, ports, electrical/optical signal | Cable unplugged, bad optic, no link light |
| Layer 2 Data link | Ethernet, MAC addresses, VLANs, switching | Wrong VLAN, MAC not learned, port disabled |
| Layer 3 Network | IP addresses, routes, gateways | Wrong IP, wrong gateway, routing failure |
| Layer 4 Transport | TCP/UDP ports | Service port blocked or not listening |
| Layer 5 Session | Connection state | Session timeout or reset |
| Layer 6 Presentation | Encoding/encryption | TLS/certificate issue |
| Layer 7 Application | Application protocol | Web service, DNS query, SSH login |

### Practical troubleshooting idea

Start with the simplest evidence:

1. Is the cable connected and is there link?
2. Does the interface appear up?
3. Does the device have the expected IP address?
4. Is there a route and gateway?
5. Can it ping an IP?
6. Can it resolve a name with DNS?
7. Is the target service listening or reachable?

## 3. Ethernet MAC addresses and ARP

Ethernet is the common local network technology used in data centers. Devices communicate locally using MAC addresses.

### MAC address

A MAC address is a hardware address assigned to a network interface. It usually looks like:

```text
00:1A:2B:3C:4D:5E
```

In data center work, MAC addresses help identify which physical NIC is connected to which switch port or which VM/interface is generating traffic.

### ARP

ARP means Address Resolution Protocol. It maps an IPv4 address to a MAC address on the local network.

Example idea:

```text
Who has 192.168.1.1?
192.168.1.1 is at 34:12:98:aa:bb:cc
```

### Why this matters

If a server has an IP address but cannot reach the gateway, ARP evidence can help show whether the server can see the gateway at Layer 2. If a MAC address does not appear where expected, the cable, switch port, VLAN, or NIC mapping may be wrong.

## 4. IP addressing subnet masks and gateways

An IP address identifies a device at Layer 3. A subnet mask tells the device which addresses are local and which must go through a gateway.

### Example

```text
IP address: 192.168.10.25
Subnet:    255.255.255.0 or /24
Gateway:   192.168.10.1
```

In a `/24`, `192.168.10.25` usually treats `192.168.10.1` through `192.168.10.254` as local usable addresses.

### Gateway

The default gateway is the router used to reach other networks. If the gateway is wrong or unreachable, the server may communicate locally but fail to reach remote networks.

### Data center relevance

Tickets may ask a technician to confirm:

- Current IP address.
- Subnet mask or prefix length.
- Default gateway.
- Interface name.
- Whether the address is static or assigned by DHCP.
- Whether the configured details match the expected build sheet.

## 5. Practical subnetting

Subnetting divides a larger network into smaller networks. A junior technician does not need to do complex design, but she should recognize common prefix lengths.

| Prefix | Mask | Total addresses | Usable IPv4 addresses | Common use |
|---|---|---:|---:|---|
| `/24` | 255.255.255.0 | 256 | 254 | General small network |
| `/25` | 255.255.255.128 | 128 | 126 | Half of a `/24` |
| `/26` | 255.255.255.192 | 64 | 62 | Smaller segment |
| `/27` | 255.255.255.224 | 32 | 30 | Small server group |
| `/28` | 255.255.255.240 | 16 | 14 | Very small segment |

### Simple method for common subnets

For a `/24`, the block size is 256. For smaller networks:

- `/25` block size is 128.
- `/26` block size is 64.
- `/27` block size is 32.
- `/28` block size is 16.

Example: `192.168.10.70/26`

- `/26` block size is 64.
- Ranges are `192.168.10.0-63`, `192.168.10.64-127`, `192.168.10.128-191`, `192.168.10.192-255`.
- `70` belongs in `192.168.10.64-127`.
- Network address: `192.168.10.64`.
- Broadcast address: `192.168.10.127`.
- Usable range: `192.168.10.65-126`.

## 6. DNS and DHCP

### DNS

DNS translates names into IP addresses. When a user connects to `example.com`, the system asks DNS which IP address to use.

DNS failure can look like "the internet is down" to a beginner, but IP connectivity may still work.

Example:

```text
ping 8.8.8.8 works
nslookup google.com fails
```

That suggests basic IP connectivity exists, but DNS resolution may be broken.

### DHCP

DHCP automatically assigns network settings such as IP address, subnet mask, gateway, and DNS servers.

Data center servers often use static addresses for production interfaces, but DHCP may be used for build networks, PXE boot, management networks, or lab environments.

### Why this matters

A technician may need to distinguish:

- No link: physical or switch port issue.
- No IP address: static config or DHCP issue.
- IP works but name fails: DNS issue.
- Local IP works but remote IP fails: gateway/routing/firewall issue.

## 7. Copper cabling patch panels and RJ45

Copper Ethernet cabling is common for management ports, lower-speed server connections, office networks, and some data center links.

### Terms to know

- Cat5e: common copper cabling that can support 1 GbE and sometimes more depending on length and environment.
- Cat6/Cat6a: supports higher performance and is common in newer cabling.
- RJ45: common Ethernet connector.
- Patch cable: short cable between device and patch panel or switch.
- Patch panel: fixed cabling termination point.
- Cable tester: tool used to test wiring continuity and basic faults.
- Link light: LED showing whether the physical connection is up.

### Safe handling

- Do not yank cables.
- Do not bend cables sharply.
- Do not disconnect unlabeled or ambiguous cables.
- Verify both ends before replacing a cable.
- Keep cable paths tidy to protect airflow and maintenance access.

## 8. Fiber optics transceivers and connector care

Fiber cabling uses light to carry data. It is common in data centers for high-speed links, uplinks, storage networks, and longer distances.

### Terms to know

- Single-mode fiber: often used for longer distances; usually yellow jacket.
- Multi-mode fiber: often used for shorter data center distances; often aqua or orange jacket.
- LC connector: small fiber connector common in data centers.
- Transceiver or optic: module inserted into switch/NIC ports, such as SFP, SFP+, QSFP, or QSFP28.
- Dust cap: cap that protects unused fiber ends and optics.
- Polarity: direction/pairing of transmit and receive fibers.

### Safety and cleanliness

- Never look into fiber ends or optics.
- Keep dust caps on unused connectors.
- Do not touch fiber end faces.
- Avoid tight bends.
- Use approved cleaning tools if trained.
- Treat fibers and optics as delicate parts.

## 9. Switches routers firewalls and load balancers

### Switch

A switch connects devices on the same local network and forwards Ethernet frames based on MAC addresses.

### Router

A router connects different IP networks and forwards packets based on IP addresses.

### Firewall

A firewall allows or blocks traffic based on security rules. Firewalls may inspect source, destination, port, protocol, state, and sometimes application data.

### Load balancer

A load balancer distributes traffic across multiple servers or services. It can improve availability and performance.

### Technician boundary

Technicians may connect cables to these devices, check labels, and report LED states. Configuration changes normally belong to network or platform engineers.

## 10. VLANs access ports and trunk ports

A VLAN is a logical network segment on switches. VLANs let different networks share the same physical switch infrastructure while remaining separated at Layer 2.

### Access port

An access port usually carries traffic for one VLAN. A server NIC connected to an access port may not need to know about VLAN tags.

### Trunk port

A trunk port carries multiple VLANs, often between switches or to servers/hypervisors that understand VLAN tags.

### Why VLANs matter

If a server is connected to the wrong VLAN, it may have link but still be unable to reach the expected network. This is why a "link light is on" does not prove the network path is correct.

### Junior explanation

A VLAN is like a separate logical room inside the same switch. Devices in one VLAN do not automatically talk to devices in another VLAN unless routing and policy allow it.

## 11. Link speed duplex and negotiation

Link speed describes how fast an Ethernet link is operating, such as 1 Gbps, 10 Gbps, 25 Gbps, or 100 Gbps.

Duplex describes whether traffic can flow both ways at the same time. Modern switched Ethernet is usually full duplex.

### Auto-negotiation

Many links automatically negotiate speed and duplex. If negotiation fails or the port is forced to a mismatched setting, the link may be down or degraded.

### Evidence to collect

- Is the link light on?
- What speed does the OS report?
- What speed does the switch report, if the network engineer provides it?
- Did the issue begin after a cable, optic, NIC, or switch-port change?
- Are errors, drops, or flaps being reported?

## 12. Network command evidence

Commands help collect facts. The goal is evidence, not guessing.

### Windows commands

```cmd
ipconfig /all
ping 8.8.8.8
nslookup google.com
tracert google.com
arp -a
route print
```

### Linux commands

```bash
ip addr
ip link
ip route
ping -c 4 8.8.8.8
resolvectl status
ss -tulpn
traceroute google.com
```

### What to record

- Exact command run.
- Time run.
- Relevant output.
- What the output proves.
- What it does not prove.

## 13. Network diagrams port maps and labels

Network documentation prevents mistakes. A port map should show where each server interface connects.

### Example label

```text
R12-U18-NIC1 -> PP-A-24 -> SW01-Eth1/12
```

### Useful fields

- Rack.
- U position.
- Hostname.
- Asset tag.
- Server interface.
- Cable label.
- Patch panel port.
- Switch name.
- Switch port.
- VLAN or network name if approved to record.
- Link speed.
- Notes.

### Quality bar

Someone else should be able to identify the same cable and port from the documentation without relying on memory.

## 14. Physical layer troubleshooting

Physical layer checks are common technician work.

### Link down checks

- Confirm correct rack, U position, hostname, and asset tag.
- Confirm correct NIC or management port.
- Check link LED state without moving cables.
- Check cable label at both ends if accessible.
- Check whether the cable is seated.
- Check for obvious damage or tight bends.
- Check patch panel and switch port labels.
- Record photos if allowed.
- Do not disconnect or reseat unless approved.

### Common causes

- Cable unplugged.
- Wrong cable.
- Bad patch cable.
- Bad optic.
- Dirty fiber connector.
- Wrong switch port.
- Port disabled.
- Wrong VLAN.
- NIC failure.
- Maintenance on upstream device.

## 15. Ticket updates escalation and safe boundaries

Network ticket updates should be factual and careful. Avoid vague phrases such as "network is broken" or "cable looks fine."

### Good update structure

```text
Time:
Location:
Asset verified:
Interface/port checked:
Observed link state:
Cable/label evidence:
Commands run:
Changes made:
Current status:
Blocker/risk:
Next step:
```

### Escalate when

- The cable label is missing or does not match the ticket.
- The switch port is not confirmed.
- Link is up but the server is still unreachable.
- The task requires switch configuration.
- The ticket asks for a disconnect but does not identify both ends.
- The requested action could affect production traffic.
- The VLAN or network name does not match documentation.
- Fiber cleaning or optic replacement is required and she is not trained.
- A remote instruction differs from the ticket.

---

# Part 2: Week 3 questions and model answers

Use these as flashcards and mock interview practice. She should answer aloud first, then compare with the model answer.

## Networking fundamentals

### 1. Why does a data center technician need networking knowledge?

**Answer:** A technician works around cables, switch ports, server NICs, management networks, and connectivity tickets. She may not configure the network, but she must verify physical connections, collect evidence, document accurately, and escalate clearly.

### 2. What is the OSI model useful for?

**Answer:** It helps troubleshoot in layers. A link problem is different from an IP problem, and an IP problem is different from a DNS problem. The OSI model helps avoid random guessing.

### 3. What is Layer 1?

**Answer:** Layer 1 is the physical layer: cables, optics, ports, signal, and link lights.

### 4. What is Layer 2?

**Answer:** Layer 2 is the data link layer: Ethernet, MAC addresses, switching, ARP, and VLAN behavior.

### 5. What is Layer 3?

**Answer:** Layer 3 is the network layer: IP addresses, subnet masks, gateways, and routing between networks.

### 6. What is a MAC address?

**Answer:** A MAC address is a hardware address for a network interface. Switches use MAC addresses to forward traffic on a local network.

### 7. What is ARP?

**Answer:** ARP maps an IPv4 address to a MAC address on the local network. It helps a device find the local Ethernet address for another local IP, such as the default gateway.

### 8. What does a link light prove?

**Answer:** It proves there is some physical link at the port. It does not prove the VLAN, IP address, routing, DNS, or application is correct.

### 9. What is the difference between a NIC and a switch port?

**Answer:** A NIC is the network interface on a server or device. A switch port is the network port on the switch that the cable connects to.

### 10. Why should she avoid changing cables without approval?

**Answer:** The cable may carry production traffic. Moving or disconnecting the wrong cable can cause an outage, data path failure, or customer impact.

### 11. What is a management network?

**Answer:** A management network is used to manage devices, such as BMC/iDRAC/iLO, switches, or other infrastructure. It is often separate from production traffic.

### 12. What does "remote hands" mean in a network ticket?

**Answer:** It means a technician physically performs or observes something on behalf of a remote engineer, such as checking link lights, tracing a cable, or reading a label.

## IP addressing and subnetting

### 13. What is an IP address?

**Answer:** An IP address identifies a device at Layer 3 so it can communicate on an IP network.

### 14. What is a subnet mask?

**Answer:** A subnet mask tells a device which IP addresses are local and which are remote. Remote traffic is sent through the gateway.

### 15. What is a default gateway?

**Answer:** The default gateway is the router a device uses to reach other networks.

### 16. What does `/24` mean?

**Answer:** `/24` means the first 24 bits are the network portion. In IPv4 it is commonly written as `255.255.255.0` and usually has 254 usable host addresses.

### 17. How many usable addresses are in a `/25`?

**Answer:** A `/25` has 128 total addresses and usually 126 usable host addresses.

### 18. How many usable addresses are in a `/26`?

**Answer:** A `/26` has 64 total addresses and usually 62 usable host addresses.

### 19. What is the network address of `10.10.10.75/26`?

**Answer:** `/26` blocks are 64 addresses. The ranges are `0-63`, `64-127`, `128-191`, and `192-255`, so `10.10.10.75` is in `10.10.10.64/26`. The network address is `10.10.10.64`.

### 20. What is the broadcast address of `10.10.10.75/26`?

**Answer:** The broadcast address is the last address in the block, `10.10.10.127`.

### 21. Why can two devices with correct-looking IP addresses still fail to communicate?

**Answer:** They may be in different subnets, have the wrong gateway, be on different VLANs, have firewall rules between them, or have a physical/link issue.

### 22. What happens if the gateway is wrong?

**Answer:** The device may reach local addresses but fail to reach other networks.

### 23. What is an APIPA address on Windows?

**Answer:** It is an address in the `169.254.x.x` range that Windows may assign when DHCP fails. It usually indicates the device did not receive a normal DHCP address.

### 24. Should production servers usually rely on random DHCP leases?

**Answer:** Usually no. Production servers often use static addressing or controlled DHCP reservations, depending on the environment. The key is that the expected addressing method should be documented.

## DNS DHCP and name resolution

### 25. What is DNS?

**Answer:** DNS translates names such as `google.com` into IP addresses.

### 26. What is DHCP?

**Answer:** DHCP automatically provides network settings such as IP address, subnet mask, gateway, and DNS servers.

### 27. If `ping 8.8.8.8` works but `nslookup google.com` fails, what might be wrong?

**Answer:** Basic IP connectivity may be working, but DNS resolution may be broken or misconfigured.

### 28. If a server has no IP address, what should she check?

**Answer:** Check whether the interface is up, whether DHCP is expected, whether static configuration is expected, whether the cable/link is active, and whether the ticket/build sheet lists the correct network settings.

### 29. What does `nslookup` do?

**Answer:** It queries DNS and shows whether a name can be resolved to an IP address.

### 30. What does `resolvectl status` show on many Linux systems?

**Answer:** It shows DNS configuration and resolver status, including DNS servers associated with interfaces.

### 31. Why is DNS evidence useful in a ticket?

**Answer:** It can separate name-resolution failure from broader network failure and gives the next team specific evidence.

### 32. What should she avoid when troubleshooting DNS?

**Answer:** She should avoid changing production DNS settings without approval. She should collect evidence and escalate to the appropriate team.

## Cabling fiber and physical checks

### 33. What is an RJ45 connector?

**Answer:** It is the common connector used for copper Ethernet cables.

### 34. What is a patch panel?

**Answer:** A patch panel is a fixed termination point for cabling. It lets cables be organized and connected between racks, devices, and switches.

### 35. What is a transceiver or optic?

**Answer:** It is a module that plugs into a network port and sends/receives network signals, often over fiber.

### 36. What is the difference between single-mode and multi-mode fiber?

**Answer:** Single-mode is commonly used for longer distances and often has yellow jacket. Multi-mode is commonly used for shorter data center distances and often has aqua or orange jacket.

### 37. Why should she never look into fiber?

**Answer:** Fiber can carry light that may be invisible and dangerous to eyes. She should never look into fiber ends or optics.

### 38. Why are dust caps important?

**Answer:** Dust can block or degrade optical signals. Caps protect unused fiber ends and optics.

### 39. What should she do if a cable label is missing?

**Answer:** Stop before disconnecting. Document the missing label, trace using approved methods, and escalate for confirmation.

### 40. What does a cable tester prove?

**Answer:** It can prove basic copper wiring continuity and some faults. It does not prove VLAN, routing, firewall policy, or application health.

### 41. Why should cable paths be tidy?

**Answer:** Tidy cabling protects airflow, reduces accidental disconnects, makes troubleshooting easier, and improves safety.

### 42. What information should be verified before replacing a patch cable?

**Answer:** Ticket approval, asset, rack/U, source port, destination port, cable label, expected impact, maintenance window if needed, validation plan, and rollback or escalation path.

## Switching routing and VLANs

### 43. What does a switch do?

**Answer:** A switch connects devices on a local network and forwards Ethernet frames based on MAC addresses.

### 44. What does a router do?

**Answer:** A router connects different IP networks and forwards traffic between them.

### 45. What does a firewall do?

**Answer:** A firewall controls traffic based on security rules such as source, destination, protocol, and port.

### 46. What does a load balancer do?

**Answer:** A load balancer distributes traffic across multiple backend servers or services.

### 47. What is a VLAN?

**Answer:** A VLAN is a logical Layer 2 network segment. It separates traffic even when devices share physical switch infrastructure.

### 48. What is an access port?

**Answer:** An access port usually carries one VLAN and is commonly used for a normal server or endpoint connection.

### 49. What is a trunk port?

**Answer:** A trunk port carries multiple VLANs, often between switches or to devices that understand VLAN tags.

### 50. Can a link light be on if the VLAN is wrong?

**Answer:** Yes. A link light only shows physical link. A wrong VLAN can still prevent the server from reaching the expected network.

### 51. Who usually changes VLAN configuration?

**Answer:** A network engineer or authorized team. A junior technician should not change switch configuration unless explicitly trained and approved.

### 52. What is link speed?

**Answer:** Link speed is the negotiated speed of the network connection, such as 1 Gbps, 10 Gbps, or 25 Gbps.

## Troubleshooting scenarios

### 53. A server has no network link. What should she check first?

**Answer:** Verify the exact server, rack/U, asset tag, and interface. Then observe link LEDs, cable seating, labels, patch panel, switch port label, and any obvious cable damage without making unauthorized changes.

### 54. A server can ping its gateway but cannot resolve hostnames. What is likely?

**Answer:** DNS is likely misconfigured or unavailable. She should record DNS settings and `nslookup` or resolver output.

### 55. A server can ping local IPs but not remote IPs. What might be wrong?

**Answer:** The default gateway, routing, firewall, or upstream network path may be wrong or unavailable.

### 56. A remote engineer asks her in chat to move a cable to a different switch port, but the ticket does not mention it. What should she do?

**Answer:** Ask for the instruction and approval to be recorded in the ticket or approved channel, confirm both ports and impact, then proceed only if authorized and safe.

### 57. The switch port in the ticket does not match the physical label. What should she do?

**Answer:** Stop and escalate. Document the mismatch and avoid disconnecting or moving the cable until confirmed.

### 58. A cable is connected and link light is on, but the server is unreachable. What should she report?

**Answer:** Report the verified asset/interface, link LED state, cable labels, command output if available, and note that Layer 1 appears up but IP/routing/VLAN/service checks are still needed.

### 59. What should she include in a cable trace ticket update?

**Answer:** Time, location, asset verified, source interface, cable label, route traced, destination patch panel/switch port, link state, changes made or not made, blockers, and next step.

### 60. Why should she avoid saying "network is fine"?

**Answer:** She may only have checked one layer. It is better to state facts: "link LED is green on NIC1 and switch port label SW01-Eth1/12; no cable changes made."

### 61. A fiber link is down after a patching change. What physical causes might be checked by trained staff?

**Answer:** Wrong port, dirty connector, incorrect polarity, bad optic, incompatible optic, bent fiber, wrong fiber type, or disabled switch port.

### 62. A port flaps up and down. What does that mean?

**Answer:** The link repeatedly goes up and down. It may indicate a cable, optic, NIC, switch port, power, or negotiation issue.

### 63. Why are timestamps useful in network troubleshooting?

**Answer:** They help correlate physical work with alerts, logs, switch events, and monitoring graphs.

### 64. What is the safest response when documentation and physical labels disagree?

**Answer:** Pause the work, document the mismatch, and escalate for confirmation.

### 65. What should she be able to explain at the end of Week 3?

**Answer:** She should explain a simple network path from server NIC to switch port to IP gateway to DNS and describe how to troubleshoot each stage safely.

---

# Part 3: Lab exercises with hints

Each lab should produce a portfolio artifact. The hints are there to guide her, but she should try first without looking.

## Lab 1: Build a practical OSI model map

### Goal

Create a troubleshooting-focused OSI model reference.

### Steps

1. Create a table with the seven OSI layers.
2. Write a plain-English definition for each layer.
3. Add at least two data center examples per layer.
4. Add a symptom that could happen at each layer.
5. Add one command or observation that can collect evidence for layers 1-4.

### Hints

- Layer 1 can be link light, cable, optic, or port.
- Layer 2 can be MAC, ARP, VLAN, or switch port.
- Layer 3 can be IP, subnet, gateway, or route.
- Layer 7 can be DNS, HTTP, SSH, or application behavior.

### Expected portfolio output

`01-practical-osi-model-map.md` or `.drawio`

## Lab 2: Complete a subnetting worksheet

### Goal

Build confidence with common subnet sizes.

### Steps

For each network below, calculate the network address, first usable IP, last usable IP, broadcast address, and usable host count:

- `192.168.20.45/24`
- `192.168.20.130/25`
- `10.10.5.70/26`
- `10.10.5.96/27`
- `172.16.4.141/28`

### Hints

- Work out the block size first.
- For `/26`, blocks increase by 64.
- For `/27`, blocks increase by 32.
- For `/28`, blocks increase by 16.

### Expected portfolio output

`02-subnetting-worksheet.md`

## Lab 3: Discover and diagram a home network

### Goal

Identify basic network settings on a real computer and draw a simple diagram.

### Steps

1. On Windows, run `ipconfig /all`.
2. On Linux, run `ip addr` and `ip route`.
3. Record local IP, subnet, gateway, DNS servers, and interface name.
4. Identify the router or default gateway.
5. Draw a diagram: laptop/PC, Wi-Fi or Ethernet, router, ISP/internet, DNS.
6. Write a short note explaining what each part does.

### Hints

- Do not publish real public IPs, Wi-Fi passwords, or sensitive details.
- Replace private details with examples if the portfolio will be public.

### Expected portfolio output

`03-home-network-diagram.png` or `.drawio`

## Lab 4: Compare IP DNS DHCP and gateway failures

### Goal

Learn to distinguish common network failure types.

### Steps

Create a table with these columns:

- Failure type.
- Example symptom.
- Command evidence.
- Likely team to escalate to.
- Safe technician action.

Include:

- No link.
- No DHCP address.
- Wrong static IP.
- Wrong gateway.
- DNS failure.
- Firewall block.
- Service not listening.

### Hints

- `ping 8.8.8.8` and `nslookup` results can help separate IP from DNS.
- A firewall block may look like timeout even if routing exists.

### Expected portfolio output

`04-dns-dhcp-gateway-failure-notes.md`

## Lab 5: Collect Windows network evidence

### Goal

Practice collecting command output without changing settings.

### Steps

Run these commands on a Windows machine:

```cmd
ipconfig /all
ping 8.8.8.8
nslookup google.com
tracert google.com
arp -a
route print
```

For each command, write:

- What command was run.
- One useful line from the output.
- What the output proves.
- What the output does not prove.

### Hints

- Redact public IPs or personal network names if needed.
- Do not paste huge output blocks. Capture the useful evidence.

### Expected portfolio output

`05-windows-network-command-evidence.md`

## Lab 6: Collect Linux network evidence

### Goal

Practice Linux network observation commands.

### Steps

Run these commands in a Linux VM:

```bash
ip addr
ip link
ip route
ping -c 4 8.8.8.8
resolvectl status
ss -tulpn
```

If `traceroute` is installed, run:

```bash
traceroute google.com
```

For each command, write what it tells a technician.

### Hints

- `ip link` shows link/interface state.
- `ip route` shows the default route.
- `ss -tulpn` shows listening network sockets.

### Expected portfolio output

`06-linux-network-command-evidence.md`

## Lab 7: Observe ARP and MAC addresses

### Goal

See the relationship between IP addresses and MAC addresses.

### Steps

1. Record the computer's MAC address.
2. Ping the default gateway.
3. Run `arp -a` on Windows or `ip neigh` on Linux.
4. Find the gateway IP and MAC entry.
5. Write a short explanation of ARP in your own words.

### Hints

- If the ARP entry does not appear, ping the gateway first.
- Do not include real MAC addresses in a public portfolio; use redacted examples.

### Expected portfolio output

`07-mac-arp-notes.md`

## Lab 8: Create a rack-to-switch port map

### Goal

Practice documentation used in real data center work.

### Steps

Create a fictional port map for at least six servers. Include:

- Hostname.
- Rack.
- U position.
- Asset tag.
- Server interface.
- Cable label.
- Patch panel port.
- Switch name.
- Switch port.
- Network/VLAN name.
- Link speed.
- Notes.

### Hints

- Use realistic fake values.
- Keep label formats consistent.
- Include one row with a missing label note to practice documentation.

### Expected portfolio output

`08-rack-to-switch-port-map.md` or `.csv`

## Lab 9: Create a cable labeling standard

### Goal

Define a repeatable cable label format.

### Steps

1. Choose a label pattern.
2. Define each part of the label.
3. Give at least ten examples.
4. Include rules for source, destination, date, and owner if useful.
5. Include a rule for what to do when a label is damaged or missing.

### Example

```text
DUB1-R12-U18-NIC1__SW01-E1-12
```

### Hints

- Short labels are easier to fit on cables.
- Documentation can hold extra detail that does not fit physically on the cable.

### Expected portfolio output

`09-cable-labeling-standard.md`

## Lab 10: Build fiber handling notes

### Goal

Understand fiber safety and care at a junior level.

### Steps

Create notes covering:

- Single-mode versus multi-mode.
- LC connectors.
- Optics/transceivers.
- Dust caps.
- Bend radius.
- Cleaning basics.
- Why not to look into fiber.
- When to escalate.

### Hints

- Keep the notes practical.
- Do not turn this into vendor-specific optical engineering.

### Expected portfolio output

`10-fiber-handling-notes.md`

## Lab 11: Create a two-VLAN diagram or Packet Tracer lab

### Goal

Explain VLAN separation visually.

### Steps

1. Create two VLANs: VLAN 10 for `web` and VLAN 20 for `db`.
2. Place two hosts in each VLAN.
3. Show a switch connecting them.
4. Show that hosts in the same VLAN can communicate.
5. Show that hosts in different VLANs need routing.
6. Add labels for access ports and trunk ports if included.

### Hints

- If Packet Tracer is not available, draw the diagram in diagrams.net.
- Focus on concept, not perfect configuration.

### Expected portfolio output

`11-two-vlan-diagram.md` or `.pkt`

## Lab 12: Build a network troubleshooting flowchart

### Goal

Create a safe order of checks for network issues.

### Flowchart should include

- Verify ticket and asset.
- Check physical link.
- Check interface state.
- Check IP address.
- Check default gateway.
- Test ping by IP.
- Test DNS lookup.
- Check service port if appropriate.
- Document evidence.
- Escalate when configuration or authorization is needed.

### Hints

- Include "stop and escalate" paths for mismatched labels or unclear approval.
- Avoid steps that change production configuration.

### Expected portfolio output

`12-network-troubleshooting-flowchart.md`

## Lab 13: Write mock network ticket updates

### Goal

Practice professional network communication.

### Scenarios

Write updates for:

1. Server `app-dub-01` has no link on NIC1.
2. Cable trace requested from `db-dub-02` NIC2 to switch port.
3. DNS failure reported from a Linux VM.
4. Switch port label does not match the ticket.
5. Fiber patch replacement requested but no maintenance approval is present.

### For each scenario, include

- Acknowledgement.
- Verification details.
- Observations.
- Commands or physical checks completed.
- Action taken or reason for stopping.
- Next step or escalation question.

### Hints

- Use exact labels and timestamps.
- State "no cable changes made" where relevant.
- Do not claim a root cause unless the evidence supports it.

### Expected portfolio output

`13-mock-network-ticket-updates.md`

## Lab 14: Build a Week 3 mock interview script

### Goal

Prepare confident spoken answers.

### Steps

Write 45-90 second answers for:

1. What is the OSI model and how would you use it?
2. What is the difference between a switch and a router?
3. What is a VLAN?
4. What happens when you ping a hostname?
5. How would you troubleshoot a server with no network link?
6. How do you tell DNS failure from network failure?
7. What is the difference between single-mode and multi-mode fiber?
8. What would you do if cable labels do not match the ticket?
9. What network commands can you run on Windows?
10. What network commands can you run on Linux?

### Hints

- Mention safety and scope.
- Use portfolio evidence: port map, cable labeling standard, troubleshooting flowchart.
- Avoid pretending to configure enterprise switches if she has not done it.

### Expected portfolio output

`14-week-03-interview-script.md`

## Lab 15: Final Week 3 self-assessment

### Goal

Check readiness to move to Week 4.

### Self-assessment table

| Skill | Can do without notes | Can do with notes | Need more practice |
|---|---|---|---|
| Explain OSI layers practically | | | |
| Explain MAC addresses and ARP | | | |
| Explain IP address, subnet mask, and gateway | | | |
| Calculate `/24`, `/25`, `/26`, `/27`, `/28` | | | |
| Explain DNS and DHCP | | | |
| Use Windows network commands | | | |
| Use Linux network commands | | | |
| Explain copper and fiber cabling basics | | | |
| Explain switches, routers, firewalls, load balancers | | | |
| Explain VLANs and access/trunk ports | | | |
| Create a rack-to-switch port map | | | |
| Write network ticket updates | | | |
| Know when to stop and escalate | | | |

### Expected portfolio output

`15-week-03-self-assessment.md`

---

# Part 4: Templates to copy into the portfolio

## Rack-to-switch port map template

```markdown
| Hostname | Asset tag | Rack | U | Server interface | Cable label | Patch panel | Switch | Switch port | Network/VLAN | Speed | Notes |
|---|---|---|---:|---|---|---|---|---|---|---|---|
| app-dub-01 | DC-000201 | R12 | 18 | NIC1 | DUB1-R12-U18-NIC1__SW01-E1-12 | PP-A/24 | SW01 | Eth1/12 | prod-web | 10G | Example only |
```

## Cable trace checklist

```markdown
# Cable Trace Checklist

Ticket:
Technician:
Date/time:

## Before tracing

- [ ] Ticket and authorization confirmed.
- [ ] Correct site/room/rack confirmed.
- [ ] Hostname confirmed.
- [ ] Asset tag confirmed.
- [ ] Source interface confirmed.
- [ ] Instruction says whether disconnecting is allowed.

## Observations

- Source cable label:
- Source port:
- Patch panel label:
- Destination switch:
- Destination switch port:
- Link LED state:
- Cable condition:

## Safety

- [ ] No ambiguous cable disconnected.
- [ ] No switch configuration changed.
- [ ] Mismatch escalated if found.
- [ ] Evidence/photos attached if allowed.
```

## Network troubleshooting ticket template

```markdown
# Network Troubleshooting Ticket Update

Time:
Location:
Ticket:
Asset verified:
Interface checked:
Cable/port labels:
Link LED state:
OS interface state:
IP address:
Default gateway:
DNS servers:
Commands run:
Findings:
Changes made:
Blocker/risk:
Next step:
```

## Subnetting worksheet template

```markdown
| IP/prefix | Block size | Network address | First usable | Last usable | Broadcast | Usable hosts |
|---|---:|---|---|---|---|---:|
| | | | | | | |
```

## DNS and DHCP evidence template

```markdown
# DNS and DHCP Evidence

Device:
Interface:
Time:

## Addressing

- IP address:
- Prefix/subnet:
- Default gateway:
- DHCP or static:
- DNS servers:

## Tests

- Ping gateway:
- Ping public IP:
- DNS lookup:
- Traceroute/tracert:

## Interpretation

What works:
What fails:
Likely layer:
Escalation needed:
```

## Network escalation template

```markdown
# Network Escalation

Issue:
Impact/risk:
Asset and interface verified:
Physical checks completed:
Command evidence:
What I did not change:
Mismatch or blocker:
Decision/help needed:
Urgency:
```

---

# Part 5: Week 3 final exam

## Written exam

Answer these without looking at notes:

1. Explain the OSI model in practical troubleshooting terms.
2. Explain MAC addresses and ARP.
3. Explain IP address, subnet mask, and default gateway.
4. Calculate network, broadcast, and usable range for `192.168.50.77/26`.
5. Explain DNS and DHCP.
6. Explain the difference between a switch and a router.
7. Explain the difference between an access port and trunk port.
8. Explain why a link light does not prove the network is correctly configured.
9. List ten physical checks for a link-down issue.
10. Explain when to stop and escalate during cable work.
11. Compare copper and fiber cabling.
12. Explain single-mode versus multi-mode fiber.
13. Write a ticket update for a cable trace.
14. Write an escalation for a missing cable label.
15. Explain how to tell DNS failure from general network failure.

## Practical exam

Complete these tasks:

1. Build a subnetting table for `/24`, `/25`, `/26`, `/27`, and `/28`.
2. Draw a home network or lab network diagram.
3. Run Windows or Linux network commands and explain the useful evidence.
4. Create a six-row rack-to-switch port map.
5. Create a cable labeling standard with examples.
6. Draw a two-VLAN diagram.
7. Build a network troubleshooting flowchart.
8. Write three mock network ticket updates.
9. Explain a no-link troubleshooting process aloud.
10. Answer five random Week 3 questions aloud.

## Passing standard

She passes Week 3 if she can:

- Explain basic network concepts in plain English.
- Calculate common small IPv4 subnets.
- Collect useful network evidence on Windows and Linux.
- Create clean cable and port documentation.
- Explain link, IP, gateway, DNS, and VLAN failure differences.
- Write safe network ticket updates.
- Stop and escalate when physical labels, ticket details, or authorization do not match.

---

# Part 6: Interview positioning for Week 3

Week 3 gives her credibility around network-adjacent data center work. She should position herself as careful, evidence-driven, and aware of her boundaries.

## Strong interview themes

- I can troubleshoot in layers instead of guessing.
- I verify the asset, interface, cable, and port before touching anything.
- I can collect useful Windows and Linux network evidence.
- I understand the difference between physical link, IP connectivity, DNS, and application reachability.
- I can create clean port maps and cable labels.
- I know network configuration belongs to authorized network engineers.
- I stop and escalate when labels, ports, or instructions do not match.

## Example answer: server has no network link

"First I would verify the exact server, rack and U position, asset tag, and the interface named in the ticket. Then I would observe the link LEDs on the server NIC and, if accessible and authorized, the switch or patch panel side. I would check cable labels and seating without disconnecting anything unless the ticket allowed it. If the label or port did not match the ticket, I would stop and escalate. If Layer 1 looked correct, I would collect interface and IP evidence such as `ip link`, `ip addr`, or `ipconfig /all` and update the ticket with facts."

## Example answer: DNS works differently from IP connectivity

"DNS translates names to IP addresses. If I can ping an IP address like the gateway or a known external IP, but name lookup fails with `nslookup`, that suggests the network path may exist but DNS is failing or misconfigured. I would record the DNS server settings and the exact lookup result rather than just saying the network is down."

## Example answer: VLANs in plain English

"A VLAN is a logical network segment on a switch. It separates traffic so devices can be connected to the same physical switch but still behave like they are on separate networks. A server can have a link light but still be unable to reach the expected network if the switch port is in the wrong VLAN."

---

# Part 7: Week 3 completion checklist

- [ ] I created a Week 3 portfolio folder.
- [ ] I built a practical OSI model map.
- [ ] I can explain MAC addresses and ARP.
- [ ] I can explain IP address, subnet mask, and default gateway.
- [ ] I completed subnetting practice for `/24`, `/25`, `/26`, `/27`, and `/28`.
- [ ] I documented my home or lab network.
- [ ] I can explain DNS and DHCP.
- [ ] I collected Windows network command evidence.
- [ ] I collected Linux network command evidence.
- [ ] I can explain copper cable, patch panels, and RJ45.
- [ ] I can explain fiber, optics, LC connectors, and dust caps.
- [ ] I can explain switches, routers, firewalls, and load balancers.
- [ ] I can explain VLANs, access ports, and trunk ports.
- [ ] I created a rack-to-switch port map.
- [ ] I created a cable labeling standard.
- [ ] I built a network troubleshooting flowchart.
- [ ] I wrote mock network ticket updates.
- [ ] I built a Week 3 mock interview script.
- [ ] I completed the Week 3 final exam.
- [ ] I can explain when to stop and escalate during network work.
- [ ] My Week 3 portfolio folder is complete.
