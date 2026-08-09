# Week 5 Detailed Workbook: Data Center Physical Operations

## Table of contents

- [Purpose of this workbook](#purpose-of-this-workbook)
- [Week 5 target level](#week-5-target-level)
- [Scope boundary: what is new this week](#scope-boundary-what-is-new-this-week)
- [Suggested weekly schedule](#suggested-weekly-schedule)
- [Day-by-day Week 5 study order](#day-by-day-week-5-study-order)
- [Required Week 5 portfolio artifacts](#required-week-5-portfolio-artifacts)
- [Part 1: Comprehensive Week 5 topics](#part-1-comprehensive-week-5-topics)
- [Part 2: Week 5 questions and model answers](#part-2-week-5-questions-and-model-answers)
- [Part 3: Lab exercises with hints](#part-3-lab-exercises-with-hints)
- [Part 4: Templates to copy into the portfolio](#part-4-templates-to-copy-into-the-portfolio)
- [Part 5: Week 5 final exam](#part-5-week-5-final-exam)
- [Part 6: Interview positioning for Week 5](#part-6-interview-positioning-for-week-5)
- [Part 7: Week 5 completion checklist](#part-7-week-5-completion-checklist)

## Purpose of this workbook

This workbook expands Week 5 of the Data Center Engineer / Data Center Technician study plan. It turns the hardware, networking, Linux, ticketing, and safety knowledge from Weeks 1-4 into safe physical operations work.

The aim is not to authorize the learner to work on live electrical infrastructure. A junior technician must follow site procedures, approved methods of procedure, and the direction of the facilities or operations team. The aim is to understand a rack-and-stack or remote-hands ticket well enough to plan it, identify risks, verify the correct equipment, collect evidence, and close the work professionally.

By the end of the week, she should be able to explain a physical task from ticket to closure: confirm scope, prepare the rack, install or trace the right item, preserve power and airflow, validate the result, update records, and escalate anything uncertain.

## Week 5 target level

The target is not "I know what a rack looks like." The target is:

- She can read a rack elevation, identify a rack unit position, and distinguish the front, rear, and 0U mounting areas.
- She can plan a safe rack-and-stack task, including approvals, tools, lifting, rails, cable slack, power, network, validation, and rollback.
- She can explain why weight distribution, rail compatibility, airflow, blanking panels, and cable management affect reliability.
- She can trace the normal power path from facility supply to a dual-PSU server without touching protected electrical infrastructure.
- She can distinguish A and B power paths, record which PSU is connected to which feed, and avoid creating a single point of failure.
- She can follow a cable label, port map, and device identifier before touching a cable.
- She can handle patch cables, fiber assemblies, optics, and latches carefully according to site procedure.
- She can update inventory, labels, photos, and ticket evidence after physical work.
- She can prepare a controlled decommissioning checklist that preserves approvals, data-handling evidence, and chain of custody.
- She can stop and escalate if the target, power path, safety condition, or instruction does not match the ticket.

## Scope boundary: what is new this week

Weeks 1-4 already introduced safety, server parts, networking basics, ticketing, and Linux health checks. This week does not repeat those lessons in detail. It focuses on their physical application.

| Earlier knowledge | Week 5 applies it by |
|---|---|
| Safety and change control | Building a physical work plan, stop points, and validation record |
| Server components | Identifying the correct chassis, rail kit, PSU, NIC, and asset tag before installation |
| Switch ports and VLAN concepts | Using approved port maps and labels without changing switch configuration |
| Linux evidence gathering | Using only approved post-install health checks as validation evidence |
| Ticket updates and handovers | Recording physical state, labels, photos, serials, and unresolved risks |

Do not practise on production equipment without authorization. Paper, diagram, spare hardware, cardboard mock-ups, a home lab, or a fictional environment are all sufficient for these exercises.

## Suggested weekly schedule

| Day | Focus | Main output |
|---|---|---|
| Day 1 | Tickets, rack elevations, rack safety, rails, and installation planning | Physical work plan and annotated rack elevation |
| Day 2 | Rack-and-stack workflow, weight, cable routes, and asset verification | Rack installation checklist and inventory update |
| Day 3 | Power paths, A/B feeds, redundancy, cooling, and airflow | Power map and airflow review |
| Day 4 | Copper, fiber, optics, labels, port maps, and validation | Cable standard and trace record |
| Day 5 | Change execution, spares, decommissioning, ticket updates, and interviews | Mock change pack, decommission checklist, and interview script |
| Day 6 optional | Repeat a full dry-run from ticket to closure | Timed evidence pack |
| Day 7 optional | Rest or catch-up | Clean Week 5 portfolio |

## Day-by-day Week 5 study order

| Day | Study sections | Practice | Portfolio output |
|---|---|---|---|
| Day 1 | Sections 1-4: operational boundaries, rack coordinates, safety, rails, and mechanical planning | Labs 1-3; Questions 1-12 | Rack elevation and method of procedure |
| Day 2 | Sections 5-6: installation sequence, asset control, cable pathways, and service loops | Labs 4 and 10; Questions 13-20 | Installation checklist and receiving record |
| Day 3 | Sections 7-8: power delivery, A/B resilience, cooling, and airflow | Labs 5-6; Questions 21-30 | Power matrix and airflow audit |
| Day 4 | Sections 9-10: copper, fiber, optics, labels, and traceability | Labs 7-8; Questions 31-38 | Cable labeling standard and port trace |
| Day 5 | Sections 11-12: spares, decommissioning, validation, handover, and escalation | Labs 9 and 11-12; Questions 39-50 | Change pack, decommission checklist, interview script, and self-assessment |
| Day 6 optional | Rehearse the end-to-end scenario without notes | Repeat Labs 2, 5, 7, and 9 | Timed physical-work evidence pack |
| Day 7 optional | Rest or catch-up | Review artifacts against the completion checklist | Ready-to-review Week 5 portfolio |

## Required Week 5 portfolio artifacts

Create a folder called week-05-data-center-operations and include:

    week-05-data-center-operations/
      README.md
      01-rack-elevation-and-legend.md
      02-rack-and-stack-method-of-procedure.md
      03-installation-dry-run-notes.md
      04-asset-and-receiving-record.md
      05-a-b-power-map-and-matrix.md
      06-airflow-and-rack-layout-audit.md
      07-cable-labeling-standard.md
      08-cable-and-port-trace-record.md
      09-network-cable-change-pack.md
      10-spares-management-checklist.md
      11-decommissioning-checklist.md
      12-physical-operations-ticket-updates.md
      13-week-05-interview-script.md
      14-week-05-self-assessment.md

---

# Part 1: Comprehensive Week 5 topics

## 1. Physical operations mindset and boundaries

Physical work can affect many customers at once. A small action, such as moving a cable, removing a blanking panel, or unplugging one PSU, can create a service interruption, airflow issue, or loss of redundancy. The professional habit is to slow down before the touch point.

Before beginning work, confirm:

- The ticket number, approved change, maintenance window, and requested outcome.
- The exact site, room, row, rack, rack face, and rack-unit position.
- The device hostname, asset tag, serial number, and visible label.
- Whether the equipment is production, lab, spare, decommissioned, or quarantined.
- Whether a remote engineer needs to be present or reachable for validation.
- The approved work method, rollback condition, and stop/escalate contacts.
- Local safety rules, access restrictions, photo policy, and lifting requirements.

Never infer that equipment is safe to touch just because it is physically near the target. Treat labels, rack positions, and written approval as separate checks that must agree.

## 2. Reading a rack elevation and physical coordinates

A rack elevation is the vertical map of a cabinet. Standard racks are often 42U or 45U, where 1U is 1.75 inches or 44.45 mm high. Rack-unit numbering normally starts at the bottom, so U1 is near the floor and U42 is near the top of a 42U cabinet. Always check the rack drawing and physical rail markings because a site may have a documented convention for its diagrams.

A useful elevation includes:

- Site, room, row, rack identifier, and front or rear view.
- U position, device name, asset tag, height, and mounting direction.
- 0U equipment such as vertical PDUs, which uses side or rear mounting space rather than horizontal rack units.
- Patch panels, switches, servers, storage, blanking panels, and reserved capacity.
- Front-to-back airflow direction and cable-management zones.
- A legend that differentiates production, management, and decommissioned equipment.

When the drawing and the physical rack disagree, stop. Do not "correct" the rack by memory. Collect photos if allowed, note the mismatch, and ask the owner to confirm the authoritative record.

## 3. Rack safety, rails, and mechanical planning

Racks are designed to hold heavy equipment safely only when rails, cage nuts, screws, and mounting points are compatible. The server rail kit must match the chassis and rack type. Do not force a rail, substitute undocumented hardware, or mount equipment on unsupported ears alone.

Plan mechanical work before opening the rack:

- Check the equipment weight and whether a two-person lift, lift device, or escalation is required.
- Confirm the rack is stable and that heavy equipment is placed low when the design permits.
- Verify front and rear rail positions, depth, cable-management arms, and clearance.
- Ensure the required cage nuts, screws, anti-static protection, and tools are approved and available.
- Avoid extending multiple heavy devices at the same time.
- Keep aisles clear and packaging controlled so it does not obstruct airflow, exits, or other work.

The goal is controlled motion. If the chassis binds, does not align, or feels unsafe, lower it safely and reassess instead of applying more force.

## 4. Method of procedure for physical work

A method of procedure, often called an MOP, converts a request into safe, observable steps. It should be detailed enough that another qualified technician can follow it and see where to stop.

A practical MOP has five phases:

1. Preparation: verify approval, equipment, identifiers, dependencies, tools, access, and contacts.
2. Baseline: record current LEDs, cable labels, PSU-feed mapping, port state supplied by the owner, and photos where permitted.
3. Execution: perform one controlled action at a time and mark each completed step.
4. Validation: confirm the requested physical state and ask the service owner to validate logical health where needed.
5. Closure or rollback: restore the known-good state if a stop condition occurs, then document exactly what happened.

Good stop conditions are specific. For example: "Stop if the asset tag does not match," "stop if both PSUs appear to use the same power feed," "stop if a port label does not match the port map," or "stop if the chassis does not fit the approved rail kit."

## 5. Rack-and-stack execution and asset control

The basic physical sequence is verify, install, connect, validate, document. It is not simply "put the server in the rack."

An example sequence for a new device is:

1. Verify the delivery record, asset tag, serial number, chassis model, rail kit, and approved rack position.
2. Inspect the device and packaging for visible damage. Record exceptions before installation.
3. Confirm the target rack, U positions, and rails are empty and match the elevation.
4. Install rails and chassis using the approved lifting method.
5. Install only the approved components, drives, transceivers, or cable-management parts.
6. Attach power and network connections by their exact labels, keeping A and B feeds distinct.
7. Dress cables so they have appropriate slack, no sharp stress, and do not block fan exhaust or access.
8. Confirm physical indicators, close rails or doors as required, and remove packaging.
9. Update asset records, rack elevation, cable map, labels, photos, and ticket evidence.
10. Obtain the required remote or local validation before closure.

The asset record should preserve the identity of the device throughout its lifecycle. At minimum, record hostname or planned hostname, asset tag, serial or service tag, rack and U position, installed date, owner, network identifiers, and power-feed information.

## 6. Cable pathways and cable management

Cable management is an availability practice, not decoration. A neat bundle is useful only if it is still traceable, serviceable, and does not place stress on cables or obstruct airflow.

Use site standards for:

- Separation of power and data routes where the facility requires it.
- Front versus rear cable routing.
- Horizontal and vertical managers.
- Approved hook-and-loop fasteners rather than overly tight cable ties where rework is expected.
- Service loops that allow removal without excessive slack.
- Bend radius, especially for fiber and high-speed assemblies.
- Consistent label orientation that can be read without disconnecting anything.
- Keeping fan inlets, exhausts, rails, PDUs, and rack doors clear.

Never use a cable's color as its only identity. Color can support a convention, but the label and documented source/destination are the evidence.

## 7. Power delivery and A/B resilience

It is useful to understand the physical power chain, even though facilities specialists operate the upstream electrical systems. A simplified chain is:

    Utility or generator source -> switchgear -> UPS -> distribution -> rack PDU -> server PSU

The exact facility design varies. A technician should not open electrical panels or work outside her authorization. Her operational responsibility is usually at the equipment and rack-PDU level: confirm the intended receptacle, preserve redundant paths, identify alarms or damage, and escalate facility concerns.

For a dual-PSU server:

- PSU 1 should connect to the designated A-path rack PDU outlet.
- PSU 2 should connect to the designated B-path rack PDU outlet.
- The two feeds should be genuinely independent according to the facility design, not just different sockets on the same unprotected path.
- Labels should make the mapping visible on the device, cable, and PDU record.

Redundancy only helps when it is preserved during work. Accidentally moving both power cords to one feed, or unplugging the only live PSU while testing the other, can turn a resilient design into an outage.

## 8. Cooling and airflow management

Most rack servers pull cooler air through the front and exhaust warmer air at the rear. A hot aisle/cold aisle layout keeps supply air and exhaust air separated. The exact layout is site-specific, but the principle is to avoid hot exhaust returning to device intakes.

Technicians protect airflow by:

- Leaving empty front rack spaces covered with blanking panels where required.
- Keeping front and rear doors, perforations, and fan paths unobstructed.
- Routing cables so they do not cover fans, power supplies, or vents.
- Reporting missing blanking panels, blocked tiles, damaged doors, unusual fan noise, or temperature alarms.
- Avoiding unapproved changes to rack layout or cooling equipment.

Cooling is a reliability and capacity issue. A system may appear healthy after an installation but later overheat if the cable bundle blocks rear exhaust or the change disrupts containment.

## 9. Copper, fiber, and optics handling

Copper Ethernet patch cables are flexible but still need gentle routing and strain relief. Fiber and optical transceivers need additional care because dirt, scratches, tight bends, and incorrect connector types can prevent a stable link.

Before connecting a cable or optic:

- Verify the approved source, destination, port, speed, medium, and label.
- Confirm the connector and transceiver type match the documented design.
- Keep protective caps in place until the connection is ready.
- Follow site procedure for inspection and cleaning. Do not improvise cleaning tools.
- Do not look into fiber ends or active optical ports.
- Do not pull on a cable to release it; use the correct latch or pull tab.
- Respect bend-radius and routing guidance.

If a link does not come up, preserve the evidence: labels, port identifiers, visible LED state, optic type, and the time of connection. Do not repeatedly swap optics or cables without approval because each change makes the fault harder to isolate.

## 10. Labels, port maps, and traceability

Every physical connection should be traceable without guessing. A label normally records enough information to identify both ends of the cable, such as:

    Site-Room-Rack-U-Device-Port <-> Site-Room-Rack-U-Device-Port

The exact format should follow local conventions. A good standard also defines:

- When labels are applied and who verifies them.
- Whether the label is attached at both ends and how it is oriented.
- How temporary, failed, spare, and decommissioned cables are marked.
- Which source is authoritative if the label and record conflict.
- How port maps, rack elevations, and asset databases are updated after a move, add, or change.

Use a two-person or two-source check for high-impact changes where procedure calls for it. Read the device label, cable label, port map, and ticket aloud or compare them line by line before disconnecting.

## 11. Receiving, spares, and decommissioning

Good physical operations includes the full equipment lifecycle.

For receiving and spares:

- Check the purchase or delivery reference, item count, part number, serial number, and physical condition.
- Record where the item is stored and its status: available, reserved, faulty, return pending, or quarantined.
- Preserve anti-static packaging and site-required environmental handling.
- Do not install a spare that has not been approved for the target model or configuration.

For decommissioning:

- Confirm owner approval, change record, maintenance window, and data-handling requirements.
- Confirm that service migration or retirement is complete; a powered-off server may still be needed for data, licences, or evidence.
- Obtain documented confirmation for data sanitization or storage handling from the responsible owner. Do not claim data was erased merely because hardware was removed.
- Trace and remove only approved cables, update power and network records, and protect reused parts.
- Update asset status, rack elevation, CMDB or inventory record, chain-of-custody record, and disposal or return evidence.

Decommissioning is not complete until the physical, logical, inventory, and security records agree.

## 12. Validation, ticket closure, and handover

Physical completion is different from service validation. A server may be correctly mounted and powered while still awaiting network, operating-system, or application validation by another team.

A strong closure update separates facts:

- Physical work completed: exact device, rack position, cable labels, power-feed mapping, and photos if approved.
- Validation completed: LEDs, console state, remote engineer confirmation, or approved health checks.
- Changes made: what was connected, moved, labelled, removed, or left unchanged.
- Exceptions: mismatched labels, unavailable port, damaged cable, lack of remote validation, or any temporary workaround.
- Records updated: rack elevation, asset record, port map, inventory, and ticket.
- Current state and next owner: ready for imaging, awaiting network configuration, monitoring for a specified period, or escalated.

Never use vague phrases such as "all good" when the owner has not validated the service. State exactly what was verified.

---

# Part 2: Week 5 questions and model answers

## Rack work and physical safety

### 1. What is a rack unit?

One rack unit, or 1U, is a standard vertical height of 1.75 inches or 44.45 mm. Rack elevations use U positions to show where equipment belongs.

### 2. Where is U1 normally located?

It is normally at the bottom of the rack. She should still confirm the site drawing and rail markings before working.

### 3. What is 0U equipment?

It uses rack space without occupying horizontal U positions, often by mounting vertically at the rear or side of a rack. Vertical rack PDUs are a common example.

### 4. Why must a rack elevation identify front or rear view?

Ports, power supplies, cable managers, and device orientation differ between the front and rear. A drawing without a view can cause the technician to work at the wrong side.

### 5. Why is equipment weight important during rack-and-stack?

Heavy equipment can injure people or destabilize a rack. Weight determines whether the task needs a second person, lift equipment, a lower rack position, or escalation.

### 6. What should she do if a rail kit does not fit?

Stop, support the device safely, and verify the chassis, rail kit, rack depth, and approved hardware. She should not force it or substitute parts without approval.

### 7. Why should heavy equipment normally be installed low in a rack?

Keeping weight low improves stability and reduces the risk of the rack becoming top-heavy. The approved rack plan remains the authority.

### 8. Why should multiple heavy servers not be extended at the same time?

Extending weight changes the rack's centre of gravity and can create a tipping hazard.

### 9. What is a method of procedure?

It is a step-by-step, approved work document that defines preparation, execution, validation, rollback, and stop conditions.

### 10. What is a useful stop condition?

An observable condition that requires work to pause, such as a mismatched asset tag, unknown cable, unsafe lifting condition, or unexpected loss of redundancy.

### 11. What should she do if the physical rack does not match its elevation?

She should stop, collect permitted evidence, report the mismatch, and ask the owner to confirm or correct the authoritative record.

### 12. Why is a baseline useful before physical work?

It records the known state, such as LEDs, cable labels, and power feeds, so unexpected changes can be recognized and a rollback has a reference point.

## Installation, power, and cooling

### 13. What is the basic order of a controlled installation?

Verify the target, install the approved hardware, connect labelled power and network paths, validate the physical state, update records, and obtain service-owner confirmation where required.

### 14. What is A/B power?

It is a redundant design in which separate power paths feed separate PSUs of a device. It reduces the chance that one power-path failure stops the device.

### 15. Does plugging two PSUs into two sockets always create A/B redundancy?

No. The sockets must map to independent paths according to the facility design. Two outlets on the same failed path may not provide meaningful redundancy.

### 16. Why should PSU-to-feed mapping be recorded?

It lets technicians preserve redundancy during later work and provides evidence when investigating power events.

### 17. What should she do before unplugging one PSU?

Confirm the exact device and PSU, verify the other PSU and its feed are healthy as required by procedure, confirm approval, and understand the validation and rollback plan.

### 18. What is a rack PDU?

It is the power-distribution unit in or near a rack that provides power outlets for IT equipment. Upstream electrical equipment remains within facilities responsibilities.

### 19. Why are blanking panels important?

They reduce recirculation of hot exhaust air into the cold aisle and help direct cooling air through installed equipment.

### 20. What should she do if a cable bundle blocks a fan or exhaust path?

Do not make an unapproved rearrangement. Record the risk and work with the owner or change process to correct the routing safely.

### 21. What is hot aisle/cold aisle containment trying to prevent?

It prevents hot server exhaust from mixing with cool supply air, improving cooling effectiveness and reducing hot spots.

### 22. Why is airflow a concern after adding a server?

The new device changes heat load, airflow resistance, and cable density. A physically successful installation can still create a later thermal problem.

### 23. What is the difference between redundancy and capacity?

Redundancy provides an alternate path after a failure. Capacity is the ability to carry normal or peak load. A system can be redundant but still overloaded.

### 24. Should a technician alter UPS, generator, or switchgear settings during a normal rack ticket?

No. Those systems are normally managed by authorized facilities personnel. She should report concerns through the approved escalation path.

### 25. Why is exact outlet identification important?

Wrong outlet use can overload a circuit, break A/B separation, or disconnect another device during tracing.

### 26. What should a power map show?

The device, each PSU, cable label, rack PDU, outlet, A or B path, and any required validation status.

### 27. What is a single point of failure?

A component or path whose failure can stop a service because no independent alternative exists.

### 28. Why should she not assume an unplugged power cord is unused?

It may be a reserve feed, a disconnected path under investigation, or a cable serving another device. Labels and records must be checked.

### 29. What does a temperature alert require from a technician?

She should assess and report the approved physical evidence, such as rack location, obstructions, LED or display status, and obvious airflow concerns, then escalate to the responsible team.

### 30. Why should rack doors and aisles be kept clear?

They support airflow, safe access, emergency egress, and the ability to perform future work without disturbing equipment.

## Cabling, labels, and lifecycle work

### 31. Why is a cable label more reliable than cable color?

Color conventions can be reused, misunderstood, or inconsistent. A label tied to an approved record identifies the source and destination.

### 32. What should she verify before disconnecting a network cable?

The ticket, device identity, port map, cable label at both ends if possible, service impact, approval, and rollback plan.

### 33. Why should power and data cabling be managed deliberately?

Good routing improves safety, traceability, airflow, serviceability, and compliance with site standards.

### 34. What is a service loop?

It is controlled extra cable length that permits approved maintenance without stressing connectors. It must not become a tangled obstruction.

### 35. Why is fiber bend radius important?

Tight bends can damage the fibre or cause signal loss. Follow the cable and site handling guidance.

### 36. Why should protective caps stay on unused fiber connectors and optics?

They help prevent contamination and damage to sensitive optical surfaces.

### 37. Can she look into a fiber connector or active optical port?

No. She should never look into fiber ends or active optical ports.

### 38. A newly connected link stays down. What is the safest first response?

Confirm the approved source, destination, labels, port and optic types, and visible LED state. Record the evidence and escalate rather than repeatedly swapping components.

### 39. What records should be updated after a cable move?

The cable label record, port map, rack elevation if relevant, asset or configuration record, ticket, and approved photos or validation evidence.

### 40. What should be checked when receiving a spare part?

Part number, serial number, quantity, condition, storage location, status, compatibility, and delivery reference.

### 41. Is removing a server enough to prove it is decommissioned?

No. Decommissioning also needs owner approval, data-handling confirmation, asset and service-record updates, and disposal or return evidence.

### 42. Why is chain of custody relevant to removed drives?

It records who handled sensitive equipment and supports security, audit, and data-protection requirements.

### 43. What should she do if a device is labelled for decommissioning but is still powered and connected?

Pause and obtain confirmation from the owner or change record. The physical label alone is not authorization to disconnect it.

### 44. What should a good physical-work ticket update contain?

Time, target identifiers, approved task, actions performed, cables and power paths affected, evidence collected, validation result, record updates, and any outstanding risk or owner.

### 45. How should she describe incomplete validation?

State the physical state that is confirmed and name the missing validation and responsible next owner. Do not imply service health without evidence.

### 46. Why remove packaging and tools after work?

They can obstruct airflow, access, cleaning, safety routes, and future work. Clearing them also confirms the work area is left controlled.

### 47. What does "remote hands" mean in this context?

It means carrying out approved physical tasks for a remote engineer while reporting exact observations and following instructions without guessing.

### 48. What if the remote engineer asks for an action that conflicts with the ticket or appears unsafe?

Pause, explain the discrepancy factually, and request a documented clarification or escalation through the approved process.

### 49. What is the strongest evidence that a cable was changed correctly?

Matching labels and records, approved before/after evidence, physical link state where applicable, and validation from the appropriate network or service owner.

### 50. What should she be able to do at the end of Week 5?

Plan, dry-run, document, and explain a safe rack-and-stack, cable, power, cooling, or decommissioning task without claiming authority beyond her role.

---

# Part 3: Lab exercises with hints

## Lab 1: Build a 42U rack elevation and legend

### Goal

Create a readable physical map of a fictional rack.

### Steps

1. Draw a 42U front and rear elevation in diagrams.net, on paper, or in a spreadsheet.
2. Place a patch panel, two switches, four 1U servers, one 2U storage device, blanking panels, and two vertical rack PDUs.
3. Label each device with hostname, asset tag, and U position.
4. Mark front-to-back airflow and identify which items are 0U.
5. Add a legend for production equipment, management equipment, spare capacity, and decommissioned equipment.
6. Reserve enough empty space for airflow and future capacity according to your fictional design.

### Hints

- Number the rack from U1 at the bottom.
- Keep the front and rear views clearly separate.
- A diagram is useful only if another person can find a device quickly.

### Expected portfolio output

01-rack-elevation-and-legend.md

## Lab 2: Write a rack-and-stack method of procedure

### Goal

Turn a ticket to install a new 1U server into a controlled work plan.

### Scenario

Install server DC-LAB-WEB-03, asset tag LAB-103, into Rack R12 at U18. It has two PSUs and two network ports. The remote engineer will validate operating-system reachability after the physical work.

### Steps

1. Write preparation, baseline, execution, validation, rollback, and closure sections.
2. Include exact identifiers to verify before touching the rack.
3. Include stop conditions for a mismatched U position, rail kit, power feed, cable label, or port map.
4. Specify which facts the remote engineer must validate.
5. Include post-work record updates.

### Hints

- Do not write "connect power" without specifying the PSU-to-feed mapping.
- Make every action observable and reversible where possible.

### Expected portfolio output

02-rack-and-stack-method-of-procedure.md

## Lab 3: Run a safe installation dry-run

### Goal

Practise the sequence without live data center equipment.

### Steps

1. Use a cardboard box, spare PC, shelf, or drawn rack as a mock server.
2. Label a target rack position, two power feeds, two network ports, and cable routes.
3. Read the MOP from Lab 2 aloud and perform each mock step.
4. Mark where you would pause for a two-person lift, an identity check, and remote validation.
5. Write down one ambiguity you noticed and improve the MOP.

### Hints

- The goal is procedural accuracy, not realistic hardware.
- If you cannot explain the next step clearly, the instruction is not detailed enough yet.

### Expected portfolio output

03-installation-dry-run-notes.md

## Lab 4: Create an asset and receiving record

### Goal

Practise controlling equipment identity before it enters a rack.

### Steps

1. Create records for three fictional devices: a server, a spare drive, and a network optic.
2. Include part number, serial number, asset tag, owner, status, storage or rack location, condition, and receiving reference.
3. Mark one item as quarantined because its box is damaged.
4. Explain what needs approval before the spare drive can be installed.

### Hints

- A serial number identifies a specific item; a part number identifies a model or type.
- Keep "available spare" separate from "approved for this task."

### Expected portfolio output

04-asset-and-receiving-record.md

## Lab 5: Draw an A/B power map and verification matrix

### Goal

Show how redundant power should be preserved for a small rack.

### Steps

1. Add three dual-PSU servers to your rack diagram.
2. Draw an A-path and B-path rack PDU.
3. Connect PSU 1 and PSU 2 for each server to their intended feeds.
4. Create a table with device, PSU, cable label, PDU, outlet, feed, and verification status.
5. Describe what must be checked before temporarily disconnecting PSU 1 on one server.

### Hints

- Do not assume two outlets are independent.
- The lab is a diagram exercise; do not unplug real equipment.

### Expected portfolio output

05-a-b-power-map-and-matrix.md

## Lab 6: Perform an airflow and rack-layout audit

### Goal

Identify physical conditions that could create thermal or serviceability problems.

### Steps

1. Review your rack elevation from Lab 1.
2. Identify at least five possible problems, such as empty U gaps, a blocked fan path, a dense cable bundle, missing slack, a top-heavy layout, or inaccessible PDUs.
3. For each issue, write the risk, evidence, owner, and safe corrective recommendation.
4. Mark which changes require an approved maintenance activity.

### Hints

- Do not treat every empty U as wrong; use the rules of your fictional site.
- Separate an observed fact from a proposed correction.

### Expected portfolio output

06-airflow-and-rack-layout-audit.md

## Lab 7: Create a cable labeling standard and port map

### Goal

Make every physical connection traceable.

### Steps

1. Define a label format for power, copper network, and fiber cables.
2. Add examples for R12-U18-NIC1 to SW01-Eth1/18 and R12-U18-PSU1 to PDU-A-18.
3. Create a port map with source, destination, cable type, label, owner, and status.
4. Define what happens when the physical label disagrees with the port map.
5. Write a two-source verification step for an approved cable change.

### Hints

- Use labels that remain useful after the cable is moved or inspected months later.
- Do not rely on color alone.

### Expected portfolio output

07-cable-labeling-standard.md

## Lab 8: Write a fiber and optic handling response

### Goal

Practise a safe response to a suspected physical-link issue.

### Scenario

A remote engineer says the link on SW01-Eth1/18 has stayed down after a new fiber patch and optic were fitted.

### Steps

1. Write the facts you need before touching the link.
2. List the physical observations you can collect without changing anything.
3. State what you must not do without approval.
4. Write a concise escalation update if labels, optic type, or port map do not match.

### Hints

- Record exact port and label identifiers.
- Do not repeatedly swap parts in an uncontrolled way.

### Expected portfolio output

08-cable-and-port-trace-record.md

## Lab 9: Prepare a change pack for a failed network cable

### Goal

Plan a cable replacement without creating an avoidable outage.

### Scenario

Replace the primary network cable for a non-redundant lab server. The server owner has approved a maintenance window.

### Steps

1. Describe scope, impact, preparation, target checks, and communication plan.
2. Include a labelled before-state and intended after-state.
3. Define the exact disconnect and reconnect sequence.
4. Include validation with the service owner.
5. Include rollback if the replacement cable does not restore the link.
6. Write an implementation and closure ticket update.

### Hints

- Non-redundant means a cable change can interrupt service.
- A cable is not confirmed working just because it is physically connected.

### Expected portfolio output

09-network-cable-change-pack.md

## Lab 10: Build a spares management checklist

### Goal

Show that spare parts must be controlled before they are needed.

### Steps

1. Create a checklist for receiving, storing, issuing, returning, and disposing of a spare part.
2. Include serial tracking, compatibility, condition, anti-static handling, ownership, and status.
3. Add an escalation rule for an unlabelled or damaged spare.
4. Explain why a failed drive requires stricter handling than an empty cardboard box.

### Hints

- The checklist should work for a technician on a busy shift.

### Expected portfolio output

10-spares-management-checklist.md

## Lab 11: Write a decommissioning checklist

### Goal

Plan the safe retirement of a fictional server.

### Steps

1. Include service-owner approval, change approval, and confirmation that the device can be retired.
2. Include data-handling and storage-media confirmation from the responsible owner.
3. Include cable tracing, power removal, asset status change, rack elevation update, chain of custody, and disposal or return record.
4. Add explicit stop conditions.
5. Write a closure update that distinguishes physical removal from data sanitization confirmation.

### Hints

- "Powered off" and "safe to dispose of" are not the same status.

### Expected portfolio output

11-decommissioning-checklist.md

## Lab 12: Write mock physical-operations ticket updates

### Goal

Communicate physical work with exact evidence.

### Scenarios

Write updates for:

1. A server was installed but remote validation is still pending.
2. A cable label does not match the port map.
3. A dual-PSU server appears to have both PSUs on the same feed.
4. A rack installation is stopped because the supplied rails do not fit.
5. A decommission request lacks data-handling confirmation.

### For each scenario, include

- Time and ticket.
- Exact target identifiers.
- Facts observed.
- Actions performed or deliberately not performed.
- Risk or stop condition.
- Requested next action and owner.

### Expected portfolio output

12-physical-operations-ticket-updates.md

## Lab 13: Build a Week 5 mock interview script

### Goal

Prepare confident, safety-focused spoken answers.

### Steps

Write 45-90 second answers for:

1. How do you plan a rack-and-stack task?
2. What is A/B power and how do you protect it?
3. Why does airflow matter in a rack?
4. How do you avoid unplugging the wrong cable?
5. What do you check before installing a server?
6. How do you handle a rail kit that does not fit?
7. What is a good cable label?
8. How do you respond to a newly connected link that remains down?
9. What does decommissioning require besides removing hardware?
10. When do you stop and escalate physical work?

### Expected portfolio output

13-week-05-interview-script.md

## Lab 14: Final Week 5 self-assessment

### Goal

Measure whether the learner can plan physical work without unsafe assumptions.

### Self-assessment table

| Skill | Can do without notes | Can do with notes | Need more practice |
|---|---|---|---|
| Read a rack elevation and find a U position | | | |
| Identify front, rear, and 0U equipment | | | |
| Write a physical-work MOP with stop conditions | | | |
| Explain safe lifting and rail compatibility | | | |
| Create an A/B power map | | | |
| Explain how airflow and blanking panels affect reliability | | | |
| Create a cable label and port map | | | |
| Explain safe fiber and optic handling | | | |
| Record an asset or spare correctly | | | |
| Plan a cable replacement with rollback | | | |
| Plan a controlled decommissioning | | | |
| Write evidence-based physical-work updates | | | |
| Explain when to stop and escalate | | | |

### Expected portfolio output

14-week-05-self-assessment.md

---

# Part 4: Templates to copy into the portfolio

## Physical work method of procedure template

    # Physical Work Method of Procedure

    Ticket/change:
    Date and maintenance window:
    Technician:
    Site / room / row / rack:
    Target device and asset tag:
    Requested outcome:
    Service owner / remote engineer:

    ## Preparation

    - [ ] Approval and scope confirmed.
    - [ ] Target rack, U position, device, and asset tag confirmed.
    - [ ] Required rails, tools, labels, cables, and spares verified.
    - [ ] Lifting and safety requirements checked.
    - [ ] Power and network maps reviewed.
    - [ ] Rollback and escalation contacts confirmed.

    ## Baseline evidence

    ## Execution steps

    ## Stop conditions

    ## Validation

    ## Rollback

    ## Record updates and closure

## A/B power verification matrix

| Device | Asset tag | PSU | Cable label | Rack PDU | Outlet | Feed | Verified by | Time |
|---|---|---|---|---|---|---|---|---|
| | | PSU 1 | | | | A/B | | |
| | | PSU 2 | | | | A/B | | |

## Cable trace record

| Ticket | Source device / port | Destination device / port | Cable type | Cable label | Before state | After state | Validation owner |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

## Physical work ticket update template

    # Physical Work Update

    Time:
    Ticket/change:
    Location:
    Target device / asset tag:

    ## Scope confirmed

    ## Physical evidence before work

    ## Actions performed

    ## Power and network paths affected

    ## Validation completed

    ## Records updated

    ## Current state / risk / next owner

## Decommissioning record template

    # Decommissioning Record

    Ticket/change:
    Device / asset tag / serial:
    Owner approval:
    Service retirement confirmation:
    Storage-media or data-handling confirmation:
    Cables and power removed:
    Asset and rack records updated:
    Chain of custody:
    Disposal / return reference:
    Final status:

---

# Part 5: Week 5 final exam

## Written exam

Answer these without looking at notes:

1. Explain what a rack elevation is and how to use it safely.
2. Explain the difference between 1U and 0U equipment.
3. List the checks required before installing a server.
4. Explain why rail compatibility and equipment weight matter.
5. Explain A/B power and how an error can remove redundancy.
6. Draw a basic power path from facility supply to a server PSU.
7. Explain why blanking panels and cable routing matter to cooling.
8. List five checks before disconnecting a network cable.
9. Explain safe fiber and optic handling rules.
10. Write three useful physical-work stop conditions.
11. Explain the difference between physical completion and service validation.
12. Explain why decommissioning requires more than physical removal.
13. Write a short ticket update for an installation that awaits remote validation.

## Practical exam

Complete these tasks in the fictional lab:

1. Find a target device on a 42U rack elevation.
2. Write an MOP to install a dual-PSU server.
3. Create an A/B power map and verification matrix.
4. Trace a network cable from an approved port map without disconnecting it.
5. Identify three airflow or serviceability risks in a rack diagram.
6. Produce a cable label standard with examples.
7. Write a stop-and-escalate note for a mismatched cable label.
8. Prepare a decommissioning checklist and closure update.
9. Explain the full task aloud from ticket to handover.

## Passing standard

She passes Week 5 if she can:

- Plan physical work before touching equipment.
- Find and verify the exact rack, U position, asset, power feed, and cable path.
- Explain safe handling, lifting, rails, airflow, and cable-management principles.
- Preserve A/B power resilience in a diagram and in a written procedure.
- Use labels and records rather than visual guesses.
- Separate physical evidence from service-owner validation.
- Control spares and decommissioned equipment responsibly.
- Stop and escalate when the physical situation does not match the approved plan.

---

# Part 6: Interview positioning for Week 5

Week 5 gives her credible physical-operations language. She should not claim that she has operated a live facility or performed electrical work if she has only practised in a lab. She can truthfully say that she has built and rehearsed the documents and decision process used for safe data center physical work.

## Strong interview themes

- I verify ticket scope, location, asset identity, and approvals before touching equipment.
- I understand rack elevations, U positions, rails, lifting boundaries, and the need for controlled work.
- I protect redundancy by mapping PSU 1 and PSU 2 to the correct A and B feeds.
- I treat labels and port maps as evidence, not cable color or memory.
- I understand that airflow, blanking panels, and cable routing affect reliability.
- I document physical work, validation status, record updates, and unresolved risk clearly.
- I pause when a rail, label, power feed, or instruction does not match the approved plan.

## Example answer: planning a rack-and-stack task

"I would first confirm the ticket or change, maintenance window, rack, U position, device asset tag, rail kit, lifting requirement, power map, port map, and validation owner. I would take approved baseline evidence, install the device one controlled step at a time, connect each PSU to its designated feed, and make sure cables do not block airflow. I would update the rack elevation and asset records, then state clearly whether I completed physical validation only or also received service-owner confirmation."

## Example answer: protecting A/B power

"For a dual-PSU device, I would verify the approved mapping for each PSU before connecting or disconnecting anything. I would record the device, PSU, cable label, PDU outlet, and A or B feed. I would not assume two sockets are independent, and I would stop if the documentation or visible labels made the redundant path unclear."

## Example answer: avoiding the wrong cable

"I would not work from color or proximity. I would compare the ticket, device label, source and destination port map, cable label, and service impact. If those checks do not agree, I would pause and request clarification. After an approved change, I would record exactly what moved and who validated the result."

---

# Part 7: Week 5 completion checklist

- [ ] I created a Week 5 portfolio folder.
- [ ] I built front and rear rack elevations with a clear legend.
- [ ] I can find a device by rack and U position.
- [ ] I wrote a rack-and-stack MOP with preparation, stop conditions, validation, and rollback.
- [ ] I practised a safe installation dry-run.
- [ ] I created an asset and receiving record.
- [ ] I can explain rails, lifting boundaries, and rack stability.
- [ ] I created an A/B power map and verification matrix.
- [ ] I can explain the power path and my facilities escalation boundary.
- [ ] I completed an airflow and rack-layout audit.
- [ ] I created a cable labeling standard and port map.
- [ ] I can explain safe fiber and optic handling.
- [ ] I prepared a network-cable change pack with rollback.
- [ ] I built a spares-management checklist.
- [ ] I prepared a controlled decommissioning checklist.
- [ ] I wrote physical-operations ticket updates.
- [ ] I completed the Week 5 mock interview script.
- [ ] I completed the Week 5 final exam and self-assessment.
- [ ] I can explain when to stop and escalate rather than improvising.
