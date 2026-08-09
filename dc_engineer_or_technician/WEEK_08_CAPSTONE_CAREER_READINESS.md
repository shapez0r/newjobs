# Week 8 Detailed Workbook: Capstone and Career Readiness

## Table of contents

- [Purpose of this workbook](#purpose-of-this-workbook)
- [Week 8 target level](#week-8-target-level)
- [Scope boundary: integration rather than repetition](#scope-boundary-integration-rather-than-repetition)
- [Suggested weekly schedule](#suggested-weekly-schedule)
- [Day-by-day Week 8 study order](#day-by-day-week-8-study-order)
- [Required Week 8 portfolio artifacts](#required-week-8-portfolio-artifacts)
- [Part 1: Comprehensive Week 8 topics](#part-1-comprehensive-week-8-topics)
- [Part 2: Week 8 questions and model answers](#part-2-week-8-questions-and-model-answers)
- [Part 3: Lab exercises with hints](#part-3-lab-exercises-with-hints)
- [Part 4: Templates to copy into the portfolio](#part-4-templates-to-copy-into-the-portfolio)
- [Part 5: Week 8 final exam](#part-5-week-8-final-exam)
- [Part 6: Interview positioning for Week 8](#part-6-interview-positioning-for-week-8)
- [Part 7: Week 8 completion checklist](#part-7-week-8-completion-checklist)

## Purpose of this workbook

This workbook expands Week 8 of the Data Center Engineer / Data Center Technician study plan. It turns the previous seven weeks into one coherent, truthful hiring package.

The capstone is not a second theory course. It is an integration exercise: create a fictional but realistic environment, make its physical and logical records agree, show how it would be operated, handle representative tickets and an incident, and explain the work clearly in an interview.

A well-documented lab portfolio demonstrates judgment, practice, and learning ability. It is not the same as paid production experience. The strongest final package makes that distinction clear while still giving the candidate concrete evidence to discuss.

## Week 8 target level

The target is not "I have a collection of files." The target is:

- She can present one internally consistent mini data-center environment with stated assumptions and limits.
- She can trace a service from its rack, power feeds, and network ports to its virtual or service dependencies.
- She can show clear asset, cable, power, rack, Linux, monitoring, incident, and handover evidence without copying every previous workbook.
- She can demonstrate four common operational tickets: rack a new server, replace a failed disk, troubleshoot link down, and decommission a server.
- She can explain the design's redundancy, recovery controls, failure domains, and residual risks honestly.
- She can deliver an 8-10 minute capstone walkthrough and answer follow-up questions calmly.
- She can create an ATS-friendly CV, focused LinkedIn profile, skills-evidence matrix, and role-tailored application materials.
- She can use truthful lab examples in behavioural interviews instead of inventing production experience.
- She can identify a skills gap, state how she is closing it, and explain what she would escalate in a real environment.

## Scope boundary: integration rather than repetition

This week reuses and improves prior artifacts. It does not reproduce detailed Linux command lessons, networking theory, rack mechanics, or incident methodology.

| Earlier week | Week 8 uses it as evidence |
|---|---|
| Week 1 | Safety, change, communication, ticket, and handover discipline |
| Week 2 | Server inventory, hardware checks, failed-disk reasoning, and asset details |
| Week 3 | Port map, cable labels, network troubleshooting flow, and safe boundaries |
| Week 4 | Linux health-check runbook and service evidence |
| Week 5 | Rack elevation, A/B power map, physical-work MOP, and decommission control |
| Week 6 | Incident timeline, escalation packet, validation, handover, and PIR |
| Week 7 | Dependency map, resilience, monitoring, cloud-awareness, and failure domains |

Do not paste full earlier documents into the capstone. Link to them or summarize only the part needed to operate the fictional environment. The final package is stronger when it is concise, navigable, and internally consistent.

## Suggested weekly schedule

| Day | Focus | Main output |
|---|---|---|
| Day 1 | Audit previous work, define capstone scope, assumptions, names, and source of truth | Scope statement and evidence inventory |
| Day 2 | Build the final physical, logical, service, inventory, power, and risk architecture pack | Architecture and traceability pack |
| Day 3 | Build the operations runbook, change plan, four tickets, and evidence links | Operational ticket pack |
| Day 4 | Run integrated incident, quality assurance, and capstone presentation rehearsal | Incident pack, QA log, and presentation notes |
| Day 5 | Create CV, LinkedIn draft, job-description skill matrix, STAR stories, and mock interview | Role-ready hiring package |
| Day 6 optional | Deliver the presentation and mock interview without notes | Recording or review notes and improvements |
| Day 7 optional | Prepare a targeted application queue | Application tracker and next 30/60/90-day plan |

## Day-by-day Week 8 study order

| Day | Study sections | Practice | Portfolio output |
|---|---|---|---|
| Day 1 | Sections 1-3: capstone scope, assumptions, source of truth, naming, and confidentiality | Labs 1-2; Questions 1-10 | Scope statement, evidence inventory, architecture, and asset inventory |
| Day 2 | Sections 4-5: traceability, resilience, risk, runbooks, validation, and controlled changes | Labs 3-5; Questions 11-20 | Risk map, operations runbook, and change plan |
| Day 3 | Sections 6-7: ticket pack, integrated incident, handover, and documentation quality | Labs 6-11; Questions 21-32 | Four tickets, incident pack, handover, and QA review |
| Day 4 | Sections 8-10: presentation, CV evidence, LinkedIn, role analysis, and truthful positioning | Labs 12-14; Questions 33-43 | Presentation notes, CV, LinkedIn draft, and skill matrix |
| Day 5 | Sections 11-12: STAR stories, technical interviews, application strategy, and growth plan | Labs 15-16; Questions 44-55 | Interview script, scorecard, self-assessment, and action plan |
| Day 6 optional | Deliver and improve the capstone | Repeat Labs 11, 12, and 15 | Improved presentation and answer notes |
| Day 7 optional | Tailor materials to selected roles | Use the skills-evidence matrix | Application tracker |

## Required Week 8 portfolio artifacts

Create a folder called week-08-capstone-career-readiness and include:

    week-08-capstone-career-readiness/
      README.md
      01-capstone-scope-and-assumptions.md
      02-evidence-inventory-and-source-of-truth.md
      03-final-architecture-and-asset-inventory.md
      04-service-dependency-resilience-and-risk-map.md
      05-integrated-operations-runbook.md
      06-change-plan-and-validation-record.md
      07-ticket-rack-new-server.md
      08-ticket-replace-failed-disk.md
      09-ticket-troubleshoot-link-down.md
      10-ticket-decommission-server.md
      11-integrated-incident-and-handover.md
      12-documentation-quality-review.md
      13-capstone-presentation-notes.md
      14-role-targeted-cv.md
      15-job-description-skill-matrix-and-linkedin.md
      16-star-story-bank-and-interview-script.md
      17-week-08-self-assessment-and-next-steps.md

---

# Part 1: Comprehensive Week 8 topics

## 1. Capstone scope, assumptions, and honesty

Start by defining a fictional environment that is small enough to explain and rich enough to demonstrate operations skills. A useful scenario is a single 42U rack supporting a small internal business service with dual top-of-rack switches, two rack PDUs, several servers, monitoring, and a small virtualized workload.

State clearly:

- What is fictional, what was practised in a local lab, and what is diagram-only.
- The intended audience: hiring manager, interviewer, or peer reviewer.
- What is in scope and out of scope.
- The security and confidentiality rules for the portfolio.
- The assumptions that make the design work.
- The limitations that prevent the design from being a full production reference architecture.

Use fictional names consistently. For example, if APP-01 is on host HYP-01 and Rack R12 U18, use those identifiers in every diagram, ticket, label, and incident. Do not use a real employer, customer, facility, access badge, IP address, serial number, password, or restricted photo.

## 2. Source of truth and cross-document traceability

A capstone should have a clear source of truth for each record. A rack elevation, asset inventory, port map, power map, ticket, and diagram may all refer to the same device but serve different purposes.

Create a traceability table that links:

- Hostname or service name.
- Asset tag and lifecycle state.
- Rack, U position, front or rear location.
- Network port, cable label, and intended role.
- PSU, rack PDU, outlet, and A/B feed.
- VM, application, storage, monitoring, and owner relationship.
- Relevant ticket, change, incident, or runbook reference.

When two documents disagree, do not silently choose the convenient one. Record the inconsistency, decide which source is authoritative, correct the affected record, and document the review. This is a key operation skill and a strong interview example.

## 3. Integrated architecture and inventory

Use several focused diagrams instead of one unreadable page:

1. Physical rack elevation: devices, U positions, front/rear view, PDUs, and airflow.
2. Power map: each PSU to PDU outlet and feed.
3. Network and cable map: server NICs, switch ports, labels, and logical role.
4. Service dependency diagram: application, database, monitoring, virtual host, storage, and customer entry point.
5. Resilience and risk diagram: failure domains and controls.

The inventory should be the bridge across the diagrams. It can include hostname, asset tag, role, rack position, power feeds, network ports, operating-system or VM role, owner, lifecycle state, and related documents.

Avoid false precision. If the project is fictional, label assumptions as assumptions. For example, a fictional shared-storage component can be shown as "LAB-STOR-01" with its role and dependency, without claiming the configuration of a real product.

## 4. Resilience, recovery, and residual risk

The capstone must say both what is protected and what is not. This is more credible than simply listing redundant components.

For each major service or component, identify:

- The failure considered.
- The control: A/B power, redundant network path, backup, replication, cluster, monitoring, or documented recovery procedure.
- What the control protects.
- What it does not protect.
- How the control would be validated.
- The residual risk and owner.

Examples:

- Dual PSUs on independent feeds can protect against one PSU or one power-path failure, but may not protect a full rack, site, or application failure.
- A backup can support recovery from deletion or corruption, but needs a tested restore path and may not meet a near-zero RPO.
- Monitoring may detect a problem, but it does not prevent the problem or guarantee customer impact is known.

The purpose is not to make the design perfect. The purpose is to demonstrate that she understands trade-offs and avoids overclaiming.

## 5. Operations runbooks, controlled change, and validation

The capstone runbook should be a short navigation document, not a copy of the earlier workbooks. It should say:

- How to identify the environment and authorize work.
- Which prior runbook to use for Linux health, physical evidence, hardware, network, or incident response.
- The first-response order for a common alert.
- What requires a change, service-owner validation, or escalation.
- What evidence needs to be collected.
- What not to do without approval.

Use one controlled change as an example, such as installing a server or replacing a non-redundant cable. Include preparation, affected services, pre-checks, target verification, execution, stop conditions, validation, rollback, communication, and closure. A well-written change plan does not grant permission by itself; the required approvals still matter.

## 6. The operational ticket pack

The four ticket examples should share a common evidence structure while being specific to their task:

| Ticket | Task-specific evidence |
|---|---|
| Rack a new server | Asset tag, U position, rails, power map, cable labels, physical and remote validation |
| Replace failed disk | Correct drive bay and serial, controller or RAID evidence, approved replacement, rebuild monitoring, service impact and owner |
| Troubleshoot link down | Cable labels, port map, LEDs, scope, safe boundaries before reseat or replacement, network-owner validation |
| Decommission server | Service retirement approval, data-handling confirmation, cable and power trace, asset status, chain of custody, disposal or return evidence |

Every ticket should contain acknowledgement, scope, actions, evidence, changes or no changes, validation, risk, next owner, and closure or handover. Do not create four identical forms with different titles; show the evidence that matters to each technical scenario.

## 7. Integrated incident and handover

Choose one scenario that requires dependency thinking rather than a single obvious fix. For example:

    Several application VMs become slow. A datastore-latency alert and an application timeout appear close together. A recent maintenance activity is listed, but the cause is not confirmed.

The incident pack should include:

- First-five-minutes triage.
- Impact and scope statement.
- Timestamped evidence and hypothesis log.
- Cross-layer dependency and owner map.
- Status updates and escalation packet.
- An approved mitigation or decision record, if the scenario provides one.
- Recovery validation that distinguishes service restoration from root-cause confirmation.
- Shift handover and blameless review outline.

State uncertainty honestly. A polished incident document that claims a cause without evidence is less useful than a concise one that shows the next safe test and owner.

## 8. Documentation quality and portfolio publishing

Review the portfolio as another technician or hiring manager would:

- Can they find the capstone scope and main diagrams in under a minute?
- Do asset tags, hostnames, rack positions, switch ports, cable labels, PDU outlets, and ticket dates agree?
- Do arrows in diagrams show the intended direction and dependency?
- Do links work, headings make sense, and tables have clear units or assumptions?
- Are facts, assumptions, and future improvements labelled separately?
- Is sensitive information removed?
- Does every technical claim have a link to an artifact or a clear explanation?

Portfolio publication should be deliberate. A private repository, shared folder, or PDF may be appropriate. If publishing online, remove sensitive material and include a short statement that the environment is fictional or lab-based.

## 9. Capstone presentation

The 8-10 minute presentation should be simple and structured:

1. Purpose and scope: what the environment supports and what is fictional or lab-tested.
2. Physical architecture: rack, power, airflow, and cabling.
3. Logical architecture: hosts, VMs or services, network, storage, and monitoring.
4. Operational approach: one change, one ticket, one incident, and validation.
5. Resilience and residual risk: what the design protects and what it does not.
6. Learning and next steps: what she would improve with further training or production guidance.

Use the diagrams to tell the story. Do not read every label. Finish with a concise statement of what the portfolio proves: safe judgment, documentation, troubleshooting structure, and readiness to learn in a real operations team.

## 10. Evidence-based CV and LinkedIn

An early-career CV should be direct, accurate, and easy for a recruiter or hiring manager to scan. Use a simple, single-column layout with contact details, concise profile, skills, education or certifications, relevant work experience, and a clearly labelled projects or lab-portfolio section.

Use truthful headings such as:

    Hands-on Infrastructure Lab Portfolio

Good project bullets combine action, environment, evidence, and outcome:

- Built and documented a fictional 42U data-center rack with asset inventory, A/B power mapping, port records, and a controlled rack-and-stack procedure.
- Practised safe Linux health evidence collection in an Ubuntu lab, including service state, logs, disk, memory, and network checks.
- Produced incident timelines, escalation packets, and post-incident reviews for simulated hardware, network, and service scenarios.
- Mapped virtualized service dependencies, recovery controls, failure domains, and monitoring evidence in a structured lab portfolio.

Do not say that the lab was a paid role, a production deployment, or an earned certification if it was not. On LinkedIn, use a focused headline, a short About section, relevant skills, a project entry, and a portfolio link if comfortable. Do not expose sensitive work or personal information.

## 11. Job-description analysis and application tailoring

For each role, extract:

- Title, work location, shift or on-call expectation, and eligibility requirements.
- Hardware, Linux, networking, ticketing, physical-operation, cloud, or monitoring keywords.
- Required experience versus preferred experience.
- Certifications, safety, communication, customer, and documentation expectations.

Create a skills-evidence matrix:

| Role requirement | Honest evidence | Artifact | Confidence | Learning action |
|---|---|---|---|---|
| | | | | |

Tailor the CV summary and selected portfolio bullets to the role. Do not copy every job-description keyword if it cannot be supported. If a requirement is a gap, name a short, credible learning action rather than pretending it is complete.

## 12. Behavioural and technical interview practice

Use STAR: situation, task, action, result. Lab examples are valid if labelled honestly:

- "In my structured lab project, I found that two records were inconsistent..."
- "During a simulated remote-hands task, I paused because the cable label did not match the port map..."
- "While building the capstone, I improved the evidence and handover section after identifying a missing validation owner..."

For technical questions, use a clear answer pattern:

1. Confirm scope or define the term.
2. Explain the safe first checks and evidence.
3. State the authorization or escalation boundary.
4. Explain validation and documentation.

It is acceptable to say, "I have not performed that in production, but in my lab I learned the workflow, and in a live environment I would follow the approved runbook and escalate to the owner." That answer is more credible than an invented story.

---

# Part 2: Week 8 questions and model answers

## Capstone, evidence, and documentation

### 1. What is the purpose of the capstone?

It demonstrates how the learner connects earlier knowledge into one consistent, safe, and explainable operations environment. It should show practice and judgment without pretending to be production experience.

### 2. Why use a fictional environment?

It allows realistic documentation without exposing customer, employer, facility, or access information.

### 3. What should a capstone scope statement include?

Purpose, audience, fictional or lab-tested elements, assumptions, in-scope systems, out-of-scope systems, confidentiality rules, and limitations.

### 4. Why is a source of truth important?

It identifies which record should be trusted and updated when documentation differs. This prevents technicians from acting on guesswork.

### 5. What should happen if a rack elevation and port map disagree?

Record the discrepancy, stop any risky action, identify the authoritative record through the owner or process, correct the affected documentation, and preserve the review evidence.

### 6. Why should diagrams be split into physical and logical views?

Each view has different information. Separate diagrams are easier to read and reduce the risk of hiding important details in one crowded page.

### 7. What makes a portfolio artifact credible?

It has a clear scope, consistent identifiers, stated assumptions, evidence of the learner's reasoning, safe boundaries, and an outcome or review note.

### 8. What should never appear in a public portfolio?

Credentials, private keys, customer data, unapproved screenshots, exact facility information, access-control details, live IP addresses, serials, or restricted ticket data.

### 9. Why should assumptions be labelled?

Readers can distinguish lab facts from fictional design choices and assess the work honestly.

### 10. What is traceability?

The ability to follow an item or service across records, such as linking a hostname to its asset tag, rack position, power feeds, ports, owner, tickets, and dependencies.

## Resilience, operation, and tickets

### 11. What should a resilience map show?

The failure considered, controls in place, what they protect, their limitations, validation evidence, residual risk, and owner.

### 12. Does A/B power make a service fully resilient?

No. It can protect specific power-path failures but not every rack, site, network, storage, application, or data failure.

### 13. Why is a tested restore more meaningful than a successful backup job?

A restore test provides evidence that data and procedures can actually recover the required service.

### 14. What is the purpose of a capstone operations runbook?

It navigates a technician to the right prior runbook, states the first-response order, and identifies boundaries, evidence, owners, and validation without duplicating every procedure.

### 15. Does a written change plan authorize the work?

No. The required approvals and maintenance conditions still need to be in place.

### 16. What makes a rack-new-server ticket different from a link-down ticket?

The shared structure is similar, but the installation ticket needs asset, rails, power, and placement evidence while the link ticket needs port, label, LED, scope, and network-validation evidence.

### 17. What should be verified before a failed disk is replaced?

Correct device, disk bay, asset or serial evidence, controller or RAID status, approved replacement part, change authority, and rebuild monitoring plan.

### 18. What makes decommissioning complete?

Service retirement and data-handling confirmation, physical removal, record updates, chain of custody, and disposal or return evidence all need to agree.

### 19. What is service validation?

Evidence that the required outcome works for the appropriate owner or user, rather than only that a physical component looks healthy.

### 20. Why state residual risk after a change?

It tells the next owner what remains exposed and prevents a temporary or partial result from being described as complete.

### 21. What should an incident pack show?

Scope, impact, facts, hypotheses, timeline, evidence, owners, updates, escalation, approved decisions, validation, handover, and improvement actions.

### 22. Why not claim root cause in the capstone incident without evidence?

It demonstrates poor incident judgment. A clear unknown plus next safe step is stronger than a speculative explanation.

### 23. What is the value of a documentation quality review?

It finds inconsistent identifiers, unclear assumptions, broken links, and gaps before someone relies on the material.

### 24. What should the capstone presentation demonstrate?

That she can explain scope, architecture, operations, risk, and evidence in a concise, honest way.

## CV, applications, and behavioural interviews

### 25. How should she label lab work on a CV?

Use a heading such as Hands-on Infrastructure Lab Portfolio or Projects, not an employment title.

### 26. What makes a CV bullet evidence-based?

It says what she did, the environment or scope, and a concrete artifact or outcome without inflated claims.

### 27. Should she claim a certification she is studying for?

No. She can state "studying toward" only if that is true, but should not claim certification until earned.

### 28. Why tailor a CV for a job description?

It helps the reader see the most relevant honest evidence quickly and shows that she understands the role.

### 29. What should she do with a skill gap?

Name it honestly, map adjacent evidence, and state a specific learning action or certification goal.

### 30. What is a skills-evidence matrix?

A table that maps a role requirement to actual proof, an artifact, confidence level, and next learning action.

### 31. What should a LinkedIn headline communicate?

The target role and the most relevant skills or focus areas, without exaggerated seniority or fabricated experience.

### 32. Why keep public portfolio content sanitized?

It demonstrates security awareness and protects people, systems, and employers.

### 33. What is STAR?

Situation, task, action, and result: a structure for giving clear behavioural answers.

### 34. Can a lab scenario be used in a behavioural interview?

Yes, if she clearly says it was a lab, capstone, or simulated exercise and describes what she actually did.

### 35. What should she say if she has not done a task in production?

Say so honestly, describe relevant lab practice and safe workflow, then explain that she would follow the approved runbook and seek the correct guidance in production.

### 36. What is a good answer structure for a technical scenario?

Confirm scope, state safe evidence checks, explain authorization or escalation boundaries, then state validation and documentation.

### 37. How should she answer "What is your biggest weakness?"

Choose a real but non-disqualifying development area, explain the practical steps she is taking to improve it, and give evidence of progress.

### 38. How should she answer "Why data center operations?"

Connect interest in reliable systems, practical troubleshooting, safety, documentation, team coordination, and the satisfaction of keeping services available.

### 39. What should she do if an interviewer asks a question she does not know?

Clarify the scenario if needed, state what she knows, describe the safe method she would use to verify it, and avoid pretending certainty.

### 40. Why rehearse a presentation aloud?

It reveals unclear explanations, missing assumptions, rushed timing, and questions that need better evidence.

### 41. What makes a mock interview useful?

Specific feedback on accuracy, structure, safety, evidence, honesty, and communication, followed by another attempt.

### 42. How can she explain shift-work readiness?

She can speak about reliability, handover discipline, planning personal routines, staying alert, and communicating early if an issue affects the next shift.

### 43. How should she handle a request that looks unsafe in an interview scenario?

Pause, confirm scope and authorization, explain the risk, and escalate or request a documented clarification instead of improvising.

### 44. How can she demonstrate attention to detail?

Use a concrete lab example, such as reconciling a port map and label, validating asset identifiers, or correcting a documentation inconsistency before a change.

### 45. What should she say about a mistake in a lab?

State the fact, how she stopped further risk, corrected it, documented the learning, and changed her checklist or process to prevent recurrence.

### 46. How can she explain hands-on experience honestly?

Describe the specific lab environments, artifacts, simulations, and practice completed, then distinguish them from paid production work.

### 47. Why is it valuable to show a portfolio in an interview?

It turns general claims into concrete evidence and gives the interviewer an easy way to explore the candidate's reasoning and communication.

### 48. What should she do after a mock interview?

Record weak answers, improve the evidence or structure, practise aloud again, and keep a small list of questions that need more study.

### 49. What should she be able to do at the end of Week 8?

Present a consistent technical portfolio, communicate it honestly, tailor it to a role, and demonstrate safe judgment in technical and behavioural interviews.

---

# Part 3: Lab exercises with hints

## Lab 1: Audit earlier artifacts and define the capstone

### Goal

Choose what to reuse, improve, or create without duplicating the previous seven weeks.

### Steps

1. List each Week 1-7 artifact and mark it Reuse, Improve, Link, or Do not include.
2. Define a fictional environment, audience, scope, assumptions, and confidentiality rules.
3. Choose consistent names for one rack, switches, PDUs, hosts, VMs, services, and storage.
4. State limitations such as single-rack or single-site risk.
5. Create a README index with links to the main artifacts.

### Hints

- Fewer coherent artifacts are better than many disconnected files.
- Make all fictional identifiers obvious.

### Expected portfolio output

01-capstone-scope-and-assumptions.md

## Lab 2: Build an evidence inventory and source-of-truth record

### Goal

Make it easy to trace any device or service to the correct records.

### Steps

1. Create a table for hostname, asset tag, role, rack/U, power feeds, switch ports, service dependency, owner, and document links.
2. Assign an authoritative source for rack position, asset lifecycle, port mapping, power mapping, and incident record.
3. Introduce one deliberate mismatch and document how it would be resolved.
4. Record a document review date and owner.

### Hints

- Do not use real identifiers from a workplace or personal network.

### Expected portfolio output

02-evidence-inventory-and-source-of-truth.md

## Lab 3: Build the final architecture and asset inventory

### Goal

Create a readable physical and logical architecture pack.

### Steps

1. Build a rack elevation with devices, PDUs, airflow direction, and empty-space assumptions.
2. Build a power map for dual-PSU servers.
3. Build a network port map with cable labels.
4. Build a service dependency diagram with application, database, monitoring, host, storage, and customer entry point.
5. Reconcile each identifier against the source-of-truth record.

### Hints

- Use separate diagrams if one page becomes crowded.
- Every hostname should mean the same thing in every artifact.

### Expected portfolio output

03-final-architecture-and-asset-inventory.md

## Lab 4: Create a service-dependency, resilience, and risk map

### Goal

Show both protection and limitation.

### Steps

1. Choose three key services or components.
2. List their dependencies, relevant failure domains, existing controls, validation evidence, and residual risks.
3. Add at least one risk that is intentionally not solved by the fictional design.
4. Give each risk an owner and recommended improvement.

### Hints

- A credible design has documented limits.

### Expected portfolio output

04-service-dependency-resilience-and-risk-map.md

## Lab 5: Write the integrated operations runbook

### Goal

Create a concise first-response and navigation guide.

### Steps

1. Link to the relevant prior runbooks for Linux, hardware, network, physical work, and incidents.
2. Add an ordered first-response flow for a generic service alert.
3. State authorization, evidence, validation, handover, and escalation boundaries.
4. Add a short "Do not do" list for unapproved reboots, cable changes, service restarts, deletions, and access bypasses.

### Hints

- The aim is navigation, not copying dozens of commands.

### Expected portfolio output

05-integrated-operations-runbook.md

## Lab 6: Write a change plan and validation record

### Goal

Show controlled work end to end.

### Scenario

Install a new dual-PSU application server in the fictional rack, with remote service-owner validation after physical installation.

### Steps

1. Include scope, approvals, maintenance window, affected services, asset and rack checks, power and port mapping, lifting and safety, and communications.
2. Define execution steps, stop conditions, rollback, validation, and closure records.
3. Write the implementation and closure updates.
4. Cross-check all identifiers against your architecture pack.

### Hints

- A document is not an approval; record the required approval placeholder.

### Expected portfolio output

06-change-plan-and-validation-record.md

## Lab 7: Complete the rack-new-server ticket

### Goal

Demonstrate safe physical installation evidence.

### Steps

1. Write acknowledgement, target verification, and pre-work baseline.
2. Include asset tag, rack/U, rails, power-feed mapping, cable labels, and cleanliness or airflow check.
3. State physical validation and remote service-owner validation separately.
4. Update inventory, rack elevation, port map, and power map.
5. Write a closure or handover note.

### Hints

- Do not write "all good" without specifying who validated what.

### Expected portfolio output

07-ticket-rack-new-server.md

## Lab 8: Complete the failed-disk replacement ticket

### Goal

Demonstrate controlled component replacement reasoning.

### Steps

1. Identify the correct host, controller evidence, drive bay, affected disk, and approved replacement.
2. Include data and redundancy risk, change authority, and stop conditions.
3. State the expected rebuild or service-owner monitoring evidence.
4. Write an escalation if controller information and physical bay labels do not match.
5. Close only after the required validation is complete or hand over the remaining monitoring.

### Hints

- Do not claim a RAID rebuild is complete merely because a disk was inserted.

### Expected portfolio output

08-ticket-replace-failed-disk.md

## Lab 9: Complete the link-down ticket

### Goal

Demonstrate careful physical and logical network boundaries.

### Steps

1. Record target service, host, expected port, cable label, LEDs, port-map evidence, and affected scope.
2. State what can be observed without changing anything.
3. Define the approval needed before reseating, replacing, or moving a cable.
4. Write the escalation request to the network owner if records differ.
5. State validation from the service or network owner.

### Hints

- Do not use cable color or proximity as the only evidence.

### Expected portfolio output

09-ticket-troubleshoot-link-down.md

## Lab 10: Complete the decommission-server ticket

### Goal

Demonstrate secure lifecycle control.

### Steps

1. Confirm service retirement, change approval, owner, data-handling confirmation, and asset identity.
2. Trace network and power connections before removal.
3. Record physical removal, retained parts, asset lifecycle update, chain of custody, and disposal or return route.
4. State any missing confirmation that blocks completion.
5. Write a closure note that separates physical removal from data sanitization evidence.

### Hints

- A powered-off server is not automatically safe to dispose of.

### Expected portfolio output

10-ticket-decommission-server.md

## Lab 11: Run an integrated incident and handover

### Goal

Show calm, dependency-aware incident communication.

### Scenario

At 13:00, several application VMs are slow. A datastore-latency alert and application timeouts appear near the same time. A platform maintenance activity completed earlier, but no root cause is confirmed.

### Steps

1. Complete first-five-minutes triage and scope.
2. Build a fact, hypothesis, dependency, and owner log.
3. Write initial, progress, and next-update messages.
4. Draft escalations for platform, storage, and service owners.
5. Define recovery validation and an active-incident handover.
6. Write a blameless review outline with corrective actions that do not assume a root cause.

### Hints

- Use links to Week 6 and Week 7 templates rather than copying all of them.

### Expected portfolio output

11-integrated-incident-and-handover.md

## Lab 12: Perform a documentation quality review

### Goal

Find and correct inconsistencies before sharing the portfolio.

### Steps

1. Check every hostname, asset tag, rack/U, switch port, cable label, PDU outlet, feed, date, and ticket status.
2. Check diagram arrows, link targets, headings, tables, and terminology.
3. Check that each claim is labelled as lab-tested, fictional, or assumed as appropriate.
4. Check that no sensitive data is included.
5. Record every correction and remaining known limitation.

### Hints

- Read the portfolio as a new technician who has never seen it before.

### Expected portfolio output

12-documentation-quality-review.md

## Lab 13: Write and rehearse the capstone presentation

### Goal

Explain the capstone clearly in 8-10 minutes.

### Steps

1. Write a six-part outline: scope, physical design, logical design, operations, resilience/risk, and learning/next steps.
2. Select only the diagrams needed to support the story.
3. Prepare answers to five likely follow-up questions.
4. Deliver the presentation aloud, time it, and improve it after one review.
5. Note any question that revealed a weak artifact and correct it.

### Hints

- Aim for clarity, not speed or exhaustive detail.

### Expected portfolio output

13-capstone-presentation-notes.md

## Lab 14: Create a role-targeted CV and LinkedIn draft

### Goal

Turn the capstone into an honest hiring package.

### Steps

1. Draft a concise CV with profile, skills, education or certifications, experience, and lab portfolio section.
2. Create four evidence-based project bullets.
3. Draft a LinkedIn headline, About section, and project description.
4. Remove claims that cannot be evidenced.
5. Check that no sensitive technical details are included.

### Hints

- Use "studying toward" only for an active learning goal, not as a substitute for certification.

### Expected portfolio output

14-role-targeted-cv.md

## Lab 15: Build a skills-evidence matrix and interview script

### Goal

Tailor the portfolio and prepare truthful examples.

### Steps

1. Select two suitable entry-level role descriptions.
2. Extract requirements and map each to evidence, artifact, confidence, and learning action.
3. Write five STAR stories from real lab work.
4. Write answers for tell-me-about-yourself, why this role, hands-on experience, unsafe request, learning gap, and a technical incident scenario.
5. Score each answer for accuracy, safety, evidence, honesty, and clarity.

### Hints

- Do not say you did production work if the evidence is from a lab.

### Expected portfolio output

15-job-description-skill-matrix-and-linkedin.md and 16-star-story-bank-and-interview-script.md

## Lab 16: Final Week 8 self-assessment and next steps

### Goal

Decide what is ready to show and what needs further practice.

### Steps

1. Complete the self-assessment table.
2. List the three strongest artifacts to show in an interview.
3. List three targeted skills to improve over the next 30, 60, and 90 days.
4. Create a simple application tracker with role, date, evidence used, follow-up, and learning gap.
5. Review every technical claim on the CV and confirm the evidence.

### Hints

- A focused next-step plan is more credible than claiming to know everything.

### Self-assessment table

| Skill | Can do without notes | Can do with notes | Need more practice |
|---|---|---|---|
| Explain the capstone scope and assumptions | | | |
| Trace a service from user to rack and facility | | | |
| Reconcile asset, rack, power, and port records | | | |
| Explain resilience controls and residual risks | | | |
| Use earlier runbooks through an integrated operations guide | | | |
| Write task-specific ticket evidence | | | |
| Run a safe incident tabletop and handover | | | |
| Deliver an 8-10 minute presentation | | | |
| Explain lab experience honestly on a CV | | | |
| Tailor evidence to a job description | | | |
| Answer behavioural questions with STAR examples | | | |
| State a skills gap and learning plan confidently | | | |

### Expected portfolio output

17-week-08-self-assessment-and-next-steps.md

---

# Part 4: Templates to copy into the portfolio

## Capstone README and scope template

    # Mini Data Center Operations Capstone

    ## Purpose

    ## Audience

    ## Environment summary

    ## Fictional, lab-tested, and diagram-only elements

    ## Assumptions

    ## Out of scope

    ## Confidentiality and sanitization statement

    ## Main artifacts

    ## Known limitations and next improvements

## Source-of-truth and consistency audit template

| Item | Identifier | Authoritative record | Related records | Checked date | Match? | Correction or owner |
|---|---|---|---|---|---|---|
| Hostname | | | | | Yes / No | |
| Asset tag | | | | | Yes / No | |
| Rack/U | | | | | Yes / No | |
| Switch port | | | | | Yes / No | |
| Power feed | | | | | Yes / No | |

## Resilience and risk register

| Service or component | Dependency / failure domain | Control | Validation evidence | Residual risk | Owner | Recommended improvement |
|---|---|---|---|---|---|---|
| | | | | | | |

## Integrated change and validation template

    # Controlled Change and Validation

    Ticket/change:
    Task:
    Environment:
    Approval and maintenance window:
    Affected services and dependencies:
    Target identifiers:

    ## Pre-checks and baseline

    ## Execution steps

    ## Stop conditions

    ## Rollback and owner

    ## Validation and owner

    ## Evidence and record updates

    ## Closure or handover

## Skills-evidence matrix

| Job requirement | Honest evidence | Artifact link | Confidence | Safe CV/interview wording | Learning action |
|---|---|---|---|---|---|
| | | | | | |

## STAR story builder and interview scorecard

    # STAR Story

    Question:
    Situation:
    Task:
    Action:
    Result:
    Evidence:
    Lesson:
    Honest lab or production wording:

| Answer | Accuracy | Structure | Safety mindset | Evidence | Honesty | Clarity | Improvement action |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

## Application tracker

| Role | Organization | Date applied | Key evidence used | Follow-up date | Outcome | Skill gap or next action |
|---|---|---|---|---|---|---|
| | | | | | | |

---

# Part 5: Week 8 final exam

## Written exam

Answer these without looking at notes:

1. Explain the scope and limitations of your capstone.
2. Explain how you keep identifiers consistent across records.
3. Trace one service from user entry point to rack and facility dependencies.
4. Explain one protection and one residual risk for that service.
5. Explain why A/B power does not solve every failure domain.
6. Describe the evidence needed for each of the four capstone tickets.
7. Explain the difference between physical completion and service validation.
8. Explain how you would handle an incident without claiming an unproven root cause.
9. Explain what information must be removed from a public portfolio.
10. Write two evidence-based CV bullets from the capstone.
11. Explain how you would tailor a portfolio to a job description.
12. Give a truthful answer about experience you have not yet gained in production.
13. Describe your 30/60/90-day learning plan.

## Practical final

Complete these tasks:

1. Deliver the 8-10 minute capstone presentation.
2. Answer follow-up questions about rack location, A/B power, a port map, storage or virtual dependency, and a residual risk.
3. Correct one deliberate mismatch between the inventory and another capstone record.
4. Write a concise ticket update for a new incident scenario.
5. Show how the update links to the correct runbook, owner, and validation method.
6. Present the CV and explain the evidence behind every technical claim.
7. Answer one technical scenario and two behavioural questions using honest lab examples.

## Passing standard

She passes Week 8 if she can:

- Present a concise, internally consistent capstone.
- Locate and reconcile physical, logical, and operational records.
- Explain safety, validation, escalation, resilience, and residual risk.
- Show task-specific evidence for common data-center tickets.
- Handle an ambiguous incident with facts, dependencies, and clear ownership.
- Describe lab work accurately without overstating production experience.
- Tailor her evidence to a role and communicate it clearly in an interview.
- Identify practical next steps for continued learning.

---

# Part 6: Interview positioning for Week 8

Week 8 is the handoff from learning to applying. The candidate should use the capstone as proof of work, not as a substitute for honesty. She can show that she is ready to contribute safely, learn site-specific procedures quickly, and communicate like a reliable operations teammate.

## Strong interview themes

- I have a structured lab portfolio that connects hardware, networking, Linux, physical operations, incidents, and service dependencies.
- I document work so another technician can verify the target, actions, evidence, validation, and next step.
- I understand the difference between a safe lab exercise and a production change.
- I can identify redundancy, failure domains, and the limits of a design.
- I use source-of-truth records and stop when labels, diagrams, and tickets do not agree.
- I can explain a technical task plainly and ask precise questions when a detail is missing.
- I am actively building the skills needed for data-center operations and know when to escalate.

## Example answer: tell me about yourself

"I am building toward an entry-level data-center operations role through a structured hands-on infrastructure lab portfolio. I have practised Linux health checks, server hardware and networking fundamentals, rack and power documentation, controlled ticket updates, incident escalation, and a capstone that maps a fictional service from rack hardware to virtualized dependencies. I am especially interested in work where careful procedures, documentation, and teamwork keep services reliable. I am looking for a role where I can apply that foundation, follow site-specific processes, and keep learning from experienced engineers."

## Example answer: what hands-on experience do you have?

"My hands-on experience is from a structured lab, so I would describe it accurately as lab practice rather than production work. I built an Ubuntu environment for health checks, created rack elevations, A/B power maps, cable and port records, and ran simulated tickets for server installation, disk replacement, link troubleshooting, and decommissioning. I also created incident timelines and escalation packs. The main habits I developed are verifying the target, using evidence, documenting what changed, and pausing when a task needs approval or another team's expertise."

## Example answer: what would you do if you did not know?

"I would first make sure the target and request are clear, then check the approved documentation or runbook and ask a precise question rather than guessing. If the action changes state, affects production, or is outside my authority, I would pause and escalate to the right owner. I would record what I observed and what I need next so the work can continue safely."

## Example answer: why data center operations?

"I enjoy the combination of physical systems and service reliability. A data center technician's work is practical, but it also requires careful thinking: one cable, power path, or document can affect a much larger service. I like the discipline of verification, clear handovers, and working with engineers to solve problems safely. My capstone helped me see how hardware, Linux, networks, monitoring, and customer impact fit together."

---

# Part 7: Week 8 completion checklist

- [ ] I created a Week 8 capstone portfolio folder and README.
- [ ] I defined what is fictional, lab-tested, assumed, and out of scope.
- [ ] I sanitized the portfolio of sensitive information.
- [ ] I created an evidence inventory and named authoritative records.
- [ ] I created consistent physical, power, network, service, and risk diagrams.
- [ ] I reconciled hostnames, asset tags, U positions, ports, PDU outlets, and feeds.
- [ ] I documented resilience controls and residual risks honestly.
- [ ] I created an integrated operations runbook that links to earlier evidence.
- [ ] I created a controlled change plan with validation and rollback.
- [ ] I completed the rack-new-server ticket.
- [ ] I completed the failed-disk replacement ticket.
- [ ] I completed the link-down ticket.
- [ ] I completed the decommission-server ticket.
- [ ] I completed an integrated incident and handover pack.
- [ ] I performed a documentation quality review.
- [ ] I wrote and rehearsed an 8-10 minute capstone presentation.
- [ ] I created an honest, role-targeted CV and LinkedIn draft.
- [ ] I created a skills-evidence matrix for selected roles.
- [ ] I created truthful STAR stories and completed a mock interview.
- [ ] I completed the final assessment and 30/60/90-day next steps.
