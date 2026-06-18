# Certification-Style Study Plan: Data Center Engineer / Data Center Technician

## Target outcome

This plan prepares a complete beginner for entry-level roles such as:

- Data Center Technician
- Data Center Operations Technician
- Data Center Engineer, junior level
- Infrastructure Technician
- Hardware Operations Technician
- Network Operations / Hands-and-Eyes Support Technician

The plan is designed to reach **one grade above entry level**. By the end, she should not only be able to rack servers and follow tickets, but also explain why tasks are done, troubleshoot common incidents, document work professionally, understand basic networking and Linux, and communicate like a reliable operations engineer.

## Duration and workload

- **Length:** 8 weeks minimum
- **Time:** 2-4 hours per day, 5-6 days per week
- **Total effort:** about 120-180 hours
- **Style:** certification program with weekly labs, checkpoints, portfolio artifacts, and interview practice

If she has more time, stretch the plan to 10-12 weeks and repeat labs until she can perform them without notes.

## Role reality in Dublin / Ireland

Data center roles in Dublin can be competitive because Ireland has a large cloud and colocation market. Employers may expect more than the title suggests. A strong candidate should show:

- Safety mindset and attention to detail.
- Comfort with shifts, procedures, documentation, and ticketing.
- Basic server hardware knowledge.
- Basic networking knowledge: IP, VLAN, switch ports, fiber, copper, DNS, DHCP.
- Ability to use Linux command line for basic checks.
- Ability to troubleshoot systematically and escalate clearly.
- Understanding of data center standards: power, cooling, cabling, asset management, access control.
- Professional communication with remote engineers and customers.

## What “one grade above entry level” means

An entry-level technician can follow instructions. A junior-plus candidate can:

- Read a ticket and identify missing information.
- Ask precise clarification questions.
- Predict risk before touching equipment.
- Explain server boot, RAID, NICs, firmware, iDRAC/iLO, PXE, and console access.
- Trace a connectivity issue from server NIC to switch port to IP configuration.
- Write a clean handover note.
- Produce evidence: photos, labels, diagrams, logs, and timeline.
- Understand how data center work affects production systems.

## Recommended optional certifications

Certifications are not mandatory, but they help a newbie prove commitment.

Priority order:

1. **CompTIA A+** - hardware, troubleshooting, operating systems.
2. **CompTIA Network+** - networking fundamentals.
3. **ITIL Foundation** - ticketing, incidents, changes, service management.
4. Optional: **Linux Essentials** or **LPIC-1 basics**.

For a focused 8-week plan, she can study the knowledge areas without immediately paying for exams.

## Tools and low-cost lab setup

She does not need a real data center. Use:

- A Windows laptop or desktop.
- VirtualBox or VMware Workstation Player.
- Ubuntu Server virtual machine.
- Draw.io / diagrams.net for rack and network diagrams.
- Packet Tracer, GNS3, or simple home-router exercises for networking.
- Old PC parts if available: RAM, SSD/HDD, Ethernet cables.
- A cheap RJ45 cable tester if possible.
- Label maker or printable labels if possible.
- GitHub or OneDrive/Google Drive for portfolio evidence.

## Portfolio deliverables

By the end, create:

1. Data center vocabulary cheat sheet.
2. Server hardware diagram.
3. Rack layout diagram with power and network connections.
4. Cable labeling standard.
5. Linux troubleshooting command sheet.
6. Network troubleshooting flowchart.
7. Mock ticket examples with resolution notes.
8. Incident report and handover example.
9. Final capstone: “Deploy and document a mini data center lab.”

---

# Week 1: IT foundations, safety, and professional operations

## Goal

Build the mindset of a careful operations technician: safety, procedures, documentation, and basic IT vocabulary.

## Detailed Week 1 workbook

Use the dedicated workbook for a deeper day-by-day module with expanded topics, interview questions with model answers, and lab exercises with hints:

- [Week 1 Detailed Workbook: IT Foundations, Safety, and Professional Operations](./WEEK_01_FOUNDATIONS_OPERATIONS.md)

## Suggested study order

1. **Day 1: Data center basics**
   - Learn what data centers do, the main building blocks, types of facilities, and common areas.
   - Produce a concept map and glossary.

2. **Day 2: Roles and operational culture**
   - Learn technician, engineer, NOC, remote-hands, facilities, security, and customer responsibilities.
   - Produce a responsibility matrix and stop/escalate rules.

3. **Day 3: Safety and access control**
   - Learn ESD, lifting, electrical awareness, hot/cold aisles, physical security, badges, visitor rules, and escorting.
   - Produce a safety checklist and access-control scenario answers.

4. **Day 4: Ticketing, documentation, and change management**
   - Learn ticket lifecycle, ticket updates, change risk, rollback, validation, photos, labels, diagrams, and asset records.
   - Produce ticket examples, a change request template, and a handover note.

5. **Day 5: Communication and review**
   - Learn concise updates, escalation, incident mindset, and interview explanations.
   - Produce escalation examples, mock interview answers, and the final Week 1 portfolio.

## Topics

- What data centers do: compute, storage, network, power, cooling.
- Types of data centers: hyperscale, colocation, enterprise, edge.
- Roles: technician, engineer, NOC, remote hands, facilities, security.
- Safety: ESD, lifting, ladders, sharp rails, hot/cold aisles, electrical awareness.
- Access control: badges, visitor logs, cages, mantraps, CCTV, escorting.
- Ticket lifecycle: open, acknowledge, investigate, update, resolve, close.
- Change management: risk, approval, rollback, maintenance windows.
- Professional communication: concise updates, timelines, escalation.
- Documentation discipline: photos, labels, diagrams, asset records.

## Hands-on labs

1. **Create an operations notebook**
   - Sections: safety, hardware, networking, Linux, tickets, interview stories.
   - Add a glossary of 50 terms.

2. **Write three mock ticket updates**
   - Example: “Replace failed disk in server rack A12.”
   - Include acknowledgement, action plan, progress update, closure note.

3. **Create a change request template**
   - Include purpose, affected systems, risk, rollback, validation, communication plan.

4. **Create a safety checklist**
   - Before, during, and after physical work.

## Interview practice

Prepare answers for:

- What is a data center?
- Why is documentation important?
- What would you do if a ticket instruction seems wrong?
- How do you handle a task you have never done before?
- How do you communicate delays?

## Checkpoint

She should be able to explain:

- The difference between incident, request, and change.
- Why technicians must not improvise on production equipment.
- How to write a clear ticket update.

## Portfolio artifact

Publish: `week-01-operations-basics.md` with glossary, safety checklist, and ticket examples.

---

# Week 2: Computer hardware and server fundamentals

## Goal

Understand the components inside servers and how to troubleshoot common hardware issues.

## Detailed Week 2 workbook

Use the dedicated workbook for a deeper day-by-day module with expanded topics, interview questions with model answers, and lab exercises with hints:

- [Week 2 Detailed Workbook: Computer Hardware and Server Fundamentals](./WEEK_02_SERVER_HARDWARE.md)

## Suggested study order

1. **Day 1: Server anatomy and layout**
   - Learn server vs desktop hardware and rack server front, back, and internal layout.
   - Produce a front/back server diagram and component glossary.

2. **Day 2: Core components**
   - Learn CPU, RAM, motherboard, PCIe, PSU, and NIC fundamentals.
   - Produce hardware comparison notes and an inspection checklist.

3. **Day 3: Storage and RAID**
   - Learn HDD, SATA SSD, SAS SSD, NVMe, RAID, HBA, and hot-swappable component concepts.
   - Produce storage notes, a RAID worksheet, and disk-failure simulation notes.

4. **Day 4: Firmware, boot, and remote management**
   - Learn BIOS/UEFI, firmware, boot order, BMC, iDRAC, iLO, IPMI, PXE, and imaging basics.
   - Produce a boot-flow diagram, VirtualBox boot lab notes, and remote-management notes.

5. **Day 5: Troubleshooting and inventory**
   - Learn common hardware symptoms, Linux inspection commands, evidence collection, ticket updates, and escalation.
   - Produce troubleshooting flowcharts, an asset inventory, mock hardware tickets, and the Week 2 interview script.

## Topics

- Server vs desktop hardware.
- CPU, RAM, motherboard, PSU, disks, NICs, RAID controller, HBA.
- Disk types: HDD, SATA SSD, SAS SSD, NVMe.
- RAID levels: RAID 0, 1, 5, 6, 10; redundancy vs backup.
- Hot-swappable components.
- Firmware, BIOS/UEFI, boot order.
- BMC, iDRAC, iLO, IPMI, remote console.
- PXE boot and imaging basics.
- Asset tags, serial numbers, service tags.
- Common hardware symptoms: no power, no boot, failed disk, failed fan, memory error.

## Hands-on labs

1. **Build a server component diagram**
   - Draw front and back of a typical rack server.
   - Label power, network, console, disk bays, fans, RAM slots.

2. **Virtual BIOS/boot practice**
   - Create a VM in VirtualBox.
   - Change boot order.
   - Attach/detach virtual disk and ISO.
   - Observe boot errors.

3. **Disk failure simulation**
   - Create a Linux VM with two virtual disks.
   - Practice listing disks with `lsblk`.
   - Detach one disk and document symptoms.

4. **Asset inventory practice**
   - Create a spreadsheet with hostname, asset tag, rack position, serial, NIC MAC, power feed, switch port.

## Commands to learn

```bash
lscpu
free -h
lsblk
df -h
ip link
dmesg | tail
sudo dmidecode
sudo smartctl -a /dev/sda
```

## Interview practice

- What is RAID and why is it not a backup?
- What is hot-swapping?
- What is the difference between iDRAC/iLO and SSH?
- A server has no network after disk replacement. What do you check?
- What information do you record before replacing hardware?

## Checkpoint

She should be able to explain a server from power-on to operating-system boot.

## Portfolio artifact

Publish: server hardware diagram and asset inventory example.

---

# Week 3: Networking fundamentals for data centers

## Goal

Gain practical network understanding sufficient to follow cabling tickets, verify connectivity, and escalate intelligently.

## Topics

- OSI model in practical terms.
- Ethernet, MAC address, ARP.
- IP addressing, subnet mask, gateway.
- DNS and DHCP.
- Copper cabling: Cat5e, Cat6, RJ45, patch panels.
- Fiber basics: single-mode, multi-mode, LC connectors, transceivers, optics.
- Switches, routers, firewalls, load balancers.
- VLANs and trunk/access ports.
- Link speed and duplex.
- Link lights and physical layer troubleshooting.
- Network diagrams and port mapping.

## Hands-on labs

1. **Subnetting practice**
   - Learn `/24`, `/25`, `/26`, `/27`, `/28`.
   - Calculate usable IPs, network address, broadcast address.

2. **Home network discovery**
   - Identify local IP, gateway, DNS.
   - Draw home network diagram.

3. **Linux network checks**
   - Use ping, traceroute/tracert, nslookup, dig if available.
   - Compare DNS failure vs network failure.

4. **Cable and port documentation exercise**
   - Create a mock rack-to-switch port map.
   - Include labels like `R12-U18-NIC1 -> SW01-Eth1/12`.

5. **Packet Tracer or diagram lab**
   - Create two VLANs and explain why hosts in different VLANs need routing.

## Commands to learn

Windows:

```cmd
ipconfig /all
ping 8.8.8.8
nslookup google.com
tracert google.com
arp -a
```

Linux:

```bash
ip addr
ip route
ping -c 4 8.8.8.8
resolvectl status
ss -tulpn
traceroute google.com
```

## Interview practice

- What is the difference between a switch and a router?
- What happens when you ping a hostname?
- What is a VLAN?
- How would you troubleshoot a server with no network link?
- What is the difference between single-mode and multi-mode fiber?

## Checkpoint

She should be able to troubleshoot from cable to DNS in a simple scenario.

## Portfolio artifact

Publish: network troubleshooting flowchart and rack port map.

---

# Week 4: Linux basics and remote troubleshooting

## Goal

Become comfortable with command-line work commonly requested by remote engineers.

## Topics

- Linux filesystem layout.
- Users, groups, permissions.
- Services and systemd.
- Logs: `/var/log`, journalctl.
- Processes, CPU, memory, disk.
- SSH basics.
- Text editing with nano or vim basics.
- File transfer: scp/sftp conceptually.
- Safe command execution and not making unauthorized changes.

## Hands-on labs

1. **Install Ubuntu Server VM**
   - Configure hostname.
   - Create non-root user.
   - Enable SSH if possible.

2. **Command-line navigation**
   - Practice creating files, directories, permissions.

3. **Service troubleshooting**
   - Install nginx.
   - Start, stop, restart it.
   - Break it intentionally by changing port or config, then inspect logs.

4. **Resource check runbook**
   - Create a checklist for CPU, memory, disk, network, service status.

5. **Remote hands simulation**
   - One person writes instructions; she performs exactly and documents results.

## Commands to learn

```bash
pwd
ls -lah
cd
cat
less
grep
find
touch
mkdir
cp
mv
rm
chmod
chown
sudo
systemctl status nginx
journalctl -u nginx --no-pager
ps aux
top
df -h
du -sh *
free -h
uptime
whoami
hostname
```

## Interview practice

- How do you check whether a Linux service is running?
- How do you check disk space?
- What is sudo?
- What would you do before running a command from a remote engineer?
- How do you collect evidence without changing the system?

## Checkpoint

She should be able to log into a Linux VM, check service health, inspect logs, and report findings.

## Portfolio artifact

Publish: Linux troubleshooting runbook with screenshots.

---

# Week 5: Data center operations: rack, stack, cable, power, cooling

## Goal

Understand physical data center work well enough to sound credible and safe in interviews.

## Topics

- Rack units, rails, rack elevations.
- Rack planning: weight, airflow, cable management.
- Hot aisle / cold aisle.
- Power: PDU, PSU, A/B power feeds, redundancy, C13/C14, C19/C20.
- UPS and generator concepts.
- Cooling concepts: CRAC/CRAH, temperature, humidity, blanking panels.
- Cabling standards and neatness.
- Labeling standards.
- Optics and transceivers handling.
- Spares management.
- Decommissioning and secure disposal basics.

## Hands-on labs

1. **Rack elevation diagram**
   - Create a 42U rack diagram.
   - Place servers, switches, PDUs, patch panels.
   - Explain why items are placed where they are.

2. **Power redundancy plan**
   - Draw A-feed and B-feed power for dual-PSU servers.
   - Explain what happens if one feed fails.

3. **Cable labeling standard**
   - Define label format, examples, source/destination, date, owner.

4. **Maintenance window plan**
   - Prepare a change for replacing a failed network cable.
   - Include rollback and validation.

5. **Decommission checklist**
   - Include approval, data wipe confirmation, asset update, physical removal, disposal.

## Interview practice

- What is a rack unit?
- What is A/B power?
- Why is airflow management important?
- How do you avoid disconnecting the wrong cable?
- What steps do you follow before decommissioning equipment?

## Checkpoint

She should be able to walk through a rack-and-stack task from ticket to closure.

## Portfolio artifact

Publish: full rack elevation, cabling standard, and power diagram.

---

# Week 6: Troubleshooting, incidents, and escalation

## Goal

Develop structured troubleshooting and incident communication skills.

## Topics

- Troubleshooting methodology: define, isolate, test, fix, validate, document.
- Severity and priority.
- Escalation paths.
- Incident timelines.
- Evidence collection: logs, photos, LED states, commands, timestamps.
- Common incidents:
  - Server down.
  - Failed disk.
  - Link down.
  - High temperature alert.
  - Power supply failed.
  - Wrong cabling.
  - Access issue.
- Root cause vs immediate fix.
- Post-incident review basics.

## Hands-on labs

1. **Incident simulation: server unreachable**
   - Use VM or home network.
   - Create possible causes: powered off, wrong IP, service stopped, DNS issue.
   - Document checks in order.

2. **Incident timeline**
   - Write a timeline with timestamps every 10-15 minutes.
   - Include customer/stakeholder updates.

3. **Escalation note**
   - Write an escalation that includes facts, impact, checks completed, and requested help.

4. **Post-incident review**
   - Write a blameless review: what happened, impact, detection, resolution, prevention.

## Interview practice

- A server is unreachable. What do you check first?
- How do you decide when to escalate?
- What information do you include in an incident update?
- Tell me about a time you made a mistake or had to learn quickly.
- How do you work under pressure?

## Checkpoint

She should be able to show calm, logical troubleshooting in a mock incident.

## Portfolio artifact

Publish: incident report, escalation note, and post-incident review.

---

# Week 7: Cloud/data center bridge and junior engineer skills

## Goal

Go beyond technician tasks by understanding how data centers support cloud and production services.

## Topics

- Virtualization: hypervisors, VMs, hosts, clusters.
- Storage concepts: SAN, NAS, object storage, block storage.
- Backup and disaster recovery basics.
- High availability and redundancy.
- Monitoring: alerts, dashboards, thresholds.
- Configuration management concept.
- Basic cloud concepts: regions, availability zones, instances, security groups.
- Security basics: least privilege, MFA, access logs, physical security.
- Compliance basics: audit trails, chain of custody, GDPR awareness.

## Hands-on labs

1. **Virtualization lab**
   - Run two Ubuntu VMs.
   - Explain host vs guest.
   - Document resource allocation.

2. **Monitoring lab**
   - Use simple commands or Netdata/Glances if comfortable.
   - Create screenshots of CPU, memory, disk, network.

3. **Cloud concept map**
   - Draw how cloud instances still depend on physical servers, networking, power, and cooling.

4. **Security checklist**
   - Create checklist for escorted access, no tailgating, no photos without permission, secure disposal.

## Interview practice

- What is virtualization?
- What is high availability?
- What is the difference between backup and redundancy?
- How does physical data center work affect cloud customers?
- What security rules must a data center technician follow?

## Checkpoint

She should be able to connect physical work to business impact and cloud reliability.

## Portfolio artifact

Publish: cloud-to-hardware architecture diagram and monitoring notes.

---

# Week 8: Capstone, CV, LinkedIn, and interview readiness

## Goal

Turn knowledge into a hiring package and practice interview performance.

## Capstone project: Mini data center operations lab

Create a complete documentation pack for a fictional rack with:

- Rack elevation.
- Server inventory.
- Power A/B diagram.
- Network port map.
- Cable labeling standard.
- Linux health-check runbook.
- Incident response runbook.
- Example tickets:
  - Rack new server.
  - Replace failed disk.
  - Troubleshoot link down.
  - Decommission old server.
- Final presentation: 8-10 minutes explaining the environment and how she would operate it.

## CV focus

Even without paid experience, she can list a “Hands-on Infrastructure Lab Portfolio” section:

```text
Hands-on Infrastructure Lab Portfolio
- Built and documented a mini data center operations lab including rack elevation, asset inventory, A/B power design, network port map, and Linux health-check runbook.
- Practiced Linux troubleshooting for services, disk usage, logs, network configuration, and system health.
- Created incident reports and escalation notes for simulated server unreachable, failed disk, and link-down scenarios.
- Developed cable labeling and change-management templates aligned with data center operational best practices.
```

## LinkedIn headline examples

- Aspiring Data Center Technician | Linux, Networking, Hardware, Rack & Stack Labs
- Entry-Level Data Center Operations Candidate | CompTIA A+/Network+ Study | Dublin

## Mock interview set

She must practice aloud until answers sound natural:

1. Tell me about yourself.
2. Why data center operations?
3. What is your hands-on experience?
4. What is a rack unit?
5. Explain A/B power redundancy.
6. What is RAID?
7. What is DNS?
8. What is DHCP?
9. What is a VLAN?
10. How do you troubleshoot a server with no network?
11. How do you check disk space in Linux?
12. How do you check logs in Linux?
13. What would you do if you accidentally unplugged the wrong cable?
14. What if a remote engineer asks you to do something unsafe?
15. How do you document completed work?
16. How do you handle shift work or urgent incidents?
17. How do you avoid mistakes during repetitive tasks?
18. What is your biggest weakness and how are you improving it?
19. Describe a time you learned something difficult.
20. Why should we hire you over another junior candidate?

## Final readiness checklist

- [ ] Can explain data center basics clearly.
- [ ] Can identify major server components.
- [ ] Can explain basic networking and troubleshoot link/IP/DNS issues.
- [ ] Can use Linux commands for health checks.
- [ ] Can write professional ticket updates.
- [ ] Can explain rack, power, cooling, and cabling concepts.
- [ ] Has a complete capstone portfolio.
- [ ] Has a role-targeted CV.
- [ ] Has practiced at least three mock interviews.
- [ ] Can answer “why this role?” with confidence.

## Extra work to stand out

If she has additional time, add:

- CompTIA A+ practice exams.
- Network+ subnetting drills.
- Basic Python script to parse an inventory CSV.
- Basic PowerShell commands for Windows troubleshooting.
- Visit public cloud/data center webinars or local tech meetups in Dublin.
- Apply to internships, apprenticeships, NOC, hardware support, and IT support roles as adjacent paths.
