# Week 7 Detailed Workbook: Cloud, Reliability, and Junior Engineer Skills

## Table of contents

- [Purpose of this workbook](#purpose-of-this-workbook)
- [Week 7 target level](#week-7-target-level)
- [Scope boundary: what is new this week](#scope-boundary-what-is-new-this-week)
- [Suggested weekly schedule](#suggested-weekly-schedule)
- [Day-by-day Week 7 study order](#day-by-day-week-7-study-order)
- [Required Week 7 portfolio artifacts](#required-week-7-portfolio-artifacts)
- [Part 1: Comprehensive Week 7 topics](#part-1-comprehensive-week-7-topics)
- [Part 2: Week 7 questions and model answers](#part-2-week-7-questions-and-model-answers)
- [Part 3: Lab exercises with hints](#part-3-lab-exercises-with-hints)
- [Part 4: Templates to copy into the portfolio](#part-4-templates-to-copy-into-the-portfolio)
- [Part 5: Week 7 final exam](#part-5-week-7-final-exam)
- [Part 6: Interview positioning for Week 7](#part-6-interview-positioning-for-week-7)
- [Part 7: Week 7 completion checklist](#part-7-week-7-completion-checklist)

## Purpose of this workbook

This workbook expands Week 7 of the Data Center Engineer / Data Center Technician study plan. It explains how the physical work from earlier weeks supports virtualized, cloud-hosted, and production services.

The goal is not to become a cloud administrator, storage engineer, or hypervisor administrator in one week. The goal is to understand the chain of dependencies behind a service, recognize shared failure domains, interpret monitoring information responsibly, and communicate the likely customer impact of physical or infrastructure work.

By the end of the week, she should be able to explain how a user request travels through virtual and physical layers; distinguish reliability, recovery, and data-protection concepts; identify the right owner for a cross-layer issue; and describe her authorization boundary honestly.

## Week 7 target level

The target is not "I know cloud vocabulary." The target is:

- She can distinguish a physical host, hypervisor, guest VM, cluster, virtual network, and datastore.
- She can trace a service from a user-facing component through virtual compute, network, storage, rack infrastructure, power, and cooling.
- She can distinguish local, block, file, and object storage at a practical level.
- She can explain the difference between snapshot, backup, replication, redundancy, high availability, disaster recovery, RPO, and RTO.
- She can identify failure domains and describe a realistic blast radius without claiming a design is more resilient than it is.
- She can distinguish metrics, logs, traces, events, dashboards, thresholds, baselines, and alerts.
- She can use monitoring evidence to establish scope and ownership without declaring a root cause too early.
- She can explain regions, availability zones, instances, managed services, security groups, and shared responsibility in plain language.
- She can apply least privilege, MFA, audit trails, confidentiality, and data-minimization principles to infrastructure work.
- She can explain when a physical technician gathers evidence and when a platform, storage, cloud, security, or application team must make the change.

## Scope boundary: what is new this week

Weeks 1-6 already cover basic access safety, hardware, networking, Linux evidence, physical racks, and incident handling. This week does not reteach IP addressing, switch configuration, Linux command syntax, RAID levels, or basic cable work.

| Earlier knowledge | Week 7 adds |
|---|---|
| Server, network, and storage components | How they become shared virtual and cloud service dependencies |
| A/B power and rack resilience | Failure domains and the limits of component redundancy |
| Linux and incident evidence | Monitoring interpretation, correlation, capacity, and ownership |
| Change and escalation practices | Maintenance impact on clusters, services, and customer experience |
| Physical and logical security basics | Shared responsibility, audit evidence, identity boundaries, and data minimization |

Use a local VM lab, diagrams, and fictional scenarios. Do not change a production hypervisor, cloud account, storage array, access policy, or backup schedule for this workbook.

## Suggested weekly schedule

| Day | Focus | Main output |
|---|---|---|
| Day 1 | Physical-to-service dependency chain, virtualization, hosts, guests, clusters | Service-chain diagram and host/guest inventory |
| Day 2 | Storage paths, data protection, HA, DR, RPO/RTO, and failure domains | Storage comparison and resilience matrix |
| Day 3 | Monitoring, alert meaning, correlation, capacity, and maintenance impact | Baseline note and alert-triage worksheet |
| Day 4 | Cloud concepts, shared responsibility, identity, access, audit, and data awareness | Cloud map and access-evidence checklist |
| Day 5 | Cross-layer tabletop, architecture explanation, interviews, and assessment | Incident exercise, interview script, and self-assessment |
| Day 6 optional | Rehearse diagrams and explanations without notes | Corrected diagrams and speaking notes |
| Day 7 optional | Rest or catch-up | Clean Week 7 portfolio |

## Day-by-day Week 7 study order

| Day | Study sections | Practice | Portfolio output |
|---|---|---|---|
| Day 1 | Sections 1-3: service chain, virtualization, clusters, resource allocation, and maintenance awareness | Labs 1-3; Questions 1-14 | Dependency map, host/guest inventory, and resource worksheet |
| Day 2 | Sections 4-6: virtual network path, storage, data protection, availability, recovery, and failure domains | Labs 4-8; Questions 15-28 | Network path, storage comparison, RPO/RTO, and failure-domain map |
| Day 3 | Sections 7-8: monitoring, alert triage, correlation, capacity, and maintenance impact | Labs 9-11; Questions 29-38 | Baseline, triage worksheet, and maintenance-impact note |
| Day 4 | Sections 9-10: cloud concepts, shared responsibility, access, audit, and data awareness | Labs 12-13; Questions 39-46 | Shared-responsibility map and access checklist |
| Day 5 | Sections 11-12: junior engineer behavior, cross-layer incident practice, and interview preparation | Labs 14-16; Questions 47-55 | Cross-layer incident, interview script, and self-assessment |
| Day 6 optional | Explain one architecture and one risk map aloud | Repeat Labs 1, 8, and 14 | Recorded or written rehearsal notes |
| Day 7 optional | Rest or catch-up | Review all artifacts for safe, consistent wording | Ready-to-review Week 7 portfolio |

## Required Week 7 portfolio artifacts

Create a folder called week-07-cloud-data-center-bridge and include:

    week-07-cloud-data-center-bridge/
      README.md
      01-physical-to-service-dependency-map.md
      02-host-guest-and-cluster-inventory.md
      03-vm-resource-allocation-worksheet.md
      04-virtual-to-physical-network-path.md
      05-storage-data-path-and-comparison.md
      06-data-protection-comparison.md
      07-rpo-rto-recovery-objectives.md
      08-ha-and-failure-domain-map.md
      09-monitoring-baseline-and-threshold-note.md
      10-alert-triage-and-correlation-worksheet.md
      11-capacity-and-maintenance-impact-note.md
      12-cloud-shared-responsibility-map.md
      13-access-and-audit-evidence-checklist.md
      14-cross-layer-incident-simulation.md
      15-week-07-interview-script.md
      16-week-07-self-assessment.md

---

# Part 1: Comprehensive Week 7 topics

## 1. The physical-to-service dependency chain

"Cloud" describes a service model, not an absence of physical infrastructure. A customer may interact with an application URL, but that service depends on layers that include compute, virtual networks, physical networks, storage, power, cooling, access controls, monitoring, and operations staff.

One simplified path is:

    User -> DNS or load balancer -> application service or VM -> virtual network -> host NIC -> physical switch -> storage or dependency service

Under the application host:

    Physical server -> rack -> A/B rack power -> facility power and cooling

The exact path varies by design. The habit to build is dependency thinking: a symptom at the user layer can arise from several lower layers, and a physical change can have a larger effect if the component is shared.

Keep customer or data traffic separate from management traffic in diagrams. A management interface may allow a team to observe or administer a host even if the customer-facing service path is impaired.

## 2. Virtualization foundations

Virtualization allows one physical host to run multiple isolated guest systems. Key terms:

| Term | Practical meaning |
|---|---|
| Hypervisor | Software layer that runs and manages guest VMs on a physical host |
| Host | The physical server that provides CPU, memory, network, and storage resources |
| Guest VM | A virtual machine using assigned virtual resources from the host or cluster |
| vCPU and vRAM | Virtual CPU and memory allocated to a guest |
| vNIC | A virtual network interface presented to a guest |
| Virtual disk | A file or logical volume presented to a guest as a disk |
| Datastore | A storage location used by a virtualization platform for virtual disks and related files |
| Virtual switch | A software switch that connects virtual network interfaces to each other and to host uplinks |

A desktop hypervisor in a lab is usually a Type 2 model running on top of a normal operating system. Production environments commonly use a Type 1 hypervisor that runs directly on server hardware. The key operational lesson is that virtual does not mean imaginary: a VM still consumes real resources and depends on real infrastructure.

## 3. Clusters, resource allocation, and maintenance impact

A cluster groups hosts so workloads can be managed across them. The details vary by platform, but common concepts include nodes or hosts, resource pools, scheduling, maintenance mode, evacuation, and live migration.

Virtualization improves flexibility, but it introduces shared dependencies:

- One host may run many VMs.
- One shared datastore may serve many hosts.
- One network uplink or virtual-switch configuration may affect many workloads.
- A host maintenance task may require enough spare capacity elsewhere for workloads to move.

Do not assume a VM is highly available just because it is virtual. Availability requires an approved design, healthy dependencies, capacity, and validation. A junior technician can identify missing information: which VMs are on the host, where they would move, whether capacity exists, who owns the maintenance decision, and how success will be confirmed.

## 4. Virtual-to-physical networking

Week 3 covered basic network concepts. Here, the focus is the bridge between a guest and the physical path:

    VM vNIC -> virtual switch or port group -> host physical NIC -> top-of-rack switch port -> wider network path

An issue can appear at several points. A VM may have a healthy virtual interface while a host uplink is impaired; a physical link may be healthy while a virtual policy or guest firewall blocks traffic. The technician should record expected and observed path identifiers, collect approved evidence, and engage the network or platform owner rather than altering virtual-switch configuration without authorization.

For a physical task, the important questions are:

- Which host NIC and switch port should the service use?
- Is the physical port map current?
- Does the ticket name the expected environment and service impact?
- Will moving a cable affect one VM, many VMs, management access, storage traffic, or backup traffic?

## 5. Storage services and data paths

Storage can be described by how it is presented and used:

| Type | Practical use | Example concern |
|---|---|---|
| Local or direct-attached storage | Disks physically attached to one server | Host failure can affect data unless protected elsewhere |
| Block storage | Raw blocks presented as a volume or LUN | Often used by databases and virtualization datastores |
| File storage | Shared files and folders over a network | Permissions, capacity, and network access affect many users |
| Object storage | Data stored as objects with metadata and API access | Different access and recovery model from a mounted disk |
| SAN | A storage network commonly providing block storage | Fabric, controller, path, and latency can be shared dependencies |
| NAS | Network-attached file storage | File-service availability and network path are shared dependencies |

For a virtual disk, a simplified path may be:

    Guest virtual disk -> datastore or volume -> storage path -> controller or storage service -> physical media

Capacity, latency, throughput, and IOPS are different measures. Capacity is available space. Latency is delay. Throughput is data transferred per unit of time. IOPS is input/output operations per second. A service may have enough free storage capacity and still suffer from high latency.

## 6. Data protection, availability, and recovery

These terms are often confused. They solve different problems:

| Mechanism | Main purpose | Important limitation |
|---|---|---|
| Snapshot | Point-in-time, usually short-term capture of a state | Not automatically an independent backup or proof of restore |
| Backup | Recover data or systems from a separate copy | A successful job is not proof that restoration will work |
| Replication | Copy data to another system or location | Can copy corruption or deletion depending on design |
| Redundancy | Keep alternate components or paths available | Does not protect against all errors or data loss |
| High availability | Reduce service interruption after defined failures | Depends on every required dependency and capacity |
| Disaster recovery | Restore service after a larger failure domain is lost | Requires tested plans, people, data, and alternate capacity |

RPO, or recovery point objective, is the maximum acceptable data loss measured in time. RTO, or recovery time objective, is the targeted time to restore service. They are business objectives, not promises a technician should invent. Recovery plans need owners, tested procedures, dependencies, and evidence of restore testing.

Remember:

- A snapshot is not automatically a backup.
- Redundancy is not a backup.
- A completed backup job is not proof of a successful restore.
- A redundant component can still be within the same rack, site, zone, or administrative failure domain.

## 7. Failure domains and blast radius

A failure domain is an area that can fail together. It may be a device, host, rack, PDU, switch, shared-storage system, availability zone, region, identity provider, or an application dependency.

Blast radius is the likely scope of impact if that domain fails. Mapping failure domains prevents a misleading design claim such as "dual power means full disaster recovery." Dual power protects certain power failures; it does not protect against every rack, network, storage, application, or site failure.

For each key service, ask:

- What does it depend on?
- Which dependencies are shared?
- Which failure is covered by redundancy, backup, replication, or DR?
- What remains unprotected?
- Who owns the risk and what evidence proves the control works?

Residual risk should be written honestly. An architecture diagram is stronger when it clearly states its limits.

## 8. Monitoring, observability, and alert meaning

Monitoring helps teams observe system behavior. Important signals include:

| Signal | What it can show |
|---|---|
| Metrics | Numeric trends such as CPU use, latency, errors, throughput, temperature, or free capacity |
| Logs | Timestamped records of events and messages |
| Traces | A view of a request as it travels across components, where available |
| Events | State changes, deployments, alerts, or infrastructure actions |
| Dashboard | A visual summary of selected signals |
| Alert | A rule that says a signal crossed a threshold or unusual condition |

A baseline is the normal range or pattern for a service. A threshold is a configured point that triggers an alert. An anomaly is unusual behavior that may not fit a simple threshold.

An alert is a prompt to investigate. It is not a diagnosis. A green dashboard may also be incomplete: it reflects only the signals being collected and shown.

For beginner service thinking, availability, latency, errors, traffic, and saturation are useful categories. They help frame whether a service is reachable, slow, failing, idle, or running out of a resource.

## 9. Alert triage, correlation, and capacity

When an alert arrives:

1. Verify the alert source, timestamp, threshold, environment, target, and current state.
2. Establish scope and user or service impact.
3. Compare the time with approved changes, other alerts, and known dependencies.
4. Collect approved evidence from relevant host, network, storage, facility, or service owners.
5. Record confirmed facts, assumptions, and next owner separately.
6. Decide whether the correct next step is observation, escalation, approved mitigation, or a planned capacity change.

Capacity planning uses trends, peak and sustained use, growth, headroom, and maintenance scenarios. A host can look healthy today but lack spare CPU, memory, storage, or network capacity to evacuate workloads during maintenance.

The junior technician does not need to size a production cluster. She should be able to ask useful questions: What workload moves? Where does it go? Is spare capacity confirmed? Which dependencies are shared? Who validates customer impact? What is the rollback path?

## 10. Cloud concepts and shared responsibility

Cloud terminology differs by provider, but these high-level concepts are useful:

| Term | Plain-language meaning |
|---|---|
| Region | A geographic deployment area containing cloud infrastructure |
| Availability zone | An isolated location or fault domain within a region, as defined by the provider |
| Instance | A virtual compute resource, often similar to a VM |
| Image | A reusable template for creating an instance or system |
| Managed service | A service where the provider operates more of the underlying platform |
| Virtual network | An isolated network construct for cloud resources |
| Security group | A rule set that controls permitted traffic to or from resources in many cloud platforms |
| Load balancer | A component that distributes traffic across service targets |
| Autoscaling | Adding or removing capacity automatically according to policy |

Shared responsibility means the provider and customer each have obligations, but the boundary varies by service model and contract. In a virtual-machine service, the provider may operate the facility and underlying platform while the customer still owns guest operating-system configuration, identities, applications, data, and many network settings. In a managed database or SaaS product, the provider may operate more layers, but the customer can still own data classification, user access, and configuration.

Do not assume that every availability zone is a separate building or that every managed service has the same responsibility split. Consult the approved service documentation.

## 11. Identity, access, audit, and data awareness

Security controls protect infrastructure and provide evidence after the fact:

- Least privilege: give the minimum access needed for the task.
- MFA: require more than one factor for sensitive access.
- Role-based access: assign permissions through roles rather than broad individual grants.
- Time-bound or just-in-time access: limit elevated access duration.
- Segregation of duties: avoid concentrating incompatible approvals and actions in one person.
- Audit trail: retain records of who accessed, changed, or approved something.

For a technician, strong behavior includes confirming the environment, using the approved account or access method, avoiding shared credentials, keeping secrets out of tickets, and ending temporary access when the task completes.

Data awareness matters in public portfolios and internal tickets. Remove customer names, live IP addresses, passwords, private keys, serial numbers, exact facility details, access badges, and restricted photos. GDPR awareness means treating personal data carefully and sharing only what is necessary; it is not a substitute for legal or compliance guidance.

## 12. Junior engineer behavior: dependencies, ownership, and honesty

At the junior-plus level, she can add value without pretending to own every platform:

- Draw the dependency chain before assuming where a fault lives.
- Ask which service, host, storage, network, power path, or failure domain is shared.
- Translate a physical alert into a possible business risk without claiming customer impact until verified.
- State "I can collect this evidence; the platform team owns that change."
- Identify missing validation, capacity, approval, or rollback details before a maintenance task begins.
- Make diagrams, records, and updates simple enough for another person to use.

This behavior is what bridges hands-on data-center work and junior infrastructure engineering.

---

# Part 2: Week 7 questions and model answers

## Virtualization and service dependencies

### 1. What is virtualization?

Virtualization uses software to run multiple isolated guest systems on shared physical resources. It lets one host support several workloads while still depending on real compute, network, storage, power, and cooling.

### 2. What is the difference between a host and a guest?

A host is the physical server or platform providing resources. A guest is a virtual machine using assigned resources from the host or cluster.

### 3. What is a hypervisor?

It is the software layer that creates and runs guest VMs and manages their access to physical resources.

### 4. Is a virtual machine automatically highly available?

No. High availability needs a designed and healthy set of hosts, storage, networks, capacity, and recovery controls.

### 5. What is a cluster?

A group of hosts managed together so workloads and resources can be coordinated. The exact behavior depends on the platform and approved design.

### 6. Why can maintenance on one host affect many services?

One host may run many VMs, and moving them safely may require spare capacity, healthy network and storage paths, and platform-owner approval.

### 7. What is a vNIC?

A virtual network interface presented to a guest VM.

### 8. What is a virtual switch?

Software that connects virtual interfaces and, through host uplinks, connects them to physical network paths.

### 9. What is a datastore?

A storage location used by a virtualization platform for virtual disks and related VM files.

### 10. Why should a technician map a VM path to physical network ports?

It helps identify shared dependencies and ensures that physical work does not unintentionally affect many VMs or management traffic.

### 11. What is the difference between customer traffic and management traffic?

Customer traffic supports the service users consume. Management traffic supports administration, monitoring, or platform control. Both can be important but may have different paths and owners.

### 12. What is resource contention?

It occurs when workloads compete for limited CPU, memory, storage, or network resources, which can cause performance problems even when components appear online.

### 13. What is overcommit?

Allocating more virtual resources than are physically available under an assumption that not all workloads peak at once. It requires careful platform management and is not automatically unsafe or safe.

### 14. What should she ask before host maintenance?

Which workloads are affected, where they will run, whether capacity and dependencies are confirmed, who approved the move, how success is validated, and what happens if migration or maintenance cannot proceed.

## Storage, resilience, and recovery

### 15. What is block storage?

Storage presented as raw blocks or volumes, often used by operating systems, databases, and virtualization platforms.

### 16. What is file storage?

Storage presented as shared files and folders over a network.

### 17. What is object storage?

Storage that keeps data as objects with metadata and API-based access rather than as a normal mounted filesystem.

### 18. What is the difference between SAN and NAS?

A SAN commonly provides shared block storage over a storage network. A NAS provides shared file storage over a network. Their exact technologies and protocols vary.

### 19. What is latency?

The delay between a request and response. High storage latency can slow applications even if capacity is available.

### 20. What is IOPS?

Input/output operations per second, a measure of how many storage operations occur in a period. It is different from latency and throughput.

### 21. Is a snapshot a backup?

Not automatically. A snapshot is usually a point-in-time mechanism and may depend on the same platform or storage. It needs to be assessed as part of a broader recovery design.

### 22. Is redundancy a backup?

No. Redundancy keeps alternate components or paths available; it does not necessarily recover deleted, corrupted, or maliciously changed data.

### 23. What is replication?

Copying data to another system or location. Depending on design, it can also copy bad changes, so it does not replace backup planning.

### 24. What is RPO?

Recovery point objective: the maximum acceptable data loss measured in time.

### 25. What is RTO?

Recovery time objective: the targeted time to restore service after a disruption.

### 26. Why is a successful backup job not enough?

The data and procedure must also be restorable. Restore testing provides evidence that recovery works as intended.

### 27. What is a failure domain?

An area that can fail together, such as a host, rack, PDU, switch, storage system, zone, region, or identity service.

### 28. What is blast radius?

The likely range of service impact when a component or failure domain fails.

## Monitoring, cloud, and security

### 29. What is the difference between a metric and a log?

A metric is a numeric measurement over time. A log is a timestamped record of events or messages. Both can be useful evidence.

### 30. What is a trace?

Where available, a trace follows a request across components and can help identify where delay or error occurs.

### 31. What is a baseline?

The normal range or pattern for a system or service, used to recognize meaningful deviation.

### 32. What is an alert threshold?

A configured point at which a monitoring rule reports a condition. It should be interpreted with scope and context.

### 33. Does an alert prove root cause?

No. It is a signal that needs correlation and investigation.

### 34. What should she record when triaging an alert?

Source, time, threshold, target, environment, current state, scope, user impact, related changes, evidence, owner, and next action.

### 35. What is capacity headroom?

Usable spare capacity that allows for growth, peaks, failures, or maintenance without exhausting a resource.

### 36. Why does maintenance need capacity confirmation?

Moving workloads or failing over paths may concentrate load elsewhere. Without confirmed headroom, a planned task can cause a new problem.

### 37. What is a cloud region?

A geographic deployment area containing cloud infrastructure, as defined by a provider.

### 38. What is an availability zone?

An isolated location or fault domain within a cloud region as defined by the provider. Its exact physical implementation should not be assumed.

### 39. What is shared responsibility?

The split of operational and security responsibilities between customer and provider. It depends on the service model, contract, and configuration.

### 40. What is least privilege?

Giving a person or system only the access needed for the approved task.

### 41. Why use MFA?

It reduces the risk that a stolen password alone can grant access.

### 42. What is an audit trail?

A record of access, approvals, or changes that supports accountability and investigation.

### 43. What should never be included in a public lab portfolio?

Real credentials, private keys, customer data, unapproved screenshots, exact facility information, restricted access details, and other sensitive operational data.

### 44. A managed cloud database is used. Does the customer have no security responsibility?

No. The provider may operate more of the underlying platform, but the customer can still own access, data, configuration, and application responsibilities.

### 45. A single storage service supports many VMs and becomes slow. What is the likely operational concern?

The blast radius may be broad. She should establish scope, collect timestamps and dependency evidence, and escalate to the appropriate storage or platform owner.

### 46. A VM is unreachable but its host appears healthy. What should she avoid assuming?

She should not assume the host is the cause or that the VM is isolated. Virtual networking, guest state, service configuration, dependencies, and policy may need investigation by the correct owners.

### 47. How does physical data center work affect cloud customers?

A physical change can affect shared hosts, network paths, storage, power, cooling, or security controls that underpin virtual or cloud services. Scope, maintenance planning, and validation protect customers.

### 48. What should she say if a cloud or hypervisor change is outside her authority?

She should state the evidence she can collect, identify the owner who can make the change, and request or follow the approved escalation path.

### 49. Why is a dependency map useful during an incident?

It helps identify shared components, likely blast radius, appropriate owners, and the evidence needed before making a change.

### 50. What should she be able to do at the end of Week 7?

Explain a service from physical infrastructure to cloud-facing behavior, identify reliability limits, interpret evidence cautiously, and escalate platform changes responsibly.

---

# Part 3: Lab exercises with hints

## Lab 1: Map a physical-to-service dependency chain

### Goal

Show how a user-facing service relies on virtual and physical infrastructure.

### Steps

1. Draw a fictional service from user request to DNS or load balancer, application VM, virtual network, host, physical switch, storage, rack, power, and cooling.
2. Mark customer traffic and management traffic separately.
3. Add the owner and one safe evidence source for each layer.
4. Identify three components whose failure could affect more than one VM.

### Hints

- Keep the diagram readable; use layers or separate pages if needed.
- Do not claim that every cloud service exposes the same physical path.

### Expected portfolio output

01-physical-to-service-dependency-map.md

## Lab 2: Create a host, guest, and cluster inventory

### Goal

Document a small lab without confusing observed facts and assumptions.

### Steps

1. Use your local host and one or two lab VMs.
2. Record host or VM name, role, virtual CPU, memory, disk, network mode, and whether each item is physical or virtual.
3. Add a fictional cluster column and mark it as an assumption if your lab does not have a cluster.
4. State what a platform owner would need before approving maintenance.

### Hints

- Do not publish real device serials or private network details.

### Expected portfolio output

02-host-guest-and-cluster-inventory.md

## Lab 3: Build a VM resource-allocation worksheet

### Goal

Understand resource contention and maintenance headroom.

### Steps

1. Create a fictional host with a fixed CPU and memory budget.
2. Allocate resources to web, database, monitoring, management, and backup VMs.
3. Add a maintenance scenario where one host is unavailable and workloads need capacity elsewhere.
4. Identify capacity questions and escalation points instead of calculating a production design.

### Hints

- Keep reserved capacity and peak demand separate.
- The goal is to identify risk, not to configure a hypervisor.

### Expected portfolio output

03-vm-resource-allocation-worksheet.md

## Lab 4: Draw a virtual-to-physical network path

### Goal

Connect Week 3 port mapping to a virtual workload.

### Steps

1. Draw VM vNIC to virtual switch or port group to host NIC to physical switch port.
2. Reuse your Week 3 cable and port-map style for the physical portion.
3. Mark which elements a physical technician can verify and which need a network or platform owner.
4. Add one troubleshooting question for each layer.

### Hints

- Do not recreate a VLAN lesson; focus on path ownership and shared dependencies.

### Expected portfolio output

04-virtual-to-physical-network-path.md

## Lab 5: Compare storage services and draw a data path

### Goal

Choose the right vocabulary for storage dependencies.

### Steps

1. Compare local storage, block storage, file storage, and object storage.
2. Add practical use, shared-failure risk, evidence source, and typical owner for each.
3. Draw a simplified VM virtual-disk path to a datastore or volume and storage service.
4. Explain how high latency differs from lack of capacity.

### Hints

- Do not claim a specific product is always SAN, NAS, or object storage; describe the service model.

### Expected portfolio output

05-storage-data-path-and-comparison.md

## Lab 6: Create a data-protection comparison

### Goal

Avoid treating all recovery controls as the same thing.

### Steps

1. Use three events: deleted file, host failure, and site loss.
2. For each, decide whether snapshot, backup, replication, redundancy, HA, or DR is relevant.
3. State what the selected mechanism does not protect against.
4. Add the evidence required to claim that recovery is possible.

### Hints

- A restore test is stronger evidence than a successful backup-job message alone.

### Expected portfolio output

06-data-protection-comparison.md

## Lab 7: Set fictional RPO and RTO objectives

### Goal

Connect recovery targets to service importance.

### Steps

1. Choose three fictional services: monitoring, internal web application, and finance database.
2. Propose an RPO and RTO for each as a planning exercise.
3. Explain the business question that would validate each target.
4. List the owner, recovery dependency, and validation method.

### Hints

- Label targets as assumptions, not guarantees.

### Expected portfolio output

07-rpo-rto-recovery-objectives.md

## Lab 8: Build an HA and failure-domain map

### Goal

Identify protection and residual risk honestly.

### Steps

1. Map hosts, rack, PDU feeds, switches, storage, availability zone, region, and identity service.
2. Show which services share each component.
3. Mark a single point of failure or residual risk for at least five components.
4. Add an owner and recommended next improvement for each risk.

### Hints

- A redundant PSU does not eliminate a shared rack or site failure domain.

### Expected portfolio output

08-ha-and-failure-domain-map.md

## Lab 9: Collect a monitoring baseline and threshold note

### Goal

Learn to interpret trends rather than one isolated number.

### Steps

1. Reuse safe read-only checks from Week 4 on a lab VM at three different times.
2. Record CPU, memory, disk, and network activity in a simple table.
3. Describe a normal pattern and a condition worth investigating.
4. Explain why a threshold needs service context.

### Hints

- This is not a request to tune production monitoring.

### Expected portfolio output

09-monitoring-baseline-and-threshold-note.md

## Lab 10: Complete an alert-triage and correlation worksheet

### Goal

Practise turning an alert into a bounded investigation.

### Scenario

At 15:00, a datastore-latency alert fires. Two application VMs are slow, one VM on another datastore is normal, and no customer-impact report has yet been confirmed.

### Steps

1. Record alert metadata, scope, confirmed facts, assumptions, and affected dependencies.
2. List safe evidence requests for platform, storage, and application owners.
3. State what cannot yet be claimed.
4. Write a concise escalation or status update.

### Hints

- Slow VMs and a latency alert are correlated, not automatically proof of root cause.

### Expected portfolio output

10-alert-triage-and-correlation-worksheet.md

## Lab 11: Write a capacity and maintenance-impact note

### Goal

Identify questions before a host maintenance task begins.

### Scenario

A virtualization host needs planned maintenance. Its active VMs must continue to run elsewhere.

### Steps

1. List affected workloads, dependencies, potential destination capacity, approvals, and validation owner.
2. Add stop conditions for missing capacity, unknown workloads, unknown data paths, or absent rollback ownership.
3. State what a data center technician can verify physically.
4. State which decisions belong to the platform team.

### Hints

- Do not assume live migration is available or approved.

### Expected portfolio output

11-capacity-and-maintenance-impact-note.md

## Lab 12: Create a cloud shared-responsibility map

### Goal

Explain responsibility boundaries without oversimplifying them.

### Steps

1. Compare a virtual-machine service, managed database, and SaaS application.
2. For each, mark likely provider and customer responsibilities for facility, host platform, operating system, application, identity, configuration, and data.
3. Add a note that the contract and service documentation are authoritative.
4. Identify one risk caused by assuming the provider owns everything.

### Hints

- "Likely" is deliberate: responsibility varies by provider and service.

### Expected portfolio output

12-cloud-shared-responsibility-map.md

## Lab 13: Build an access and audit evidence checklist

### Goal

Apply security principles to an infrastructure task.

### Steps

1. Create checks for authorization, correct environment, correct role, MFA, time-bounded access, audit evidence, and access removal.
2. Add rules for avoiding passwords, private keys, personal data, and restricted screenshots in tickets or portfolios.
3. Include an escalation rule for access that is too broad or does not match the task.
4. Explain why shared accounts weaken accountability.

### Hints

- This is an operational checklist, not legal advice or a complete security policy.

### Expected portfolio output

13-access-and-audit-evidence-checklist.md

## Lab 14: Run a cross-layer incident simulation

### Goal

Use dependency thinking during an ambiguous incident.

### Scenario

Several VMs on one host report slow response. A storage-latency alert appears, the host network link remains up, and a recent platform maintenance activity is listed in the change calendar.

### Steps

1. Establish scope, customer impact, and known shared dependencies.
2. Build a timestamped fact and hypothesis log.
3. Write evidence requests for platform, storage, network, and service owners.
4. State what a physical technician can verify and what she must not change.
5. Write a status update and a clear escalation packet.

### Hints

- A host link being up does not rule out storage, virtual networking, guest, or application issues.

### Expected portfolio output

14-cross-layer-incident-simulation.md

## Lab 15: Build a Week 7 mock interview script

### Goal

Prepare plain-language answers that show dependency awareness.

### Steps

Write 45-90 second answers for:

1. What is virtualization?
2. What is the difference between a host and a guest VM?
3. What is the difference between backup, redundancy, replication, and high availability?
4. What are RPO and RTO?
5. What is a failure domain?
6. How can a physical task affect cloud customers?
7. How would you respond to an alert affecting several VMs?
8. What does shared responsibility mean?
9. Why are least privilege and MFA important?
10. What would you do if a cloud-platform change was outside your authority?

### Expected portfolio output

15-week-07-interview-script.md

## Lab 16: Final Week 7 self-assessment

### Goal

Check whether the learner can connect physical work to service reliability.

### Self-assessment table

| Skill | Can do without notes | Can do with notes | Need more practice |
|---|---|---|---|
| Explain a user-to-infrastructure dependency chain | | | |
| Distinguish host, guest, hypervisor, cluster, and vNIC | | | |
| Map a virtual network path to physical infrastructure | | | |
| Compare local, block, file, and object storage | | | |
| Explain snapshot, backup, replication, redundancy, HA, and DR | | | |
| Explain RPO and RTO as recovery objectives | | | |
| Identify failure domains and blast radius | | | |
| Interpret metrics, logs, traces, alerts, and baselines | | | |
| Identify capacity and maintenance questions | | | |
| Explain cloud region, availability zone, and shared responsibility | | | |
| Apply least privilege, MFA, and audit evidence | | | |
| Escalate a cross-layer issue without guessing a root cause | | | |

### Expected portfolio output

16-week-07-self-assessment.md

---

# Part 4: Templates to copy into the portfolio

## Service dependency map template

| Service | Customer entry point | VM or platform | Host or cluster | Virtual/physical network | Storage dependency | Rack/facility dependency | Owner | Safe evidence source |
|---|---|---|---|---|---|---|---|---|
| | | | | | | | | |

## Resilience and recovery matrix

| Service or component | Failure considered | Control | What it protects | What it does not protect | RPO | RTO | Test evidence | Residual risk |
|---|---|---|---|---|---|---|---|---|
| | | Backup / HA / Redundancy / Replication / DR | | | | | | |

## Alert triage and correlation worksheet

    # Alert Triage

    Alert source:
    Time and time zone:
    Environment:
    Target:
    Threshold or condition:
    Current state:
    Confirmed customer or service impact:
    Affected scope:
    Related change or event:

    ## Evidence by dependency layer

    ## Confirmed facts

    ## Assumptions and hypotheses

    ## Current owner and escalation request

    ## Next update and no-change statement

## Capacity and maintenance-impact check

    # Capacity and Maintenance Impact Check

    Requested work:
    Affected host, service, or component:
    Workloads and dependencies:
    Confirmed spare capacity:
    Change and decision owner:
    Service validation owner:
    Rollback owner:

    Stop and escalate if:
    - Workload placement is unknown.
    - Capacity is not confirmed.
    - Shared storage or network impact is unclear.
    - Approval, validation, or rollback owner is absent.

## Shared responsibility and access matrix

| Service model | Provider likely owns | Customer likely owns | Required access role | Approval source | Audit evidence | Data-handling note |
|---|---|---|---|---|---|---|
| VM service | | | | | | |
| Managed database | | | | | | |
| SaaS application | | | | | | |

---

# Part 5: Week 7 final exam

## Written exam

Answer these without looking at notes:

1. Explain how a user-facing service depends on physical data-center infrastructure.
2. Explain host, guest, hypervisor, cluster, vNIC, virtual switch, and datastore.
3. Explain why a VM is not automatically highly available.
4. Compare local, block, file, and object storage.
5. Explain latency, throughput, capacity, and IOPS.
6. Explain snapshot, backup, replication, redundancy, high availability, and disaster recovery.
7. Explain RPO and RTO.
8. Identify five possible failure domains in a virtualized service.
9. Explain metrics, logs, traces, alerts, thresholds, and baselines.
10. Explain why capacity matters before host maintenance.
11. Explain region, availability zone, instance, and shared responsibility.
12. Explain least privilege, MFA, and audit trail.
13. Explain what information must be removed from a public lab portfolio.

## Practical exam

Complete these tasks using a fictional service:

1. Draw the service dependency map from user to rack and facility.
2. Create a host/guest inventory and virtual-to-physical network path.
3. Compare storage and data-protection controls for three failure scenarios.
4. Identify failure domains, blast radius, and residual risks.
5. Triage a datastore-latency alert affecting several VMs without claiming a root cause.
6. Write an escalation update that identifies scope, evidence, ownership, and next action.
7. Explain a shared-responsibility and access-control map aloud.

## Passing standard

She passes Week 7 if she can:

- Explain the physical and virtual dependencies behind a service.
- Use correct storage, recovery, availability, and monitoring vocabulary.
- Identify the limits of redundancy and the likely blast radius of shared components.
- Ask useful capacity and maintenance-impact questions.
- Interpret an alert as evidence rather than a diagnosis.
- Explain cloud responsibility boundaries without overclaiming.
- Protect access, audit, and confidentiality boundaries.
- Escalate platform or cloud changes to the correct owner.

---

# Part 6: Interview positioning for Week 7

Week 7 lets her speak about infrastructure as a service chain rather than as isolated hardware. She should say "in my lab and documentation exercises" for work she has not performed in a production cloud or virtualization platform.

## Strong interview themes

- I understand that cloud services still depend on physical compute, network, storage, power, cooling, and operations.
- I can explain a host, hypervisor, guest VM, virtual network, and shared datastore at a junior level.
- I separate backup, redundancy, replication, high availability, and disaster recovery.
- I think about failure domains and customer impact before a physical or maintenance change.
- I use monitoring to establish scope and evidence, not to guess root cause.
- I understand that access and configuration responsibility varies with the service model.
- I know when to collect evidence and when to escalate a change to platform, storage, cloud, security, or application owners.

## Example answer: virtualization for a data center technician

"Virtualization allows multiple guest VMs to run on shared physical hosts. From a data center perspective, that means one physical server, network uplink, storage path, or power issue can affect several services. Before I make physical changes, I would confirm the host, workloads, maintenance plan, dependency impact, validation owner, and rollback path. I would collect approved evidence and escalate platform changes to the correct team."

## Example answer: backup versus redundancy

"Redundancy keeps an alternate component or path available, such as dual power feeds or multiple hosts. Backup is an independent recoverable copy of data. Replication copies data to another location, and high availability aims to reduce interruption after planned failure conditions. They can work together, but none of them automatically protects every failure. I would ask what failure is covered and what recovery evidence has been tested."

## Example answer: multiple VMs are slow

"I would establish whether the VMs share a host, datastore, network path, application dependency, or recent change. I would record alert times, scope, customer impact, and safe evidence from the relevant owners. I would not declare the storage alert or the host as root cause without evidence. My update would separate confirmed facts from hypotheses and request the specific platform or storage review needed."

---

# Part 7: Week 7 completion checklist

- [ ] I created a Week 7 portfolio folder.
- [ ] I built a physical-to-service dependency map.
- [ ] I created a host, guest, and cluster inventory.
- [ ] I created a VM resource-allocation worksheet.
- [ ] I mapped a virtual network path to physical infrastructure.
- [ ] I compared local, block, file, and object storage.
- [ ] I compared snapshot, backup, replication, redundancy, HA, and DR.
- [ ] I set fictional RPO and RTO objectives with assumptions stated.
- [ ] I created an HA and failure-domain map with residual risks.
- [ ] I collected a monitoring baseline and explained threshold context.
- [ ] I completed an alert-triage and correlation worksheet.
- [ ] I wrote a capacity and maintenance-impact note.
- [ ] I created a cloud shared-responsibility map.
- [ ] I created an access and audit evidence checklist.
- [ ] I completed a cross-layer incident simulation.
- [ ] I completed the Week 7 mock interview script.
- [ ] I completed the Week 7 final exam and self-assessment.
- [ ] I can explain when to collect evidence and when to escalate.
