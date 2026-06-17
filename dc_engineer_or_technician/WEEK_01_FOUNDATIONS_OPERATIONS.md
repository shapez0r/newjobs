# Week 1 Detailed Workbook: IT Foundations, Safety, and Professional Operations

## Purpose of this workbook

This workbook expands **Week 1** of the Data Center Engineer / Data Center Technician study plan. It is written for a complete beginner and is designed to build the professional foundation expected from a strong junior candidate in a competitive Dublin job market.

By the end of this week, she should sound like someone who understands the seriousness of production infrastructure work: safety first, no guessing, precise documentation, clear communication, and disciplined ticket handling.

## Week 1 target level

The target is not “I watched a video about data centers.” The target is:

- She can explain what a data center does in plain English.
- She can describe the main physical and operational areas of a data center.
- She understands the difference between a technician, engineer, NOC, remote-hands, facilities, security, and customer roles.
- She can explain why safety, access control, and change management matter.
- She can write professional ticket updates and handover notes.
- She can identify when to stop and escalate instead of guessing.
- She can show a Week 1 portfolio with diagrams, templates, notes, and mock tickets.

## Suggested weekly schedule

| Day | Focus | Main output |
|---|---|---|
| Day 1 | What data centers do and how they are organized | Data center concept map and glossary |
| Day 2 | Roles, responsibilities, and operational culture | Responsibility matrix and “stop/escalate” rules |
| Day 3 | Safety, physical security, and access control | Safety checklist and access-control scenario answers |
| Day 4 | Ticketing, documentation, and change management | Ticket examples, change template, handover note |
| Day 5 | Communication, incident mindset, and review | Mock interview answers and final Week 1 portfolio |
| Day 6 optional | Revision and mock interview | Recorded 10-minute explanation |
| Day 7 optional | Rest or catch-up | Improve weak areas |

## Required Week 1 portfolio artifacts

Create a folder called `week-01-operations-basics` and include:

```text
week-01-operations-basics/
  README.md
  01-data-center-concept-map.png or .drawio
  02-glossary.md
  03-role-responsibility-matrix.md
  04-safety-checklist.md
  05-access-control-scenarios.md
  06-ticket-updates.md
  07-change-request-template.md
  08-handover-note.md
  09-escalation-examples.md
  10-week-01-self-assessment.md
```

---

# Part 1: Comprehensive Week 1 topics

## 1. What a data center is

A **data center** is a secure facility that houses computing equipment such as servers, storage systems, network devices, power systems, cooling systems, and security controls. Its purpose is to keep digital services running reliably.

She should understand that modern services depend on physical infrastructure. Cloud services still run on servers, network switches, storage, cables, power, and cooling inside data centers.

### Key points to learn

- A data center supports applications, websites, databases, internal systems, and cloud platforms.
- It must provide availability, security, physical protection, power, cooling, and connectivity.
- Downtime can affect customers, revenue, reputation, and legal/compliance obligations.
- Data center technicians protect production systems by following procedures exactly.

### Must-know vocabulary

- Server
- Rack
- Rack unit / U
- Switch
- Router
- Firewall
- Patch panel
- Storage
- Power distribution unit / PDU
- UPS
- Generator
- Cooling
- Hot aisle
- Cold aisle
- Cage
- Cabinet
- Meet-me room
- NOC
- Remote hands
- Smart hands
- Asset tag
- Serial number
- Change window
- Incident
- Service request
- SLA

## 2. Main data center building blocks

### Compute

Compute is the processing layer: physical servers, blade servers, hypervisors, and virtual machines. Even if she is not administering the operating systems yet, she must know that compute runs applications and workloads.

### Storage

Storage holds data. It may be local server disks, SAN, NAS, object storage, backup storage, or storage arrays.

### Network

Network connects servers to each other, to storage, to the internet, and to customer environments. It includes switches, routers, firewalls, load balancers, cables, optics, patch panels, and network diagrams.

### Power

Power keeps the equipment running. Data centers use utility power, UPS systems, generators, PDUs, A/B feeds, and redundant power supplies.

### Cooling

Servers produce heat. Cooling systems, airflow design, hot/cold aisles, blanking panels, humidity control, and temperature monitoring prevent overheating.

### Physical security

Physical security protects systems and data from unauthorized access. It includes badges, mantraps, CCTV, visitor logs, cages, locked cabinets, escort rules, and access reviews.

## 3. Types of data centers

### Enterprise data center

Owned and operated by one company for its own systems.

### Colocation data center

A facility where many customers rent rack space, power, cooling, and connectivity. Technicians may perform remote-hands tasks for customers.

### Hyperscale data center

Very large-scale data center used by major cloud/platform companies. Processes are usually highly standardized.

### Edge data center

Smaller facility closer to users or devices, often used for low latency.

### Cloud data center

The physical infrastructure behind cloud services such as AWS, Azure, or Google Cloud.

## 4. Areas inside a data center

She should know these conceptually:

- Reception/security desk
- Mantrap or controlled access point
- Data halls
- Customer cages
- Server rows
- Hot aisles and cold aisles
- Network rooms
- Meet-me rooms
- Storage rooms
- Loading dock
- Staging/build area
- Spares room
- NOC or operations area
- Facilities/electrical rooms
- Fire suppression zones

## 5. Common data center roles

### Data Center Technician

Performs physical tasks such as rack/stack, cabling, hardware replacement, visual checks, asset updates, escorting, and remote-hands instructions.

### Data Center Engineer

Usually has deeper troubleshooting ability, may plan changes, coordinate technical tasks, analyze recurring issues, and support infrastructure improvements.

### NOC Engineer

Monitors alerts, tracks incidents, escalates issues, communicates with teams, and may coordinate incident response.

### Remote Hands / Smart Hands

Performs physical tasks on behalf of customers or remote engineers. Smart hands may require more technical judgment, while remote hands may be very instruction-driven.

### Facilities Engineer

Maintains power, cooling, generators, UPS, fire suppression, and building infrastructure.

### Network Engineer

Designs, configures, and troubleshoots network devices. A technician may connect cables but normally should not change switch configuration unless authorized.

### Security Officer

Controls access, verifies identity, monitors physical security, enforces visitor and escort policies.

### Customer / Remote Engineer

May request work through tickets and rely on the data center technician to provide accurate physical observations and evidence.

## 6. Professional mindset for data center work

The most important Week 1 lesson: **do not guess in production**.

Strong technicians are trusted because they are careful, predictable, and honest. If something is unclear, unsafe, undocumented, or different from the ticket, stop and escalate.

### Core principles

- Safety first.
- Follow the ticket, SOP, MOP, or runbook.
- Verify identity and authorization.
- Confirm asset, rack, U position, cable label, serial number, and port before touching anything.
- Change one thing at a time when troubleshooting.
- Record timestamps and evidence.
- Communicate early if blocked.
- Never hide mistakes.
- Do not improvise on production equipment.

## 7. Safety fundamentals

### Electrical safety

- Do not open power equipment unless trained and authorized.
- Be aware of high-voltage areas.
- Do not overload power strips or PDUs.
- Report damaged cables, burning smell, sparks, water, or unusual heat immediately.

### ESD safety

Electrostatic discharge can damage components. Learn:

- Use anti-static bags.
- Use ESD wrist straps where required.
- Avoid touching contacts and chips.
- Handle cards and RAM by edges.
- Keep components in proper packaging.

### Manual handling

- Servers are heavy.
- Use team lifting when required.
- Use proper posture.
- Do not rush.
- Use server lifts if available.
- Do not work alone on heavy rack equipment if policy requires assistance.

### Cable safety

- Avoid trip hazards.
- Do not block aisles.
- Do not pull cables aggressively.
- Never disconnect a cable unless the exact cable is verified.
- Keep cabling tidy for airflow and maintenance.

### Fiber safety

- Never look into fiber ends or optics.
- Keep dust caps on unused optics/fiber.
- Clean fiber connectors properly if trained.
- Treat fiber as delicate and easy to damage.

### Environmental safety

- Hot aisles can be uncomfortable.
- Noise levels may require hearing protection.
- Know emergency exits.
- Know fire alarm procedure.
- Keep liquids away from equipment.

## 8. Physical security and access control

Data centers are secure environments because physical access can mean access to customer systems and data.

### Key rules

- Wear badge visibly if policy requires it.
- Do not tailgate or allow tailgating.
- Do not lend badges.
- Escort visitors if required.
- Challenge unknown people according to procedure.
- Do not photograph equipment unless authorized.
- Do not discuss customer details outside approved channels.
- Lock cabinets/cages after work.
- Record entry/exit when required.

### Access-control mindset

If she is unsure whether someone is allowed in an area, she should politely stop and verify with security or a supervisor.

## 9. Ticketing fundamentals

Data center work is driven by tickets. Tickets provide authorization, instructions, scope, audit trail, and communication history.

### Ticket types

- **Incident:** Something is broken or degraded.
- **Service request:** A standard request, such as escort, visual check, cable trace, or install.
- **Change:** Planned modification to production infrastructure.
- **Problem:** Investigation into recurring or root causes.

### Good ticket update qualities

- Clear
- Short but complete
- Timestamped
- Fact-based
- Includes actions taken
- Includes current status
- Includes blockers or risks
- Includes next step
- Avoids blame and vague language

### Bad ticket update example

```text
Checked server. Still not working.
```

### Better ticket update example

```text
21:14 - At rack D12, confirmed asset tag SRV-1842 and hostname label app-dub-01. Server has power on PSU1 and PSU2, front panel amber disk LED visible on bay 3. Network link LEDs active on NIC1 and NIC2. No physical changes made. Awaiting approval from remote engineer before disk replacement.
```

## 10. Change management basics

Change management reduces risk when modifying production systems.

### Typical change request fields

- Change title
- Business reason
- Systems/assets affected
- Risk level
- Implementation steps
- Validation steps
- Rollback plan
- Maintenance window
- Approver
- Communication plan

### Beginner rule

If the task changes production state, it probably needs authorization, a ticket, a change, or supervisor confirmation.

## 11. Documentation basics

Documentation is not paperwork for its own sake. It protects people, equipment, customers, and the company.

### Common documentation items

- Asset inventory
- Rack elevation
- Cable map
- Patch panel map
- Power feed map
- Ticket notes
- Incident timeline
- Handover note
- Photo evidence if allowed
- Serial number/service tag record
- Change record

### Documentation quality bar

Someone else should be able to continue the task from her notes without asking basic questions.

## 12. Communication and escalation

Technical skill is not enough. Data center staff must communicate clearly, especially under pressure.

### Good communication structure

Use this format:

```text
Status: What is happening now?
Impact: What is affected?
Action: What have I done?
Blocker/Risk: What prevents progress?
Next step: What will happen next and when?
```

### Escalate when

- The instruction is unclear.
- The asset label does not match the ticket.
- The rack/U position does not match the ticket.
- A cable label is missing or ambiguous.
- There is a safety concern.
- There is possible customer impact not mentioned in the ticket.
- The task requires permissions she does not have.
- The actual situation differs from the documented plan.
- She made a mistake or suspects a mistake.

---

# Part 2: Week 1 questions and model answers

Use these as flashcards and mock interview practice. She should answer aloud first, then compare with the model answer.

## Data center fundamentals

### 1. What is a data center?

**Answer:** A data center is a secure facility that houses servers, storage, networking, power, cooling, and security systems so digital services can run reliably. It supports applications, websites, databases, cloud platforms, and business systems.

### 2. Why do companies use data centers?

**Answer:** Companies use data centers to keep IT systems available, secure, connected, powered, and cooled. A proper data center provides reliability, physical security, redundancy, monitoring, and operational processes that are hard to achieve in a normal office environment.

### 3. What are the main technical building blocks of a data center?

**Answer:** The main building blocks are compute, storage, networking, power, cooling, and physical security. Compute runs workloads, storage keeps data, networking connects systems, power keeps equipment running, cooling removes heat, and security controls access.

### 4. What is compute in a data center?

**Answer:** Compute means the processing resources that run applications and services. In a data center this usually means physical servers, virtual machines, or container platforms running on server hardware.

### 5. What is storage in a data center?

**Answer:** Storage is the infrastructure used to keep data. It can include disks inside servers, storage arrays, SAN, NAS, object storage, and backup systems.

### 6. What is networking in a data center?

**Answer:** Networking connects servers, storage, customers, and the internet. It includes switches, routers, firewalls, load balancers, patch panels, copper cables, fiber cables, and optics.

### 7. Why are power and cooling so important?

**Answer:** Servers need continuous power and generate heat. If power fails, systems may go down. If cooling fails, equipment can overheat, throttle, shut down, or become damaged.

### 8. What is a rack?

**Answer:** A rack is a standardized metal frame or cabinet used to mount servers, switches, patch panels, and other equipment. Equipment height is measured in rack units, or U.

### 9. What is a rack unit?

**Answer:** A rack unit, written as 1U, is a standard height measurement for rack-mounted equipment. 1U is 1.75 inches or about 44.45 mm.

### 10. What is a data hall?

**Answer:** A data hall is the main area inside a data center where rows of racks, servers, networking equipment, and cabling are installed.

### 11. What is a hot aisle and cold aisle?

**Answer:** A cold aisle supplies cool air to the front of servers. A hot aisle collects hot exhaust air from the back of servers. Separating hot and cold air improves cooling efficiency and reduces overheating risk.

### 12. What is a meet-me room?

**Answer:** A meet-me room is a controlled area where different network providers and customers interconnect. It is common in colocation data centers.

### 13. What is a colocation data center?

**Answer:** A colocation data center rents space, power, cooling, and connectivity to multiple customers. Customers may own their own equipment while the facility provides secure hosting and operational support.

### 14. What is a hyperscale data center?

**Answer:** A hyperscale data center is a very large facility used by cloud or platform companies to run massive amounts of infrastructure with high standardization and automation.

### 15. Does cloud computing remove the need for data centers?

**Answer:** No. Cloud computing still depends on physical data centers. Cloud users do not manage the hardware directly, but cloud providers still operate servers, storage, networking, power, and cooling.

## Roles and responsibilities

### 16. What does a Data Center Technician do?

**Answer:** A Data Center Technician performs physical infrastructure tasks such as racking equipment, cabling, checking LEDs, replacing hardware, updating tickets, escorting visitors, recording assets, and following remote-hands instructions.

### 17. What is the difference between a technician and an engineer?

**Answer:** Titles vary by company, but a technician often focuses on hands-on operational tasks, while an engineer may handle deeper troubleshooting, planning, process improvement, technical coordination, and more complex changes.

### 18. What is remote hands?

**Answer:** Remote hands means a data center technician performs physical tasks on behalf of someone who is not on site, such as checking cable connections, reading serial numbers, power cycling equipment if authorized, or taking approved photos.

### 19. What is smart hands?

**Answer:** Smart hands is similar to remote hands but may require more technical skill or judgment, such as console checks, structured troubleshooting, hardware replacement, or guided diagnostics.

### 20. What does a NOC do?

**Answer:** A Network Operations Center monitors systems and alerts, tracks incidents, coordinates communication, escalates issues, and helps maintain service availability.

### 21. What does a facilities engineer do?

**Answer:** A facilities engineer maintains building infrastructure such as power, UPS, generators, cooling, fire suppression, and environmental systems.

### 22. What does a network engineer do?

**Answer:** A network engineer designs, configures, and troubleshoots network infrastructure such as switches, routers, firewalls, VLANs, routing, and connectivity.

### 23. Should a data center technician change network switch configuration without approval?

**Answer:** No. Configuration changes can affect production systems. A technician should only make changes if authorized, trained, and following an approved procedure.

### 24. Why is teamwork important in data centers?

**Answer:** Data center work often involves technicians, network engineers, facilities, security, customers, and management. Good teamwork reduces mistakes, improves safety, and speeds incident resolution.

### 25. What makes a junior candidate stand out?

**Answer:** A strong junior candidate is careful, honest, eager to learn, good at documentation, calm under pressure, safety-aware, and able to explain basic infrastructure and troubleshooting clearly.

## Safety

### 26. What is the first priority in a data center?

**Answer:** Safety is the first priority: personal safety, team safety, customer equipment safety, and facility safety.

### 27. What is ESD?

**Answer:** ESD means electrostatic discharge. It is a sudden flow of static electricity that can damage electronic components such as RAM, CPUs, drives, and circuit boards.

### 28. How can ESD risk be reduced?

**Answer:** Use ESD wrist straps or mats where required, keep components in anti-static bags, handle parts by the edges, avoid touching contacts, and follow the facility procedure.

### 29. Why is manual handling important?

**Answer:** Servers can be heavy and awkward. Poor lifting can injure people or damage equipment. Use team lifting, server lifts, and proper posture according to policy.

### 30. What should she do if she smells burning near a rack?

**Answer:** Stop work immediately, move to a safe position if needed, do not touch suspicious equipment, report to the supervisor/NOC/facilities/security according to procedure, and document the observation.

### 31. What should she do if she sees water near equipment?

**Answer:** Stop work, avoid stepping into or touching water near electrical equipment, alert facilities/security/NOC immediately, and follow emergency procedures.

### 32. Why should she not look into fiber cables or optics?

**Answer:** Fiber links can use laser light that may be invisible and harmful to eyes. Never look into fiber ends or transceivers.

### 33. Why is cable management a safety issue?

**Answer:** Poor cable management can create trip hazards, block airflow, make troubleshooting harder, and increase the risk of disconnecting the wrong cable.

### 34. What should she do before removing a cable?

**Answer:** Verify the ticket, asset, rack, port, cable label, source and destination, and approval. If anything is unclear, stop and escalate.

### 35. Why are liquids usually prohibited near equipment?

**Answer:** Liquids can cause electrical hazards, short circuits, equipment damage, downtime, and safety incidents.

### 36. What is a hot aisle?

**Answer:** A hot aisle is the aisle where the rear of servers exhausts hot air. It may be warmer and requires awareness of comfort, airflow, and cooling design.

### 37. What is a cold aisle?

**Answer:** A cold aisle is the aisle where server fronts receive cool air. Cold aisles are part of airflow management to keep equipment within safe temperatures.

### 38. What should she do if a task feels unsafe?

**Answer:** Stop the task and escalate to a supervisor or appropriate team. A good technician never continues unsafe work just to close a ticket quickly.

### 39. Why should heavy equipment not be installed alone?

**Answer:** Heavy equipment can injure the technician, damage rails, fall, or damage other equipment. Follow policy for team lifts or server lifts.

### 40. What is good housekeeping in a data center?

**Answer:** Keeping aisles clear, removing packaging, organizing tools, avoiding loose cables, closing cabinet doors, and leaving the work area clean and safe.

## Physical security and access control

### 41. Why is physical security critical in a data center?

**Answer:** Physical access can allow someone to disconnect systems, steal equipment, access data, or cause outages. Strong physical security protects customers and the business.

### 42. What is tailgating?

**Answer:** Tailgating is when someone enters a secure area by following another person without proper authentication.

### 43. What should she do if someone tries to tailgate?

**Answer:** Politely follow the site procedure: do not allow unauthorized entry, ask them to badge in, and involve security if needed.

### 44. Should she lend her access badge to a colleague?

**Answer:** No. Badges are individual credentials. Lending a badge breaks security policy and audit controls.

### 45. Can she take photos inside a data center?

**Answer:** Only if explicitly authorized by policy or ticket. Photos may reveal customer equipment, labels, security controls, or sensitive information.

### 46. What is an escort requirement?

**Answer:** Some visitors or contractors must be accompanied by authorized staff at all times inside secure areas.

### 47. What should she do if a visitor wants access to a restricted area but is not on the approved list?

**Answer:** Do not grant access. Verify with security or a supervisor and follow the site access procedure.

### 48. Why are access logs important?

**Answer:** Access logs provide an audit trail of who entered secure areas and when. They help with security investigations and compliance.

### 49. Why should customer information be protected?

**Answer:** Data centers may host sensitive customer systems. Sharing customer names, rack locations, photos, or incident details outside approved channels can violate security and confidentiality obligations.

### 50. What is least privilege?

**Answer:** Least privilege means people should only have the access needed to perform their job, and no more.

## Ticketing, changes, and documentation

### 51. What is a ticket?

**Answer:** A ticket is a formal record of a request, incident, task, or change. It provides authorization, instructions, communication history, and an audit trail.

### 52. What is an incident?

**Answer:** An incident is an unplanned interruption or degradation of service, such as a server down, link down, failed disk, or power alert.

### 53. What is a service request?

**Answer:** A service request is a standard user/customer request, such as checking a serial number, escorting a visitor, installing equipment, or tracing a cable.

### 54. What is a change?

**Answer:** A change is a planned modification to a system or environment. It usually requires risk assessment, approval, implementation steps, validation, and rollback plan.

### 55. What is a problem record?

**Answer:** A problem record tracks investigation into the root cause of recurring or significant incidents.

### 56. What is an SLA?

**Answer:** An SLA, or Service Level Agreement, is a commitment about service expectations such as response time, resolution time, or availability.

### 57. What makes a good ticket update?

**Answer:** A good ticket update is factual, timestamped, clear, concise, and includes what was checked, what was found, what was changed, current status, blockers, and next steps.

### 58. What should she do if a ticket lacks key information?

**Answer:** She should not guess. She should ask for clarification and document what information is missing, such as rack, U position, asset tag, serial number, cable label, or approval.

### 59. What should she verify before touching equipment?

**Answer:** Ticket number, authorization, asset tag, hostname/label, rack, U position, serial/service tag, port/cable label, task scope, risk, and rollback/next step if applicable.

### 60. What is a handover note?

**Answer:** A handover note summarizes task status for the next person or shift. It should include context, actions completed, current state, blockers, risks, and next steps.

### 61. Why are timestamps important?

**Answer:** Timestamps create an accurate timeline for troubleshooting, SLA tracking, accountability, and incident review.

### 62. What is a rollback plan?

**Answer:** A rollback plan explains how to return the environment to its previous safe state if a change fails.

### 63. What is validation in a change?

**Answer:** Validation confirms the change achieved the expected result and did not cause unexpected issues. It can include link checks, health checks, logs, monitoring, or customer confirmation.

### 64. Why should she avoid vague words like “fixed” or “checked” without detail?

**Answer:** Vague updates do not tell others what happened. Detailed factual notes help other engineers continue work and support audits or incident reviews.

### 65. What is an asset inventory?

**Answer:** An asset inventory records equipment details such as hostname, asset tag, serial number, rack location, model, owner, power feeds, network ports, and status.

## Communication and professionalism

### 66. How should she communicate when blocked?

**Answer:** She should quickly explain the blocker, what she has already checked, the risk, and exactly what help or clarification she needs.

### 67. What should she do if she makes a mistake?

**Answer:** Stop, make the situation safe, notify the appropriate person immediately, document facts honestly, help recover, and participate in learning from the incident. Hiding mistakes is much worse.

### 68. What should she say if she does not know something in an interview?

**Answer:** She should be honest and explain how she would find out safely. Example: “I have not done that yet, but I would check the runbook, confirm authorization, ask a senior technician, and document each step.”

### 69. How should she handle urgent work under pressure?

**Answer:** Stay calm, follow procedure, verify before acting, communicate status, escalate when needed, and avoid rushing into risky actions.

### 70. What is a good way to structure an update?

**Answer:** Use: Status, impact, actions taken, blocker/risk, next step, ETA.

### 71. What is the STAR interview method?

**Answer:** STAR means Situation, Task, Action, Result. It is a structured way to answer behavioral interview questions with a clear story.

### 72. Why is reliability a professional trait in data center work?

**Answer:** Data center teams need people who arrive on time, follow process, document work, and can be trusted around critical infrastructure.

### 73. How can a newbie show value without job experience?

**Answer:** By building a portfolio: diagrams, mock tickets, safety checklists, runbooks, labs, screenshots, notes, and clear explanations of what she learned.

### 74. What does “do not guess in production” mean?

**Answer:** It means she should never take unauthorized or uncertain actions on live equipment. If unsure, she must stop, verify, ask, and document.

### 75. Why is closing the ticket not the only goal?

**Answer:** The goal is safe, correct, documented work. Closing a ticket quickly but incorrectly can cause outages, security issues, or repeated work.

## Scenario questions

### 76. The ticket says rack R12 U18, but the label on the server says a different hostname. What should she do?

**Answer:** Stop and do not touch the server. Document the mismatch, verify asset tag/serial/rack/U, ask for clarification, and wait for confirmation before proceeding.

### 77. A remote engineer asks her to power cycle a server, but there is no approval in the ticket. What should she do?

**Answer:** She should not power cycle it yet. Power cycling can cause outage or data loss. She should request written approval in the ticket and follow the approved process.

### 78. She notices a loose cable near the target server. Should she reconnect it?

**Answer:** Not automatically. She should identify and document it, check labels and ticket scope, ask for guidance, and avoid making unauthorized changes.

### 79. A visitor says they are in a hurry and asks to follow her through the secure door. What should she do?

**Answer:** She should not allow tailgating. She should ask them to follow the proper access process and involve security if necessary.

### 80. She accidentally unplugged the wrong cable. What should she do?

**Answer:** Stop, reconnect only if safe and certain, notify the supervisor/NOC immediately, document the facts and time, support recovery, and participate in the review. Do not hide it.

### 81. The ticket asks for a photo of a rack. What must she check first?

**Answer:** She must check photo policy and authorization. Photos may expose customer information. If allowed, she should avoid capturing unrelated sensitive details where possible.

### 82. During a disk replacement, the disk bay number in the ticket does not match the amber LED. What should she do?

**Answer:** Stop and escalate. Replacing the wrong disk can cause data loss. She should document the mismatch and wait for confirmation.

### 83. A task is near the end of her shift and not complete. What should she do?

**Answer:** Write a clear handover note with context, completed actions, current state, blockers, risks, and next steps. Inform the next shift or supervisor according to process.

### 84. A customer is angry about delay. How should she respond?

**Answer:** Stay professional, acknowledge the concern, provide factual status, explain the blocker or safety/approval requirement, give the next step, and escalate if needed.

### 85. She finds equipment not recorded in the asset inventory. What should she do?

**Answer:** Do not assume ownership or remove it. Document location, labels, serial/model if allowed, notify the appropriate team, and follow asset reconciliation process.

### 86. A server front panel shows an amber light. Does that prove the server is down?

**Answer:** No. Amber usually indicates a fault or warning, but the server may still be running. She should record the exact LED state, check the runbook/vendor meaning if available, and report facts.

### 87. A cable label is missing. What is the correct action?

**Answer:** Do not disconnect it based on guesswork. Trace and verify using approved methods, ask for assistance, and document that the label is missing.

### 88. She is asked to work in an area where she does not have access. What should she do?

**Answer:** Request proper access or an authorized escort through the official process. She should not borrow someone else’s badge.

### 89. A remote engineer gives instructions by chat that differ from the ticket. What should she do?

**Answer:** Ask for the updated instruction to be recorded in the ticket or approved channel. Confirm scope before acting.

### 90. She sees packaging left in the aisle. Is this her problem?

**Answer:** Yes, it is a safety and housekeeping concern. She should remove it if allowed and safe, or report it to the responsible team.

---

# Part 3: Lab exercises with hints

Each lab should produce a portfolio artifact. The hints are there to guide her, but she should try first without looking.

## Lab 1: Build a data center concept map

### Objective

Create a visual map showing the main components of a data center and how they support digital services.

### Time

60-90 minutes

### Tools

- diagrams.net / draw.io, PowerPoint, Excalidraw, or paper

### Tasks

1. Draw a user accessing an application.
2. Show the request reaching a data center.
3. Add compute, storage, network, power, cooling, and security blocks.
4. Add at least three examples under each block.
5. Add arrows showing dependencies.
6. Write a 150-word explanation below the diagram.

### Hints

- Start with: `User -> Internet -> Network -> Server -> Storage`.
- Add power and cooling as supporting layers under everything.
- Add security as a boundary around the facility.
- Do not worry about perfect architecture; focus on explaining dependencies.

### Success criteria

- Someone non-technical can understand what the data center does.
- The diagram includes all six core areas: compute, storage, network, power, cooling, security.
- The explanation mentions why downtime matters.

### Deliverable

`01-data-center-concept-map.png` or `.drawio`

## Lab 2: Create a 75-term data center glossary

### Objective

Build vocabulary for interviews and future weeks.

### Time

2-3 hours

### Tasks

Create a markdown table with columns:

| Term | Simple definition | Why it matters |
|---|---|---|

Include at least 75 terms from this workbook and the main study plan.

### Hints

- Use simple words. If the definition is too complex, she probably does not understand it yet.
- Include examples, e.g. “A rack is like a standardized cabinet for servers.”
- Add terms from safety and ticketing, not only hardware.

### Success criteria

- At least 75 terms.
- Each term has a definition in her own words.
- She can explain 20 random terms aloud without reading.

### Deliverable

`02-glossary.md`

## Lab 3: Role responsibility matrix

### Objective

Understand who does what in a data center.

### Time

60 minutes

### Tasks

Create a table with roles as columns or rows:

- Data Center Technician
- Data Center Engineer
- NOC Engineer
- Facilities Engineer
- Network Engineer
- Security Officer
- Customer/Remote Engineer

For each task below, mark who is usually responsible, who assists, and who approves:

- Replace a failed disk
- Escort a visitor
- Investigate power alarm
- Configure a switch VLAN
- Trace a cable
- Update an incident ticket
- Approve a risky change
- Check CCTV/access logs
- Install a new server
- Investigate cooling issue

### Hints

- A technician may physically replace hardware, but a remote engineer or system owner may approve.
- Facilities owns power/cooling.
- Security owns access control.
- Network engineers own network configuration.

### Success criteria

- Matrix shows she understands boundaries.
- She can explain why technicians should not make unauthorized config changes.

### Deliverable

`03-role-responsibility-matrix.md`

## Lab 4: Data center safety checklist

### Objective

Create a practical checklist for safe physical work.

### Time

90 minutes

### Tasks

Create sections:

1. Before entering the data hall
2. Before touching equipment
3. During work
4. Before disconnecting cables
5. Before replacing hardware
6. After completing work
7. Emergency stop conditions

Each section should include at least 5 checklist items.

### Hints

- Include authorization checks, asset verification, ESD, manual handling, cable labels, and housekeeping.
- “Emergency stop conditions” should include burning smell, water, wrong asset, unclear instructions, missing approval, and unsafe lifting.

### Success criteria

- Checklist prevents common beginner mistakes.
- It is specific enough to be usable during real work.

### Deliverable

`04-safety-checklist.md`

## Lab 5: Access-control scenario exercise

### Objective

Practice security decisions before entering a real facility.

### Time

60 minutes

### Tasks

Write answers to these scenarios:

1. Someone follows behind you through a secure door without badging.
2. A contractor says their badge is not working but they are already late.
3. A customer asks you to take photos of a rack.
4. A colleague asks to borrow your badge.
5. You see a visitor alone in a restricted area.
6. A delivery driver asks where a specific customer cage is located.
7. You find a cabinet door left open.
8. Someone asks about an outage in a public area.

For each, write:

- Risk
- Correct action
- Who to notify
- Ticket/log note if needed

### Hints

- Think like an auditor: “Was access authorized, recorded, and appropriate?”
- Avoid confrontation; follow procedure and involve security.
- Do not reveal customer information casually.

### Success criteria

- Answers prioritize security without being rude.
- Answers include escalation path.

### Deliverable

`05-access-control-scenarios.md`

## Lab 6: Write professional ticket updates

### Objective

Practice writing clear ticket updates.

### Time

90 minutes

### Tasks

For each ticket below, write:

1. Acknowledgement update
2. Investigation update
3. Blocker or escalation update
4. Closure update

### Ticket A: Visual check

```text
Customer reports server app-dub-01 may be powered off. Please visually inspect rack D12 U18 and report LED status. Do not power cycle.
```

### Ticket B: Cable trace

```text
Please trace cable from server db-dub-02 NIC1 in rack C04 U22 to switch port. Do not disconnect cable.
```

### Ticket C: Disk fault

```text
Amber disk LED reported on storage node stg-dub-07. Confirm bay number and asset tag. Do not replace disk until remote engineer confirms.
```

### Hints

- Include timestamps.
- Mention what you verified: rack, U, asset tag, hostname label.
- State clearly if no physical changes were made.
- Avoid saying “fixed” unless you know the service owner has confirmed.

### Success criteria

- Updates are factual and professional.
- Anyone reading can understand current status and next step.

### Deliverable

`06-ticket-updates.md`

## Lab 7: Create a basic change request template

### Objective

Understand what makes a production change safe.

### Time

60-90 minutes

### Tasks

Create a reusable template with:

- Change title
- Requester
- Business reason
- Affected assets
- Risk level
- Preconditions
- Implementation steps
- Validation steps
- Rollback plan
- Maintenance window
- Communication plan
- Approvals
- Post-change notes

Then fill it out for this scenario:

```text
Replace a suspected faulty copper patch cable between server web-dub-03 NIC1 and switch SW-DUB-01 port Eth1/18 during a maintenance window.
```

### Hints

- Implementation should include verifying labels before touching anything.
- Validation could include link light, remote engineer ping test, monitoring clear, or customer confirmation.
- Rollback could be reconnecting the original cable if safe and approved.

### Success criteria

- Template shows risk, validation, and rollback.
- The example change is safe and controlled.

### Deliverable

`07-change-request-template.md`

## Lab 8: Handover note practice

### Objective

Learn how to transfer work safely to another shift.

### Time

45-60 minutes

### Scenario

Your shift ends before a ticket is complete:

```text
Ticket INC-1042: Server app-dub-01 unreachable. Visual inspection completed. Server powered on. NIC1 no link light. Cable label is partially missing. Remote engineer asked to trace cable, but switch-side port is not yet confirmed.
```

### Tasks

Write a handover note with:

- Ticket number
- Summary
- Timeline
- Actions completed
- Current status
- Risks
- Blockers
- Next recommended action
- Who has been notified

### Hints

- The next technician should not need to ask “what happened?”
- Be clear that no cable should be disconnected until verified.
- Include exact uncertainty: partial cable label, switch port not confirmed.

### Success criteria

- Handover is safe, factual, and actionable.

### Deliverable

`08-handover-note.md`

## Lab 9: Escalation writing practice

### Objective

Practice asking for help clearly.

### Time

45 minutes

### Tasks

Write escalation messages for:

1. Rack/U mismatch
2. Missing approval for power cycle
3. Unsafe lifting requirement
4. Cable label missing
5. Burning smell near rack
6. Visitor access mismatch

Use this structure:

```text
Issue:
Impact/Risk:
What I verified:
What I did not change:
Help/decision needed:
```

### Hints

- Good escalation is not weakness; it is risk control.
- Include facts, not emotion.
- State if work is paused.

### Success criteria

- Escalations are clear and specific.
- Each message includes requested decision or next step.

### Deliverable

`09-escalation-examples.md`

## Lab 10: Build a Week 1 mock interview script

### Objective

Prepare confident spoken answers.

### Time

2 hours

### Tasks

Write 1-2 minute answers for:

1. Tell me about yourself.
2. Why do you want a data center technician role?
3. What does a data center do?
4. What are the main safety risks in a data center?
5. How would you handle unclear ticket instructions?
6. Why is documentation important?
7. What would you do if you made a mistake?
8. How would you handle a difficult customer or remote engineer?
9. What have you done to prepare for this role?
10. Why should we hire you?

### Hints

- Use portfolio evidence: “I created a safety checklist, ticket examples, and a change template.”
- Do not pretend to have professional experience if she does not.
- Emphasize reliability, learning speed, calm communication, and careful process.

### Success criteria

- Answers sound natural, not memorized.
- She can give specific examples from labs.
- She can explain what she would do safely if unsure.

### Deliverable

`10-week-01-mock-interview-script.md`

## Lab 11: “Stop or proceed?” decision drill

### Objective

Train safe judgment.

### Time

45 minutes

### Tasks

For each item, answer **Proceed**, **Proceed with caution**, or **Stop and escalate**, then explain why.

1. Ticket, rack, U, asset tag, and cable label all match.
2. Ticket says U18 but server label at U18 is different.
3. Remote engineer asks for power cycle in chat but not in ticket.
4. Cable has no label.
5. Disk bay in ticket does not match amber LED.
6. Approved ticket asks only for visual inspection.
7. There is water near the rack.
8. Visitor badge does not allow access to requested cage.
9. Server is too heavy for one-person lift.
10. You completed the work and validation passed.

### Hints

- Most dangerous beginner mistakes happen when people assume.
- “Proceed” usually requires clear authorization, correct identification, and safe conditions.

### Suggested answer pattern

- Items 2, 3, 4, 5, 7, 8, 9 should normally be **Stop and escalate**.
- Item 6 should be **Proceed only within scope**: inspect but do not change anything.
- Item 10 should be **Proceed to documentation/closure**, not simply walk away.

### Deliverable

`11-stop-or-proceed-drill.md`

## Lab 12: Final Week 1 self-assessment

### Objective

Confirm readiness to move to Week 2.

### Time

60 minutes

### Tasks

Rate herself from 1 to 5 on each item:

| Skill | Score 1-5 | Evidence | Improvement action |
|---|---:|---|---|
| Explain what a data center does | | | |
| Name main data center components | | | |
| Explain core roles | | | |
| Describe safety risks | | | |
| Handle access-control scenarios | | | |
| Write ticket updates | | | |
| Create a change template | | | |
| Write a handover note | | | |
| Know when to escalate | | | |
| Answer Week 1 interview questions | | | |

### Hints

- Score honestly. A score of 3 is acceptable if there is a clear improvement plan.
- Anything below 3 should be reviewed before moving on.

### Success criteria

- All items score 3 or higher.
- At least five items score 4 or higher.
- Weak areas have concrete improvement actions.

### Deliverable

`12-week-01-self-assessment.md`

---

# Part 4: Templates to copy into the portfolio

## Ticket update template

```text
Time:
Location:
Asset verified:
Task performed:
Findings:
Changes made:
Evidence attached:
Current status:
Blockers/risks:
Next step:
```

## Handover template

```text
Ticket:
Summary:
Impact:
Timeline:
Actions completed:
Current state:
Open risks:
Blockers:
Next recommended action:
People/teams notified:
Do not do:
```

## Escalation template

```text
Issue:
Impact/Risk:
What I verified:
What I did:
What I did not change:
Decision/help needed:
Urgency:
```

## Change request template

```text
Change title:
Requester:
Business reason:
Affected assets:
Risk level:
Maintenance window:
Pre-checks:
Implementation steps:
Validation steps:
Rollback plan:
Communication plan:
Approvals:
Post-change notes:
```

## Safety checklist template

```text
Before work:
- [ ] Ticket and authorization confirmed
- [ ] Correct site/room/rack/U confirmed
- [ ] Asset tag/serial/hostname confirmed
- [ ] Scope understood
- [ ] Required tools/PPE available

During work:
- [ ] ESD precautions followed if handling components
- [ ] Cables verified before touching
- [ ] Aisle kept clear
- [ ] No unauthorized changes made
- [ ] Evidence recorded

After work:
- [ ] Equipment state verified
- [ ] Work area clean
- [ ] Labels/doors/cables checked
- [ ] Ticket updated
- [ ] Handover or closure completed
```

---

# Part 5: Week 1 final exam

## Written exam

Answer these without notes:

1. Explain a data center in 5 sentences.
2. List the six main data center building blocks and explain each.
3. Explain the difference between incident, service request, change, and problem.
4. List 10 reasons to stop and escalate.
5. Write a good ticket update for a visual server check.
6. Explain why physical security matters.
7. Explain why ESD matters.
8. Explain what a handover note should include.
9. Explain what a rollback plan is.
10. Explain why technicians should not guess in production.

## Practical exam

Complete these in 90 minutes:

1. Draw a simple data center concept map.
2. Write a safety checklist for replacing a server part.
3. Write an acknowledgement, progress update, escalation update, and closure note for a mock ticket.
4. Write a handover note for an incomplete task.
5. Answer five random scenario questions from this workbook aloud.

## Passing standard

She passes Week 1 if she can:

- Score at least 80% on the written exam.
- Complete all practical tasks with clear documentation.
- Explain mistakes and corrections.
- Answer scenario questions safely.
- Show all required portfolio artifacts.

---

# Part 6: Interview positioning for Week 1

If asked “What have you done so far to prepare for a data center role?”, she can say:

```text
I started by building the operational foundation. I studied what data centers do, the main areas like compute, storage, networking, power, cooling, and security, and the roles involved in day-to-day operations. I created a concept map, glossary, role responsibility matrix, safety checklist, access-control scenarios, ticket update examples, a change request template, and handover notes. My focus is learning to work safely and professionally: verify before touching equipment, document clearly, and escalate when something is unclear or unsafe.
```

If asked “You are new, why should we trust you around production equipment?”, she can say:

```text
I understand that trust in a data center comes from discipline, not guessing. I would follow the ticket and site procedures, verify the asset, rack, U position, labels, and authorization before touching anything, and stop if something does not match. I have been practicing professional ticket updates, safety checklists, and escalation examples so that even as a junior candidate I can work carefully and communicate clearly.
```

---

# Part 7: Week 1 completion checklist

- [ ] I can explain what a data center is.
- [ ] I can describe compute, storage, network, power, cooling, and security.
- [ ] I can explain data center roles and responsibility boundaries.
- [ ] I know at least 75 data center terms.
- [ ] I can explain ESD, manual handling, fiber safety, and electrical awareness.
- [ ] I can handle basic access-control scenarios safely.
- [ ] I can explain incident vs request vs change vs problem.
- [ ] I can write professional ticket updates.
- [ ] I can write a basic change request with validation and rollback.
- [ ] I can write a handover note.
- [ ] I know when to stop and escalate.
- [ ] I completed all Week 1 labs.
- [ ] I can answer at least 50 of the 90 questions aloud.
- [ ] I recorded or practiced a 10-minute mock interview.
- [ ] My Week 1 portfolio folder is complete.
