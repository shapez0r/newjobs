# Week 2 Detailed Workbook: Computer Hardware and Server Fundamentals

## Purpose of this workbook

This workbook expands **Week 2** of the Data Center Engineer / Data Center Technician study plan. It is written for a complete beginner and is designed to turn general computer knowledge into practical server-hardware confidence.

By the end of this week, she should be able to look at a server task and understand what the hardware is, why it matters, what information must be verified before touching it, and how to document hardware work professionally.

The focus is not advanced system administration. The focus is operational competence: identify components, understand boot flow, explain storage and RAID, use basic Linux commands to observe hardware, and troubleshoot common physical symptoms in a safe, methodical way.

## Week 2 target level

The target is not "I know what RAM is." The target is:

- She can explain the difference between desktop hardware and server hardware.
- She can identify the main internal and external parts of a rack server.
- She can explain CPU, RAM, motherboard, PCIe, PSU, disk, NIC, RAID controller, HBA, and BMC in plain English.
- She can compare HDD, SATA SSD, SAS SSD, and NVMe storage.
- She can explain RAID 0, 1, 5, 6, and 10, including the difference between redundancy and backup.
- She understands hot-swappable parts and why "hot-swap" does not mean "replace casually."
- She can describe BIOS/UEFI, firmware, boot order, PXE boot, and basic imaging.
- She can explain what iDRAC, iLO, IPMI, and remote console access are used for.
- She can collect asset information before hardware work: hostname, serial, asset tag, rack, U position, MAC address, power feed, and switch port.
- She can use basic Linux commands to inspect CPU, memory, disks, filesystems, network interfaces, kernel messages, DMI data, and disk health.
- She can produce a Week 2 portfolio with diagrams, command notes, mock tickets, and hardware troubleshooting flowcharts.

## Suggested weekly schedule

| Day | Focus | Main output |
|---|---|---|
| Day 1 | Server anatomy and rack server layout | Front/back server diagram and component glossary |
| Day 2 | CPU, RAM, motherboard, PCIe, PSU, NICs | Hardware comparison notes and inspection checklist |
| Day 3 | Storage, RAID, HBA, and disk failure concepts | RAID worksheet and disk-type comparison table |
| Day 4 | Firmware, boot order, BMC, remote console, PXE | Boot-flow diagram and remote-management notes |
| Day 5 | Hardware troubleshooting and asset inventory | Troubleshooting flowcharts, inventory example, mock tickets |
| Day 6 optional | Practical revision in VirtualBox/Linux | Screenshots, command outputs, and self-assessment |
| Day 7 optional | Rest or catch-up | Improve weak areas and clean portfolio |

## Required Week 2 portfolio artifacts

Create a folder called `week-02-server-hardware` and include:

```text
week-02-server-hardware/
  README.md
  01-server-front-back-diagram.png or .drawio
  02-server-component-glossary.md
  03-desktop-vs-server-comparison.md
  04-storage-and-raid-notes.md
  05-raid-level-comparison-table.md
  06-boot-flow-diagram.md
  07-bmc-idrac-ilo-ipmi-notes.md
  08-virtualbox-boot-lab.md
  09-disk-failure-simulation.md
  10-asset-inventory-example.csv or .xlsx
  11-hardware-troubleshooting-flowcharts.md
  12-mock-hardware-ticket-updates.md
  13-week-02-self-assessment.md
```

---

# Part 1: Comprehensive Week 2 topics

## 1. Server hardware versus desktop hardware

A desktop computer is designed for one user. A server is designed to provide services to many users, systems, or applications, often continuously.

Server hardware is built for reliability, serviceability, remote management, monitoring, and redundancy. A data center technician does not need to design servers from scratch, but she must understand why server hardware is different and why physical actions can affect production services.

### Key differences

- Servers are usually mounted in racks.
- Servers often have redundant power supplies.
- Servers may use ECC memory to detect and correct memory errors.
- Servers often have multiple network interfaces.
- Servers may have hardware RAID controllers or HBAs.
- Servers often support hot-swappable disks, fans, and power supplies.
- Servers include out-of-band management such as iDRAC, iLO, or IPMI.
- Servers use firmware and remote console tools for troubleshooting before the operating system loads.
- Servers are tracked by asset tag, serial number, service tag, rack, U position, power feed, and network port.

### Operational mindset

Server hardware belongs to a service. Replacing the wrong disk, pulling the wrong cable, or powering off the wrong host can cause an outage. A technician must verify the physical target before making any change.

Before touching a server, she should confirm:

- Ticket number.
- Approved task.
- Hostname.
- Asset tag.
- Serial or service tag.
- Rack and U position.
- Customer or owner.
- Maintenance window or approval.
- Expected impact.
- Rollback or escalation plan.

## 2. Rack server anatomy

A rack server is usually measured in rack units, often written as `U`. One rack unit is 1.75 inches high. Common server sizes are 1U, 2U, and 4U.

### Front of a server

The front of a typical rack server may include:

- Drive bays.
- Drive status LEDs.
- Power button.
- System health LED.
- USB port.
- VGA or console port.
- Service tag or pull-out information tab.
- Bezel or front cover.

### Back of a server

The back of a typical rack server may include:

- Power supply units.
- Network ports.
- Dedicated management port.
- USB ports.
- VGA port.
- Serial port.
- PCIe expansion slots.
- Storage or network adapter ports.
- Identification LED.

### Inside a server

Inside a typical server:

- CPU sockets.
- RAM slots.
- Motherboard.
- Fans.
- Air baffles.
- Heat sinks.
- PCIe risers.
- RAID controller or HBA.
- Backplane.
- Power distribution components.
- Internal cables.

### Why layout matters

Data center work is often remote-hands work. A remote engineer may ask for information like "check the amber LED on disk bay 3" or "move the cable from NIC 2 to the port labeled OCP 1." She needs enough physical vocabulary to avoid confusion.

## 3. CPU fundamentals

The CPU is the processor. It executes instructions and performs calculations for the operating system and applications.

In data center roles, she does not need to know processor design deeply, but she must understand the practical terms that appear in tickets, inventories, BIOS screens, and monitoring alerts.

### Terms to know

- Socket: the physical place where a CPU is installed.
- Core: an execution unit inside a CPU.
- Thread: a schedulable execution path, often enabled by simultaneous multithreading.
- Clock speed: how fast a CPU cycle runs, usually measured in GHz.
- Cache: fast memory inside or near the CPU.
- Heat sink: metal cooling block attached to the CPU.
- Thermal paste: material that helps transfer heat from CPU to heat sink.
- TDP: thermal design power, a rough indicator of heat output and cooling requirements.

### Common CPU-related symptoms

- Server powers on but fails POST.
- System health LED shows CPU error.
- Fans run at high speed due to temperature sensor issues.
- Server reports a CPU thermal event.
- Server will not boot after maintenance if CPU or heat sink was disturbed.

### Technician responsibility

A junior technician normally should not reseat or replace CPUs unless trained, authorized, and following a vendor procedure. CPU work is delicate and can damage sockets or pins. The stronger junior response is to identify, document, and escalate correctly.

## 4. RAM and ECC memory

RAM is temporary working memory used by the operating system and applications. Servers often use ECC memory, which can detect and correct certain memory errors.

### Terms to know

- DIMM: a memory module.
- Slot: the motherboard connector where a DIMM is installed.
- Capacity: amount of memory, such as 16 GB or 64 GB.
- Speed: memory speed, such as 2666 MT/s or 3200 MT/s.
- ECC: error-correcting code memory.
- Memory channel: path between CPU and RAM.
- Population rules: vendor rules for which slots to fill first.

### Why memory population rules matter

Servers may require DIMMs to be installed in specific slots depending on CPU count and memory layout. Incorrect placement can cause performance loss, warning messages, or boot failure.

### Common RAM-related symptoms

- Server fails POST.
- Error LED near a DIMM slot.
- BIOS reports memory training failure.
- Operating system reports less memory than expected.
- Kernel logs show memory errors.
- Server crashes or reboots unexpectedly.

### Technician responsibility

Before replacing or reseating memory:

- Confirm the exact server.
- Confirm the affected slot.
- Confirm part number and compatibility.
- Power down if required by procedure.
- Use ESD precautions.
- Follow vendor memory population rules.
- Document before and after status.

## 5. Motherboard, chipset, and PCIe

The motherboard is the main circuit board connecting CPU, RAM, storage, network, power, and expansion cards.

### Important motherboard areas

- CPU sockets.
- DIMM slots.
- PCIe slots.
- Power connectors.
- Fan connectors.
- Storage controller connections.
- Management controller.
- System battery.
- Backplane connections.
- Diagnostic LEDs.

### PCIe

PCIe is a high-speed expansion bus used for network cards, storage controllers, GPUs, accelerators, and other adapters.

Terms to know:

- Slot: physical PCIe connector.
- Lane: data path. Examples: x4, x8, x16.
- Riser: board that positions PCIe cards in a rack server.
- NIC: network interface card.
- HBA: host bus adapter.
- RAID controller: adapter that manages RAID.

### Common PCIe-related symptoms

- Network ports missing after reboot.
- Storage controller not detected.
- Server reports PCIe training error.
- Adapter LED is off.
- Firmware inventory shows missing device.

### Technician responsibility

PCIe work usually requires powering down the server unless vendor documentation explicitly supports a different process. The technician must document slot location, part number, cable positions, and firmware status where possible.

## 6. Power supplies and power path

Servers often have redundant power supply units, usually called PSUs. A server with two PSUs can often keep running if one PSU or one power feed fails.

### Terms to know

- PSU: power supply unit.
- Redundant power: more than one power source or supply.
- A/B feed: two separate power paths.
- PDU: power distribution unit in the rack.
- C13/C14: common IEC power connectors.
- Power cord retention clip: helps prevent accidental unplugging.
- Load: amount of power being used.

### What redundancy means

Redundancy reduces risk, but it does not remove risk. If a server has two PSUs but both are plugged into the same PDU, it may not be protected from a PDU failure. Good documentation records which PSU connects to which feed.

### Common power symptoms

- Server has no power.
- One PSU LED is amber.
- One PSU is missing from management inventory.
- Server runs but reports redundancy lost.
- Power cable is loose.
- PDU breaker tripped.
- Remote management is reachable but host is off.

### Technician responsibility

Before touching power:

- Confirm server identity.
- Confirm which PSU and cable are in scope.
- Check LEDs without unplugging anything.
- Check both ends of the power cable.
- Confirm PDU outlet label.
- Record current power state.
- Escalate if the ticket could affect a live production host.

## 7. Storage devices

Servers use disks or drives for operating systems, application data, logs, cache, and local storage. Storage may be local or connected to external storage systems.

### HDD

An HDD is a spinning magnetic disk. It is often cheaper per terabyte but slower and mechanically fragile compared with SSDs.

### SATA SSD

A SATA SSD uses flash memory but connects through the SATA interface. It is faster than HDD for many workloads but limited by SATA performance.

### SAS SSD

A SAS SSD is enterprise-focused storage using the SAS interface. SAS is common in servers and storage arrays because it supports enterprise features and dual-port designs in some environments.

### NVMe

NVMe storage uses PCIe for high performance and low latency. NVMe drives may be installed in front bays, internal slots, or PCIe adapters depending on server design.

### Storage terms

- Drive bay: physical slot where a disk is inserted.
- Backplane: board connecting front drives to storage controllers.
- Caddy/tray: carrier that holds the drive.
- Hot spare: unused disk reserved for RAID rebuild.
- Logical drive / virtual disk: storage volume presented by a RAID controller.
- Physical disk: actual drive hardware.
- SMART: drive health monitoring data.

## 8. RAID and HBA fundamentals

RAID means redundant array of independent disks. RAID combines multiple disks for performance, redundancy, or both.

RAID is not a backup. RAID can protect against some disk failures, but it does not protect against deletion, corruption, ransomware, wrong commands, site loss, or application-level mistakes.

### RAID 0

RAID 0 stripes data across disks for performance and capacity. It has no redundancy. If one disk fails, the data is usually lost.

Use case: temporary high-performance scratch space where data loss is acceptable.

### RAID 1

RAID 1 mirrors data across two disks. If one disk fails, the other can continue serving data.

Use case: operating system disk pair or simple redundancy.

### RAID 5

RAID 5 stripes data and parity across at least three disks. It can usually survive one disk failure.

Use case: capacity-efficient redundancy, less common for write-heavy workloads.

### RAID 6

RAID 6 uses double parity across at least four disks. It can usually survive two disk failures.

Use case: larger arrays where rebuild time and second-disk failure risk matter.

### RAID 10

RAID 10 combines mirroring and striping. It needs at least four disks and can offer good performance and redundancy.

Use case: performance-sensitive databases and virtual machine storage.

### RAID controller versus HBA

A RAID controller manages RAID arrays and presents logical drives to the operating system. An HBA presents disks more directly to the operating system or storage software.

Some modern systems use software-defined storage and prefer HBAs instead of hardware RAID. A technician should follow the design and ticket instructions, not assume one is better.

## 9. Network interfaces and MAC addresses

A NIC is a network interface card. Servers may have onboard NICs, PCIe NICs, OCP adapters, dedicated management ports, and storage-network adapters.

### Terms to know

- NIC: network interface card.
- Port: physical network connection.
- Link light: LED showing physical connectivity.
- Activity light: LED showing traffic.
- MAC address: hardware address assigned to a network interface.
- Management port: dedicated port for BMC access.
- OCP NIC: common server form factor for network adapters.
- SFP/SFP+/SFP28: optical or copper transceiver modules.

### Common NIC symptoms

- No link light.
- Wrong port patched.
- Cable in management port instead of production port.
- MAC address does not match asset record.
- Interface is down in the operating system.
- Link speed is lower than expected.
- Network adapter missing after firmware or hardware work.

### Technician responsibility

She should be able to identify the difference between production network ports and management ports. A common mistake is connecting the wrong cable to the wrong port after hardware replacement.

## 10. Hot-swappable components

Hot-swappable means a component can be replaced while the system is powered on, if the server design and procedure support it.

Common hot-swappable parts:

- Disks.
- Power supplies.
- Some fans.
- Some transceivers.

Hot-swappable does not mean risk-free. The wrong disk pull can break an array. The wrong PSU removal can power off a server if redundancy is already lost.

### Hot-swap checklist

Before hot-swapping:

- Confirm the exact component.
- Confirm component status through LEDs, ticket, and management tools.
- Confirm redundancy state.
- Confirm approved procedure.
- Confirm replacement part compatibility.
- Take a photo before removal if policy allows.
- Remove and replace one component at a time.
- Validate status after replacement.

## 11. Firmware, BIOS, and UEFI

Firmware is low-level software stored on hardware devices. BIOS or UEFI firmware initializes hardware and starts the boot process before the operating system loads.

### Terms to know

- BIOS: older firmware interface.
- UEFI: modern firmware interface.
- POST: power-on self-test.
- Boot order: sequence of devices the server tries to boot from.
- Firmware version: installed version of low-level software.
- Secure Boot: feature that verifies boot software.
- Lifecycle Controller: vendor management environment on some Dell servers.
- Intelligent Provisioning: vendor management environment on some HPE servers.

### Why firmware matters

Firmware affects hardware detection, stability, compatibility, and security. Firmware changes can be risky and must follow change management.

### Common firmware-related symptoms

- Server stuck during POST.
- New hardware not detected.
- Boot device missing.
- Firmware inventory mismatch.
- Remote console works but OS does not boot.
- System reports unsupported component.

## 12. Boot process

The boot process is the path from power-on to operating system startup.

### Basic boot flow

1. Power is applied.
2. Hardware initializes.
3. POST checks hardware.
4. BIOS/UEFI loads settings.
5. Firmware selects a boot device.
6. Bootloader starts.
7. Operating system kernel loads.
8. Services start.
9. Server becomes reachable on the network.

### Boot devices

Common boot devices:

- Local disk.
- RAID virtual disk.
- NVMe disk.
- USB device.
- ISO mounted through remote console.
- Network PXE boot.

### Common boot symptoms

- No power.
- No POST.
- POST error.
- No boot device found.
- Boot loop.
- Kernel panic.
- Operating system boots but network is down.

### Technician mindset

Troubleshooting boot issues means identifying where the flow stops. "Server down" is too vague. A better update is: "Server powers on, completes POST, then displays 'No boot device found' on remote console."

## 13. BMC, iDRAC, iLO, and IPMI

A BMC is a baseboard management controller. It is a small management system inside the server that can work even when the main operating system is down, as long as the server has standby power and network access to the management port.

Vendor names:

- Dell: iDRAC.
- HPE: iLO.
- Lenovo: XClarity Controller.
- Supermicro and many others: IPMI/BMC.

### What remote management can do

Depending on configuration and permissions, remote management may allow:

- Check power state.
- Power on, power off, or power cycle.
- View hardware health.
- View system event logs.
- Use remote console.
- Mount virtual media.
- Change boot device for next boot.
- Collect hardware inventory.

### How it differs from SSH

SSH connects to the operating system. iDRAC, iLO, or IPMI connects to the server management controller. If the operating system is crashed or not installed, SSH may not work, but remote console might still show the boot screen.

### Technician responsibility

She may not have permission to log into BMC tools, but she must understand what they are and how remote engineers use them. In remote-hands work, she may be asked to confirm the management cable, management port link light, or iDRAC/iLO IP label.

## 14. PXE boot and imaging basics

PXE boot allows a server to boot over the network. It is often used to install operating systems or run deployment tools.

### Basic PXE flow

1. Server starts.
2. Network card initializes.
3. Server asks the network for boot information.
4. DHCP provides an IP address and boot details.
5. Server downloads boot files from the network.
6. Imaging or installer environment starts.

### Common PXE issues

- Wrong boot order.
- Network cable in wrong port.
- No link light.
- DHCP not available.
- Server on wrong VLAN.
- PXE disabled in BIOS/UEFI.
- Secure Boot compatibility issue.

### Technician responsibility

A technician usually does not configure PXE services, but she may verify cabling, boot order, link lights, VLAN information from the ticket, and console messages.

## 15. Asset tags, serial numbers, service tags, and inventory

Asset inventory is a core data center discipline. Hardware must be traceable.

### Common identifiers

- Hostname.
- Asset tag.
- Serial number.
- Service tag.
- Rack name.
- U position.
- Manufacturer.
- Model.
- CPU count.
- RAM amount.
- Disk count.
- NIC MAC addresses.
- Power feed.
- PDU outlet.
- Switch and switch port.
- Owner or customer.
- Warranty status.

### Why inventory matters

Accurate inventory prevents wrong-device work, supports warranty replacement, improves troubleshooting, and helps incident response.

### Good inventory practice

- Record exact values, not guesses.
- Preserve leading zeros.
- Use consistent rack and U naming.
- Record before and after changes.
- Note missing labels.
- Attach evidence where allowed.

## 16. Common hardware symptoms

### No power

Possible causes:

- PDU outlet off.
- Cable loose.
- Failed PSU.
- Both power feeds unavailable.
- Server power button not pressed.
- Motherboard failure.

Good first checks:

- Check PSU LEDs.
- Check PDU outlet label and state.
- Check power cable seating.
- Check whether BMC is reachable.
- Confirm whether maintenance or power work is ongoing.

### No boot

Possible causes:

- Boot order incorrect.
- Boot disk missing.
- RAID virtual disk offline.
- OS corrupted.
- Firmware setting changed.
- Hardware POST failure.

Good first checks:

- Observe console message.
- Check POST completion.
- Check boot order.
- Check disk or RAID status if available.
- Document exact error text.

### Failed disk

Possible causes:

- Physical drive failure.
- Backplane issue.
- RAID controller issue.
- Disk pulled or unseated.
- Firmware reporting predictive failure.

Good first checks:

- Confirm bay number.
- Check drive LED.
- Confirm RAID state.
- Confirm replacement part.
- Replace only the confirmed drive.

### Failed fan

Possible causes:

- Fan module failed.
- Fan not seated.
- Air baffle missing.
- Firmware sensor issue.
- Server overheating.

Good first checks:

- Confirm fan number.
- Check health LEDs.
- Ensure air baffle is installed.
- Follow hot-swap procedure if supported.
- Monitor health after replacement.

### Memory error

Possible causes:

- Failed DIMM.
- DIMM not seated.
- Wrong slot population.
- Incompatible memory.
- Motherboard slot issue.

Good first checks:

- Confirm DIMM slot label.
- Check event logs.
- Confirm server model and memory rules.
- Do not randomly move DIMMs in production.

## 17. Linux hardware inspection commands

The Week 2 goal is not to become a Linux administrator. The goal is to collect basic evidence.

### `lscpu`

Shows CPU architecture, CPU count, threads, model, and virtualization support.

Useful questions:

- How many CPUs or cores does the system report?
- Does the CPU model match inventory?
- Is virtualization support visible?

### `free -h`

Shows memory usage in human-readable format.

Useful questions:

- How much memory is installed?
- Is the operating system seeing the expected memory?

### `lsblk`

Lists block devices such as disks and partitions.

Useful questions:

- What disks are visible?
- Which disk holds the root filesystem?
- Did a disk disappear after detachment?

### `df -h`

Shows mounted filesystems and free space.

Useful questions:

- Which filesystems are mounted?
- Is the root filesystem full?
- Is a data mount missing?

### `ip link`

Shows network interfaces and link state.

Useful questions:

- Which network interfaces exist?
- Is an interface up or down?
- What MAC addresses are visible?

### `dmesg | tail`

Shows recent kernel messages.

Useful questions:

- Did the kernel report disk errors?
- Did a device disconnect?
- Are there recent hardware-related messages?

### `sudo dmidecode`

Shows hardware information from DMI/SMBIOS tables.

Useful questions:

- What manufacturer and model does the system report?
- What serial number or asset tag is visible?
- What memory and BIOS information is visible?

### `sudo smartctl -a /dev/sda`

Shows disk health information for a supported disk.

Useful questions:

- Does SMART report health as passed?
- Are there reallocated sectors or other warning signs?
- Does the disk model and serial match the ticket?

## 18. Evidence, ticket updates, and escalation

Hardware work must be documented clearly. A good technician does not simply say "done." She records what she checked, what she changed, what changed afterward, and what remains unresolved.

### Good hardware ticket evidence

- Server identity verified.
- Rack and U position verified.
- Asset tag or service tag recorded.
- Component label or bay number recorded.
- Before status recorded.
- Action taken.
- After status recorded.
- Validation result.
- Photos attached if policy allows.
- Escalation details if blocked.

### Example weak update

"Changed disk. Looks fine."

### Example strong update

"Verified server `dc01-host07`, rack `A12`, U `18`, asset tag `DC-004381`. Disk bay `3` showed amber fault LED. Replaced bay `3` only with approved spare part `960GB SAS SSD`, serial recorded in inventory. After replacement, bay LED changed to green flashing. RAID rebuild reported by remote engineer at 14:22. No other components touched."

---

# Part 2: Week 2 questions and model answers

## Server fundamentals

### Question 1

**What is the main difference between a desktop computer and a server?**

Model answer:

A desktop is designed for one user, while a server is designed to provide services to many users or systems. Servers usually have stronger reliability features, remote management, redundant power, multiple network ports, ECC memory, and better serviceability. In a data center, the important point is that server hardware supports production services, so physical work must be verified and documented carefully.

### Question 2

**Why do rack units matter?**

Model answer:

Rack units identify how much vertical rack space equipment uses and help locate devices accurately. One rack unit is 1.75 inches. If a ticket says a server is in rack A12, U18, the technician must use that location to verify the exact device before touching it.

### Question 3

**What information should you verify before touching a server?**

Model answer:

I would verify the ticket, hostname, asset tag, serial or service tag, rack, U position, customer or owner, maintenance approval, expected impact, and the exact component in scope. If any detail is missing or inconsistent, I would stop and ask for clarification.

### Question 4

**Why is the service tag or serial number important?**

Model answer:

It uniquely identifies the hardware. Rack labels and hostnames can be wrong or outdated, so serial numbers and service tags help prevent wrong-device work and support warranty replacement, asset inventory, and vendor support.

## Components

### Question 5

**What does the CPU do?**

Model answer:

The CPU executes instructions for the operating system and applications. In a server, it is one of the main resources that determines how much compute work the server can handle. From a technician perspective, I need to know the CPU location, heat sink, socket sensitivity, and common error symptoms, but I should not handle CPU replacements without training and an approved procedure.

### Question 6

**What is ECC memory?**

Model answer:

ECC memory is error-correcting memory that can detect and correct some memory errors. It is common in servers because memory reliability matters for production systems. It does not make memory failure impossible, but it improves reliability and helps detect issues.

### Question 7

**Why do memory population rules matter?**

Model answer:

Servers may require memory modules to be installed in specific slots depending on CPU count and memory configuration. If DIMMs are placed incorrectly, the server may not boot, may report warnings, or may run with reduced performance. I would always follow the vendor procedure.

### Question 8

**What is PCIe used for in servers?**

Model answer:

PCIe is used for expansion cards such as NICs, HBAs, RAID controllers, GPUs, and accelerators. In rack servers, PCIe cards may be installed through risers because the chassis is shallow. If an adapter is missing after maintenance, I would check seating, slot, riser, cables, and event logs.

### Question 9

**What is a PSU?**

Model answer:

A PSU is a power supply unit. It converts incoming power into the voltages the server uses internally. Servers often have two PSUs for redundancy, ideally connected to separate power feeds.

### Question 10

**What does redundant power mean?**

Model answer:

Redundant power means the server has more than one power path, such as two PSUs connected to separate A and B feeds. If one path fails, the server can usually continue running. It still needs careful handling because redundancy may already be degraded.

## Storage and RAID

### Question 11

**What is the difference between HDD, SATA SSD, SAS SSD, and NVMe?**

Model answer:

An HDD is a spinning disk and is usually slower but cheaper per terabyte. A SATA SSD uses flash storage over a SATA interface. A SAS SSD is enterprise-focused and common in servers and storage arrays. NVMe uses PCIe and is usually much faster with lower latency.

### Question 12

**What is a drive bay?**

Model answer:

A drive bay is the physical slot where a disk is installed. In a replacement task, the bay number matters because replacing the wrong disk can damage service availability or break a RAID array.

### Question 13

**What is RAID?**

Model answer:

RAID combines multiple disks to provide performance, redundancy, or both. Different RAID levels behave differently. RAID can help survive some disk failures, but it is not a backup.

### Question 14

**Why is RAID not a backup?**

Model answer:

RAID protects against some hardware disk failures, but it does not protect against accidental deletion, data corruption, ransomware, application errors, or site loss. Backups are separate copies of data that can be restored.

### Question 15

**Explain RAID 1.**

Model answer:

RAID 1 mirrors data across two disks. If one disk fails, the other should still contain the data. It provides redundancy but only gives the usable capacity of one disk in a two-disk mirror.

### Question 16

**Explain RAID 5.**

Model answer:

RAID 5 uses striping with parity across at least three disks. It can usually survive one disk failure. It is capacity efficient compared with mirroring, but rebuilds can be risky on large arrays and write performance may be lower.

### Question 17

**Explain RAID 6.**

Model answer:

RAID 6 uses double parity across at least four disks and can usually survive two disk failures. It is often used where larger arrays need more protection during rebuilds.

### Question 18

**Explain RAID 10.**

Model answer:

RAID 10 combines mirroring and striping. It needs at least four disks and usually gives good performance and redundancy. It is often used for workloads that need both speed and fault tolerance.

### Question 19

**What is the difference between a RAID controller and an HBA?**

Model answer:

A RAID controller manages RAID and presents logical drives to the operating system. An HBA presents disks more directly to the operating system or storage software. The right choice depends on the platform design, so a technician should follow the documented architecture.

### Question 20

**What should you check before replacing a failed disk?**

Model answer:

I would verify server identity, rack and U, disk bay, drive LED, ticket instructions, RAID state, replacement part compatibility, and whether the array is already degraded. I would replace only the confirmed disk and document before and after status.

## Firmware, boot, and remote management

### Question 21

**What is BIOS or UEFI?**

Model answer:

BIOS or UEFI is firmware that initializes hardware and starts the boot process before the operating system loads. UEFI is the modern standard. It controls settings such as boot order and can show hardware status.

### Question 22

**What is POST?**

Model answer:

POST means power-on self-test. It is the hardware check that happens early in the boot process. If a server fails POST, the operating system may never start.

### Question 23

**What is boot order?**

Model answer:

Boot order is the sequence of devices the server tries when starting, such as local disk, virtual media, USB, or PXE network boot. Incorrect boot order can cause "no boot device" or unexpected installer screens.

### Question 24

**What is PXE boot?**

Model answer:

PXE boot is booting over the network. It is commonly used for imaging or operating system deployment. It depends on network link, BIOS/UEFI settings, DHCP, boot services, and often the correct VLAN.

### Question 25

**What is a BMC?**

Model answer:

A BMC is a baseboard management controller. It is a management system inside the server that can report hardware health and provide remote console access even when the main operating system is down.

### Question 26

**What are iDRAC and iLO?**

Model answer:

iDRAC is Dell's remote management platform and iLO is HPE's. They are vendor implementations of out-of-band server management. They can show hardware health, power state, logs, and remote console depending on permissions.

### Question 27

**What is the difference between iDRAC/iLO and SSH?**

Model answer:

SSH connects to the operating system over the network. iDRAC or iLO connects to the server management controller. If the operating system is down, SSH may fail, but iDRAC or iLO may still show power state, POST messages, and hardware health.

### Question 28

**What is virtual media?**

Model answer:

Virtual media lets a remote engineer mount an ISO or image through the remote management controller as if it were a local CD/DVD or USB device. It is useful for OS installation, rescue tools, or firmware utilities.

## Troubleshooting scenarios

### Question 29

**A server has no power. What do you check first?**

Model answer:

I would verify the exact server, then observe PSU LEDs, power cable seating, PDU outlet labels, and whether the BMC is reachable. I would check whether one or both PSUs are affected and whether there is known power maintenance. I would not move cables without approval.

### Question 30

**A server powers on but says "No boot device found." What does that suggest?**

Model answer:

It suggests the server completes at least part of POST but cannot find a valid boot device. Possible causes include boot order changes, missing or failed boot disk, RAID virtual disk offline, or OS bootloader issues. I would document the exact message and check boot order and storage status if authorized.

### Question 31

**A disk has an amber LED. What do you do?**

Model answer:

I would verify the server, bay number, and ticket instructions. I would confirm the amber LED matches the reported failed disk and check whether the array is already degraded. I would replace only the confirmed disk using the approved spare and document the new serial and rebuild status if available.

### Question 32

**A server has no network after a disk replacement. What do you check?**

Model answer:

Because the task involved disk replacement, I would first check whether any network cable was accidentally bumped, whether link lights are present, and whether the correct port is connected. I would also check the management and production ports are not confused. If OS access is available, I would use `ip link` to check interfaces.

### Question 33

**A fan error appears after opening the chassis. What could be wrong?**

Model answer:

A fan may not be seated properly, an air baffle may be missing, a cable may be obstructing airflow, or a fan module may have failed. I would follow the vendor procedure, confirm the fan identifier, reseat only if authorized, and validate health after closing the chassis.

### Question 34

**A memory error points to DIMM B2. What information should you record?**

Model answer:

I would record server identity, slot label, event message, current memory inventory if available, DIMM part number, serial if visible, and any before/after health status. I would also confirm the vendor memory population rules before any replacement.

### Question 35

**What does "change one thing at a time" mean in hardware troubleshooting?**

Model answer:

It means avoiding multiple simultaneous changes because they make it harder to know what fixed or worsened the issue. For example, if checking a cable issue, change one cable or one port only when approved, then test and document the result.

## Documentation and professionalism

### Question 36

**What makes a good hardware ticket update?**

Model answer:

A good update includes what was verified, what was observed, what action was taken, timestamps, exact component identifiers, and validation results. It avoids vague language and gives remote engineers enough evidence to decide the next step.

### Question 37

**Why should you take photos before hardware work if policy allows?**

Model answer:

Photos can record original cable positions, labels, component state, and LEDs. They help restore the original state if something is unclear and provide evidence for the ticket.

### Question 38

**What should you do if a label in the rack does not match the ticket?**

Model answer:

I would stop and escalate. I would document the mismatch, provide the observed labels, rack and U position, asset tag, serial number, and ask for confirmation before touching the device.

### Question 39

**What should you do if a remote engineer asks you to pull a disk but the LED does not match their instruction?**

Model answer:

I would not pull the disk yet. I would explain the mismatch, provide bay numbers and LED states, and ask them to reconfirm through the management tool or ticket. Pulling the wrong disk can cause data loss or an outage.

### Question 40

**What is the strongest Week 2 interview message?**

Model answer:

The strongest message is that I understand server hardware enough to be useful, but I also understand production risk. I verify identity, follow procedures, document evidence, and escalate when the physical state does not match the ticket.

---

# Part 3: Lab exercises with hints

## Lab 1: Build a front and back server diagram

### Goal

Create a visual diagram of a typical rack server from the front and back.

### Steps

1. Search for vendor images or diagrams of a common 1U or 2U rack server, such as a Dell PowerEdge or HPE ProLiant.
2. Draw a front view.
3. Draw a back view.
4. Label the main visible parts.
5. Add a short note explaining what each part does.

### Include these labels

- Drive bays.
- Drive LEDs.
- Power button.
- System health LED.
- Service tag area.
- PSUs.
- Production NIC ports.
- Management port.
- USB port.
- VGA or console port.
- PCIe expansion slots.
- Cable management arm if visible.

### Hints

- Use diagrams.net, PowerPoint, Canva, or paper and a phone scan.
- Do not worry about making it artistic. Accuracy matters more.
- Use arrows and labels.
- Include a note that real layouts vary by vendor and model.

### Expected portfolio output

`01-server-front-back-diagram.png` or `01-server-front-back-diagram.drawio`

## Lab 2: Create a server component glossary

### Goal

Build a practical glossary of server hardware terms.

### Steps

1. Create a markdown file.
2. Add at least 50 terms.
3. For each term, write a plain-English definition.
4. Add one operational note for important terms.

### Required terms

- Server
- Rack unit
- Chassis
- Bezel
- CPU
- Socket
- Core
- Thread
- Heat sink
- RAM
- ECC
- DIMM
- Motherboard
- PCIe
- Riser
- PSU
- A feed
- B feed
- PDU
- HDD
- SSD
- SATA
- SAS
- NVMe
- Drive bay
- Backplane
- Caddy
- RAID
- HBA
- RAID controller
- Hot spare
- NIC
- MAC address
- Management port
- BMC
- iDRAC
- iLO
- IPMI
- BIOS
- UEFI
- POST
- Boot order
- PXE
- Firmware
- Asset tag
- Serial number
- Service tag
- Link light
- SMART
- Event log

### Hints

- Keep definitions short.
- Add "why it matters in data center work" to at least 15 terms.
- Do not copy long vendor text. Write it in her own words.

### Expected portfolio output

`02-server-component-glossary.md`

## Lab 3: Compare desktop and server hardware

### Goal

Explain why servers are designed differently from desktop computers.

### Steps

1. Create a two-column comparison table.
2. Compare at least 12 areas.
3. Add a short conclusion about operational risk.

### Comparison areas

- Intended use.
- Physical format.
- Power supplies.
- Memory.
- Storage.
- Network ports.
- Remote management.
- Cooling.
- Expansion cards.
- Uptime expectations.
- Asset tracking.
- Maintenance process.
- Noise and airflow.
- Cost.

### Hints

- The answer is not "servers are faster." Some desktops can be very powerful.
- Focus on reliability, remote operation, redundancy, and serviceability.

### Expected portfolio output

`03-desktop-vs-server-comparison.md`

## Lab 4: Build a VirtualBox server-style VM

### Goal

Use a VM to practice thinking like a server technician.

### Steps

1. Create a new VirtualBox VM.
2. Name it `week02-hardware-lab`.
3. Install Ubuntu Server or use an existing Linux VM.
4. Assign at least 2 CPUs if the laptop can handle it.
5. Assign at least 2 GB RAM.
6. Add one virtual disk for the operating system.
7. Add a second small virtual disk.
8. Boot the VM and log in.
9. Run the hardware inspection commands.
10. Save command outputs or screenshots.

### Commands

```bash
lscpu
free -h
lsblk
df -h
ip link
dmesg | tail
```

### Hints

- A VM is not the same as a real server, but it is useful for learning boot order, virtual disks, and Linux inspection commands.
- Label each screenshot with what it proves.

### Expected portfolio output

`08-virtualbox-boot-lab.md`

## Lab 5: Practice boot order changes

### Goal

Understand how boot order affects startup.

### Steps

1. Shut down the VM.
2. Open the VM settings.
3. Review the boot order.
4. Attach an ISO.
5. Move optical/ISO above the hard disk.
6. Start the VM and observe what happens.
7. Move the hard disk back above the ISO.
8. Start the VM again.
9. Document the difference.

### Questions to answer

- What happened when the ISO was first in the boot order?
- What happened when the disk was first?
- How could an incorrect boot order affect a real server?
- What exact ticket update would you write if you saw the wrong boot target?

### Hints

- Do not rush the observation. The console message is the evidence.
- Take screenshots if possible.

### Expected portfolio output

Add a section called "Boot order test" to `08-virtualbox-boot-lab.md`.

## Lab 6: List disks and filesystems in Linux

### Goal

Practice identifying disks and mounted filesystems.

### Steps

1. Boot the Linux VM.
2. Run `lsblk`.
3. Run `df -h`.
4. Identify the OS disk.
5. Identify the extra disk.
6. If the extra disk is not mounted, note that clearly.
7. Write a short explanation of the difference between a disk and a mounted filesystem.

### Hints

- `lsblk` shows block devices.
- `df -h` shows mounted filesystems.
- A disk can exist without being mounted.

### Expected portfolio output

`09-disk-failure-simulation.md`

## Lab 7: Simulate a disk disappearance

### Goal

Observe what changes when a virtual disk is removed.

### Steps

1. With the VM powered off, confirm two virtual disks are attached.
2. Boot and run `lsblk`.
3. Save the output.
4. Shut down the VM.
5. Detach the second virtual disk from the VM settings.
6. Boot again.
7. Run `lsblk`.
8. Compare before and after output.
9. Run `dmesg | tail`.
10. Write a mock ticket update describing what changed.

### Safety note

Do this only in a lab VM. Do not detach disks from a real system unless the procedure is approved.

### Hints

- If the second disk was not mounted, the OS may boot normally.
- If the removed disk held an important filesystem, the system might fail or boot with errors.
- The point is to document observed evidence, not to create a perfect failure.

### Expected portfolio output

Add before/after outputs and notes to `09-disk-failure-simulation.md`.

## Lab 8: Complete a RAID reasoning worksheet

### Goal

Understand the tradeoffs between RAID levels.

### Steps

Create a table with these columns:

- RAID level.
- Minimum disks.
- Usable capacity example.
- Survives how many disk failures.
- Main benefit.
- Main risk.
- Good use case.

### Use these examples

- Two 1 TB disks in RAID 1.
- Three 1 TB disks in RAID 5.
- Four 1 TB disks in RAID 6.
- Four 1 TB disks in RAID 10.
- Four 1 TB disks in RAID 0.

### Questions to answer

- Which option gives the most usable capacity?
- Which options provide redundancy?
- Which option is unsafe for important data?
- Why does a backup still matter?

### Hints

- Keep the math simple. The goal is conceptual understanding.
- Mention that real usable capacity can vary depending on vendor, metadata, and disk size reporting.

### Expected portfolio output

`05-raid-level-comparison-table.md`

## Lab 9: Create a boot-flow diagram

### Goal

Show the path from power-on to service availability.

### Steps

1. Draw a sequence diagram or flowchart.
2. Start with "Power applied."
3. Include POST.
4. Include BIOS/UEFI.
5. Include boot device selection.
6. Include bootloader.
7. Include operating system kernel.
8. Include services starting.
9. Include network availability.
10. Add common failure points at each stage.

### Hints

- Make the diagram practical rather than theoretical.
- Add example symptoms: no power, POST error, no boot device, kernel panic, network down.

### Expected portfolio output

`06-boot-flow-diagram.png` or `06-boot-flow-diagram.drawio`

## Lab 10: Build a BMC/iDRAC/iLO/IPMI notes page

### Goal

Explain out-of-band management clearly.

### Steps

1. Create a notes page.
2. Define BMC, iDRAC, iLO, and IPMI.
3. Explain what remote console is.
4. Explain virtual media.
5. Compare remote management with SSH.
6. Add a short scenario where remote management helps.
7. Add a short scenario where management network cabling could be the problem.

### Hints

- Do not include passwords or real management IPs.
- Focus on concepts and operational use.

### Expected portfolio output

`07-bmc-idrac-ilo-ipmi-notes.md`

## Lab 11: Create an asset inventory example

### Goal

Practice recording server inventory like a data center technician.

### Steps

1. Create a spreadsheet or CSV.
2. Add at least 5 fictional servers.
3. Use realistic but fake values.
4. Include rack, U, hostname, asset tag, serial, model, power feeds, NIC MACs, and switch ports.
5. Add a notes column for missing labels or observations.

### Required columns

- Hostname.
- Asset tag.
- Serial or service tag.
- Manufacturer.
- Model.
- Rack.
- U position.
- Owner.
- CPU.
- RAM.
- Disk layout.
- Management MAC.
- Production MAC 1.
- Production MAC 2.
- PSU 1 PDU/outlet.
- PSU 2 PDU/outlet.
- Switch 1/port.
- Switch 2/port.
- Notes.

### Hints

- Do not use real company data.
- Make the format consistent.
- Preserve leading zeros in serial-like values by storing them as text.

### Expected portfolio output

`10-asset-inventory-example.csv` or `10-asset-inventory-example.xlsx`

## Lab 12: Hardware troubleshooting flowcharts

### Goal

Create simple decision flows for common hardware symptoms.

### Flowcharts to create

- No power.
- No boot.
- Failed disk.
- Failed fan.
- Memory error.
- No network after hardware work.

### Each flowchart should include

- Verify server identity.
- Observe symptom.
- Check physical indicators.
- Check management or OS evidence if available.
- Record findings.
- Decide whether to proceed or escalate.

### Hints

- A good flowchart includes "stop and escalate" paths.
- Do not write steps that require unauthorized changes.
- Use short action boxes.

### Expected portfolio output

`11-hardware-troubleshooting-flowcharts.md`

## Lab 13: Write mock hardware ticket updates

### Goal

Practice professional hardware communication.

### Scenarios

Write updates for:

1. Failed disk replacement.
2. PSU amber LED investigation.
3. No boot device found on console.
4. Memory error where slot label does not match ticket.
5. No network after server maintenance.

### For each scenario, include

- Acknowledgement.
- Verification details.
- Observations.
- Action taken or reason for stopping.
- Validation.
- Escalation question if needed.

### Hints

- Use exact labels and timestamps.
- Avoid "looks fine" unless supported by evidence.
- Include "no other components touched" when useful.

### Expected portfolio output

`12-mock-hardware-ticket-updates.md`

## Lab 14: Build a Week 2 mock interview script

### Goal

Prepare confident spoken answers.

### Steps

1. Choose 12 questions from Part 2.
2. Write short answers in her own words.
3. Record herself answering them.
4. Listen back and improve unclear answers.
5. Add one example that shows careful production mindset.

### Hints

- Aim for 45-90 seconds per answer.
- Sound practical, not memorized.
- Mention verification, documentation, and escalation.

### Expected portfolio output

Add a section called "Interview script" to `13-week-02-self-assessment.md`.

## Lab 15: Final Week 2 self-assessment

### Goal

Check whether she can explain and apply Week 2 material.

### Self-assessment table

| Skill | Can do without notes | Can do with notes | Need more practice |
|---|---|---|---|
| Identify server front/back components | | | |
| Explain CPU, RAM, PSU, NIC, RAID, HBA | | | |
| Compare HDD, SATA SSD, SAS SSD, NVMe | | | |
| Explain RAID 0, 1, 5, 6, 10 | | | |
| Explain why RAID is not backup | | | |
| Describe BIOS/UEFI and boot order | | | |
| Explain BMC, iDRAC, iLO, IPMI | | | |
| Use `lscpu`, `free -h`, `lsblk`, `df -h` | | | |
| Use `ip link` and `dmesg | tail` | | | |
| Create a clean asset inventory | | | |
| Write hardware ticket updates | | | |
| Know when to stop and escalate | | | |

### Expected portfolio output

`13-week-02-self-assessment.md`

---

# Part 4: Templates to copy into the portfolio

## Asset inventory template

```markdown
| Hostname | Asset tag | Serial/service tag | Make/model | Rack | U | Owner | CPU | RAM | Disk layout | Mgmt MAC | Prod MAC 1 | Prod MAC 2 | PSU 1 | PSU 2 | Switch/port 1 | Switch/port 2 | Notes |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| dc01-host01 | DC-000101 | SVCTAG001 | Dell PowerEdge R650 | A12 | 18 | Platform | 2 x CPU | 256 GB | 2 x 960 GB RAID1 | 00:11:22:33:44:55 | 00:11:22:33:44:56 | 00:11:22:33:44:57 | PDU-A/18 | PDU-B/18 | sw-a01/Eth1/18 | sw-b01/Eth1/18 | Example only |
```

## Hardware replacement checklist

```markdown
# Hardware Replacement Checklist

Ticket:
Date/time:
Technician:
Remote engineer/customer:

## Verification

- [ ] Ticket number confirmed.
- [ ] Approval or maintenance window confirmed.
- [ ] Hostname confirmed.
- [ ] Asset tag confirmed.
- [ ] Serial/service tag confirmed.
- [ ] Rack and U position confirmed.
- [ ] Component identifier confirmed.
- [ ] Replacement part confirmed.
- [ ] Expected impact understood.
- [ ] Rollback or escalation path understood.

## Before work

- [ ] Current status recorded.
- [ ] LEDs observed and documented.
- [ ] Photos taken if allowed.
- [ ] Cable positions recorded if relevant.
- [ ] Redundancy state confirmed if relevant.
- [ ] ESD and safety precautions followed.

## Work performed

Action taken:

Component removed:

Replacement component:

New serial number:

Time started:

Time completed:

## Validation

- [ ] Component LED normal.
- [ ] Management tool or remote engineer confirms healthy state.
- [ ] Operating system sees component if relevant.
- [ ] Ticket updated with evidence.
- [ ] Inventory updated.
- [ ] No unrelated components touched.
```

## Boot troubleshooting checklist

```markdown
# Boot Troubleshooting Checklist

Server:
Rack/U:
Asset tag:
Observed by:
Time:

## Current state

- [ ] No power.
- [ ] Power present, no POST.
- [ ] POST error.
- [ ] POST complete, no boot device.
- [ ] Bootloader error.
- [ ] OS starts, then fails.
- [ ] OS starts but network/service unavailable.

## Evidence

Exact console message:

LED state:

Recent change:

Boot order observed:

Storage status observed:

Remote management status:

## Next step

- [ ] Proceed according to approved procedure.
- [ ] Ask remote engineer to verify through BMC.
- [ ] Escalate due to unclear identity or risk.
- [ ] Escalate to vendor/hardware team.
```

## Disk replacement ticket template

```markdown
# Disk Replacement Ticket Update

Acknowledged ticket at:

Verified server:

Rack/U:

Asset tag:

Failed disk reported:

Observed disk LED:

RAID/array state if provided:

Replacement part:

Action:

New disk serial:

After status:

Rebuild status:

Notes:

No other components touched:
```

## No power investigation template

```markdown
# No Power Investigation

Ticket:
Server:
Rack/U:
Asset tag:

## Observations

Front panel LED:
PSU 1 LED:
PSU 2 LED:
Power cable 1 seated:
Power cable 2 seated:
PDU outlet labels:
BMC reachable:
Any nearby power alarms:

## Action taken

## Result

## Escalation question
```

## RAID comparison template

```markdown
| RAID level | Minimum disks | Example usable capacity | Disk failures tolerated | Benefit | Risk | Good use case |
|---|---:|---|---:|---|---|---|
| RAID 0 | 2 | | 0 | Speed/capacity | No redundancy | Temporary data |
| RAID 1 | 2 | | 1 | Simple mirror | Capacity cost | OS disks |
| RAID 5 | 3 | | 1 | Capacity efficient | Rebuild risk | General storage |
| RAID 6 | 4 | | 2 | More fault tolerance | Write penalty | Larger arrays |
| RAID 10 | 4 | | Varies by failed disks | Performance and redundancy | Capacity cost | Databases/VMs |
```

## Hardware handover template

```markdown
# Hardware Handover Note

Shift/date:
Prepared by:

## Completed work

- Ticket:
- Server:
- Work completed:
- Validation:

## Open items

- Ticket:
- Server:
- Current state:
- Blocker:
- Next recommended action:

## Risks or watch items

- Item:
- Why it matters:
- Who has been informed:

## Evidence attached

- Photos:
- Logs:
- Command output:
- Inventory update:
```

---

# Part 5: Week 2 final exam

## Written exam

Answer these without looking at notes:

1. Explain the difference between a desktop and a server.
2. List ten visible parts on the front or back of a rack server.
3. What does a CPU do?
4. What is ECC memory and why is it useful?
5. What are memory population rules?
6. What is PCIe used for?
7. What is a PSU?
8. Why should redundant PSUs be connected to separate feeds?
9. Compare HDD, SATA SSD, SAS SSD, and NVMe.
10. What is RAID?
11. Explain RAID 0, 1, 5, 6, and 10.
12. Why is RAID not a backup?
13. What is the difference between a RAID controller and an HBA?
14. What is BIOS/UEFI?
15. What is POST?
16. What is boot order?
17. What is PXE boot?
18. What is a BMC?
19. What is the difference between iDRAC/iLO and SSH?
20. What asset information should be recorded before hardware work?
21. What would you check for a no-power issue?
22. What would you check for a no-boot issue?
23. What would you do if a disk bay LED does not match the ticket?
24. What Linux command lists disks?
25. What Linux command shows network interfaces?

## Practical exam

Complete these tasks:

1. Draw and label a front/back rack server diagram.
2. Create a RAID comparison table.
3. Create a boot-flow diagram from power-on to service availability.
4. Build or open a Linux VM and run:

```bash
lscpu
free -h
lsblk
df -h
ip link
dmesg | tail
```

5. Explain what each command output proves.
6. Simulate removing a second virtual disk and document the before/after `lsblk` output.
7. Create five fictional asset inventory rows.
8. Write a mock failed-disk replacement ticket update.
9. Write a mock "stop and escalate" update for a mismatch between ticket and physical label.
10. Answer five Week 2 interview questions out loud.

## Passing standard

She passes Week 2 if she can:

- Identify and explain server components confidently.
- Explain storage and RAID without confusing redundancy and backup.
- Describe the boot process and common failure points.
- Explain remote management versus operating-system access.
- Use basic Linux commands to collect hardware evidence.
- Create a usable asset inventory.
- Write clear hardware ticket updates.
- Stop and escalate when the physical state does not match the ticket.

---

# Part 6: Interview positioning for Week 2

Week 2 gives her practical credibility. She should not pretend to be a senior hardware engineer. The stronger position is:

"I understand the core server components and the risks around physical work. I can verify the correct asset, identify common hardware parts, collect evidence with basic Linux commands, document changes clearly, and escalate instead of guessing when something does not match the ticket."

## Strong interview themes

- I verify before touching hardware.
- I understand that servers support production services.
- I can explain hardware in plain English.
- I can follow vendor procedures.
- I can document component identifiers and before/after status.
- I understand RAID is not backup.
- I know the difference between remote management and OS access.
- I know when to stop and escalate.

## Example answer: failed disk replacement

"First I would verify the exact server using the ticket, rack and U position, asset tag, and service tag. Then I would confirm the affected disk bay from the ticket and by observing the drive LED. If I had access to confirmation from the remote engineer or management tool, I would make sure the array state matches the replacement instruction. I would replace only the confirmed disk, record the new disk serial, and update the ticket with before and after status, including whether the rebuild started. If the bay number or LED did not match the ticket, I would stop and escalate before pulling anything."

## Example answer: no boot

"I would try to identify where the boot process is stopping. Does the server have power? Does it complete POST? Is there a console error such as 'No boot device found'? If it reaches firmware but cannot boot, I would check boot order and storage status if authorized. I would document the exact console message and avoid changing settings unless the ticket or remote engineer approved it."

## Example answer: iDRAC/iLO versus SSH

"SSH depends on the operating system being up and reachable on the network. iDRAC or iLO is out-of-band management through the server management controller. It can often show power state, hardware health, event logs, and remote console even if the operating system is down."

---

# Part 7: Week 2 completion checklist

- [ ] I created a Week 2 portfolio folder.
- [ ] I completed the server front/back diagram.
- [ ] I wrote a server component glossary.
- [ ] I compared desktop and server hardware.
- [ ] I explained CPU, RAM, motherboard, PCIe, PSU, disks, NICs, RAID controller, HBA, and BMC.
- [ ] I compared HDD, SATA SSD, SAS SSD, and NVMe.
- [ ] I completed the RAID comparison table.
- [ ] I can explain why RAID is not a backup.
- [ ] I created a boot-flow diagram.
- [ ] I wrote BMC/iDRAC/iLO/IPMI notes.
- [ ] I completed the VirtualBox boot-order lab.
- [ ] I completed the disk disappearance simulation.
- [ ] I created an asset inventory example.
- [ ] I created hardware troubleshooting flowcharts.
- [ ] I wrote mock hardware ticket updates.
- [ ] I answered the Week 2 model questions.
- [ ] I completed the Week 2 final exam.
- [ ] I can explain when to stop and escalate during hardware work.
- [ ] My Week 2 portfolio folder is complete.
