# Week 6 Detailed Workbook: Troubleshooting, Incidents, and Escalation

## Table of contents

- [Purpose of this workbook](#purpose-of-this-workbook)
- [Week 6 target level](#week-6-target-level)
- [Scope boundary: what is new this week](#scope-boundary-what-is-new-this-week)
- [Suggested weekly schedule](#suggested-weekly-schedule)
- [Day-by-day Week 6 study order](#day-by-day-week-6-study-order)
- [Required Week 6 portfolio artifacts](#required-week-6-portfolio-artifacts)
- [Part 1: Comprehensive Week 6 topics](#part-1-comprehensive-week-6-topics)
- [Part 2: Week 6 questions and model answers](#part-2-week-6-questions-and-model-answers)
- [Part 3: Lab exercises with hints](#part-3-lab-exercises-with-hints)
- [Part 4: Templates to copy into the portfolio](#part-4-templates-to-copy-into-the-portfolio)
- [Part 5: Week 6 final exam](#part-5-week-6-final-exam)
- [Part 6: Interview positioning for Week 6](#part-6-interview-positioning-for-week-6)
- [Part 7: Week 6 completion checklist](#part-7-week-6-completion-checklist)

## Purpose of this workbook

This workbook expands Week 6 of the Data Center Engineer / Data Center Technician study plan. It teaches the decision-making and communication layer that sits above individual hardware, network, Linux, and physical-work checks.

Weeks 2-5 taught what a technician can inspect. This week teaches how to behave when the evidence is incomplete and the impact may be urgent: establish scope, preserve safety, form testable hypotheses, use the least risky check first, communicate a useful update, bring in the right resolver group, and leave a clean record for the next shift.

The goal is not to make the learner a sole incident commander or a senior root-cause investigator. The goal is to make her a dependable junior participant in an incident: calm, structured, evidence-led, and clear about her authorization boundary.

## Week 6 target level

The target is not "I can list troubleshooting commands." The target is:

- She can distinguish an alert, incident, change, problem, workaround, mitigation, recovery, and root-cause investigation in operational context.
- She can start an incident record with the correct time, target, reporter, impact, scope, known facts, and safety checks.
- She can separate facts, hypotheses, assumptions, and actions in her notes.
- She can use a repeatable sequence: stabilize, define, scope, collect evidence, hypothesize, test safely, mitigate or recover with approval, validate, document, and hand over.
- She can think across physical, power, hardware, network, operating-system, service, and dependency fault domains without assuming the first symptom is the cause.
- She can choose read-only or reversible checks before proposing a state-changing action.
- She can write an escalation packet that gives the next team usable facts and a precise request.
- She can keep an incident timeline and provide factual stakeholder updates at an agreed cadence.
- She can distinguish service restoration from proof of root cause.
- She can participate in a blameless post-incident review and track corrective actions without blaming people.

## Scope boundary: what is new this week

This is a synthesis module. It deliberately does not repeat basic server anatomy, subnetting, Linux command primers, fiber types, or rack installation steps. Use the earlier workbooks when a scenario needs those checks.

| Earlier knowledge | Week 6 adds |
|---|---|
| Hardware, network, Linux, and physical checklists | A safe order for selecting and correlating those checks |
| Ticket lifecycle and change basics | Incident scope, severity, update cadence, escalation, and shift continuity |
| Evidence collection | Evidence quality, timestamps, hypothesis logs, and decision records |
| Service restart or cable-change boundaries | Approved containment, rollback, validation, and emergency-change discipline |
| Handover notes | Active-incident handover with knowns, unknowns, risks, owner, and next update |

Do not simulate disruptive tests on production. For labs, use a VM, home network, fictional evidence, or a tabletop exercise.

## Suggested weekly schedule

| Day | Focus | Main output |
|---|---|---|
| Day 1 | Incident terms in context, impact, scope, first-five-minutes triage | Classification matrix and triage card |
| Day 2 | Fault domains, evidence quality, hypotheses, and low-risk testing | Evidence source log and hypothesis worksheet |
| Day 3 | Severity, timelines, stakeholder updates, and escalation | Incident timeline, status updates, and escalation packet |
| Day 4 | Multi-domain incident simulations, containment, recovery, validation, and handover | End-to-end incident record |
| Day 5 | Blameless review, corrective actions, interview practice, and assessment | Post-incident review and interview script |
| Day 6 optional | Run a new tabletop scenario without notes | Improved decision log |
| Day 7 optional | Rest or catch-up | Clean Week 6 portfolio |

## Day-by-day Week 6 study order

| Day | Study sections | Practice | Portfolio output |
|---|---|---|---|
| Day 1 | Sections 1-4: incident mindset, operational terms, first-five-minutes actions, impact, scope, severity, and priority | Labs 1-2; Questions 1-12 | Classification matrix and triage card |
| Day 2 | Sections 5-8: method, evidence, fault domains, hypotheses, and correlation | Labs 3-5; Questions 13-25 | Evidence bundle, source log, and server-unreachable simulation |
| Day 3 | Sections 9-11: containment, escalation, updates, timelines, and coordination | Labs 6-9; Questions 26-36 | Timeline, update pack, and cross-team escalation notes |
| Day 4 | Sections 12-13: recovery validation, handover, post-incident review, and action tracking | Labs 10-12; Questions 37-45 | Decision record, handover, PIR, and action register |
| Day 5 | Section 14: professional behavior under pressure and interview preparation | Labs 13-16; Questions 46-55 | Mock incident updates, interview script, final tabletop, and self-assessment |
| Day 6 optional | Re-run a scenario using only the triage card and templates | Repeat Labs 5, 7, and 12 | Timed incident evidence pack |
| Day 7 optional | Rest or catch-up | Complete missing artifacts | Ready-to-review Week 6 portfolio |

## Required Week 6 portfolio artifacts

Create a folder called week-06-incidents-escalation and include:

    week-06-incidents-escalation/
      README.md
      01-incident-classification-and-severity-matrix.md
      02-first-five-minutes-triage-card.md
      03-evidence-source-and-hypothesis-log.md
      04-fault-domain-troubleshooting-flow.md
      05-server-unreachable-incident-simulation.md
      06-link-down-and-wrong-cabling-simulation.md
      07-hardware-or-power-alert-simulation.md
      08-environmental-or-access-escalation-note.md
      09-incident-timeline-and-status-updates.md
      10-cross-team-escalation-packet.md
      11-decision-mitigation-and-validation-record.md
      12-active-incident-handover.md
      13-blameless-post-incident-review.md
      14-mock-incident-ticket-updates.md
      15-week-06-interview-script.md
      16-week-06-self-assessment.md

---

# Part 1: Comprehensive Week 6 topics

## 1. A calm incident mindset

An incident is not a test of who can type fastest. It is a controlled effort to protect people and service, reduce uncertainty, restore the right outcome, and preserve a record that others can trust.

The first priorities are:

1. Safety and security: stop and escalate smoke, water, electrical danger, physical-security concerns, or unsafe instructions.
2. Correct identity: confirm the incident, asset, site, rack, hostname, service, and environment.
3. Impact and scope: identify what is affected and whether redundancy or broader services may be at risk.
4. Evidence and communication: start a timeline, record facts, and tell the right people what is known.

Avoid panic actions such as rebooting, moving cables, clearing logs, or changing configuration simply because the alert is urgent. A fast but unapproved action can expand the outage and erase evidence.

## 2. Operational terms in context

Week 1 introduced core service-management terms. In an active incident, their distinction guides the next action.

| Term | Practical meaning |
|---|---|
| Event or alert | A signal that needs interpretation; it is not automatically a customer-impacting incident |
| Incident | An unplanned interruption or reduction in service that needs coordinated response |
| Service request | A planned ask, such as access or a standard install, which is not an incident by itself |
| Change | An authorized alteration to an environment; it can be related to an incident but does not replace incident handling |
| Problem | The underlying cause of one or more incidents, often investigated after restoration |
| Workaround | A temporary way to avoid or reduce the symptom |
| Mitigation | An approved action that reduces impact or stabilizes the situation |
| Recovery | Return of the required service level, confirmed by suitable validation |
| Root cause | A confirmed causal explanation, not a guess made from the first symptom |

Use the local process. A technician may supply the facts that support a major-incident declaration without being the person who formally declares it.

## 3. The first five minutes

The first five minutes should create order, not a rushed fix. Start a short triage record:

- Incident or ticket identifier and current time zone.
- Reporter, monitoring source, or customer contact.
- Exact reported symptom and when it started or was detected.
- Affected service, host, rack, user group, or location.
- Current impact and whether redundancy is degraded.
- Recent approved changes or known maintenance work.
- Immediate safety, access, or environment concerns.
- Current owner, next action, and next update time.

If the report lacks target identity, ask for it. "A server is down" is not a workable scope until it is tied to a hostname, asset tag, rack location, service, or other authoritative identifier.

## 4. Impact, scope, severity, and priority

Impact answers "who or what is affected?" Scope answers "how wide is the fault?" Severity usually reflects the operational impact. Priority adds urgency or business context. The exact labels differ by employer, so use the local matrix rather than inventing severity.

Gather observable scope facts:

- One component, one host, one rack, one service, multiple services, or a whole site?
- Full outage, degraded performance, loss of redundancy, intermittent failure, or no confirmed customer effect?
- Production, test, management, backup, or unknown environment?
- Are there safety, security, legal, or contractual implications?
- Is a planned change under way?

Do not minimise a loss of redundancy. A service may still work, but the next failure could become an outage. Equally, do not exaggerate impact before the evidence is established.

## 5. A repeatable troubleshooting method

Use one deliberate loop:

1. Stabilize: address immediate danger and avoid uncontrolled changes.
2. Define: write the exact symptom, target, time, and expected behavior.
3. Scope: determine whether the issue is isolated or shared.
4. Baseline: collect current evidence before changing anything.
5. Hypothesize: list plausible causes by fault domain.
6. Test safely: choose the smallest, least disruptive approved test that distinguishes between hypotheses.
7. Act with approval: contain, mitigate, or recover only through the authorized path.
8. Validate: prove the intended service or condition is restored, not merely that one alert changed.
9. Document and hand over: record outcome, uncertainty, follow-up, and ownership.

One controlled variable at a time is important. If a cable is moved, a service restarted, and an address changed together, it becomes difficult to know what helped or harmed.

## 6. Evidence quality and preservation

Evidence should enable another person to reconstruct what was observed. A useful entry includes:

- Timestamp and time zone.
- Source: monitoring system, device LED, remote engineer, console, command output, photo, or customer report.
- Exact target and environment.
- Observation: facts without interpretation.
- State change: whether the check only observed or changed something.
- Relevance: which hypothesis the evidence supports or weakens.
- Reference: attachment, log excerpt, ticket comment, or approved photo.

For example, "At 14:05 IST, on Rack R12 U18, PSU 2 LED was amber; PSU 1 LED was green. No cables were moved" is strong evidence. "Power supply is broken" is a conclusion that needs confirmation.

Keep evidence proportionate and confidential. Summarize a useful log excerpt rather than pasting hundreds of lines. Do not put passwords, private keys, customer data, or restricted photographs into the portfolio or an unapproved ticket channel.

## 7. Fault domains and layered triage

Use previous-week runbooks to inspect the relevant layer. The purpose here is to order the inquiry, not to repeat their commands.

| Fault domain | Example symptom | Safe early evidence | Likely owner if confirmed |
|---|---|---|---|
| Physical and environment | Loose rail, water, blocked airflow, unexpected device position | Rack location, visible state, approved photo, sensor ID | Site lead or facilities |
| Power | PSU alert, loss of redundancy, device dark | PSU LEDs, cable labels, PDU mapping, alarm ID | Facilities or hardware owner |
| Hardware and boot | Disk alert, memory fault, failed boot | Asset tag, controller or BMC evidence supplied by owner | Hardware or platform team |
| Network path | Link down, unreachable host, DNS failure | Labels, port map, link state, scope, approved network evidence | Network team |
| Operating system or service | Process failed, disk full, access denied | Approved Week 4 health evidence and service/log checks | Platform or application team |
| Application or dependency | Slow transaction, failed database connection, API timeout | Service impact, dependency map, recent change, alert correlation | Application or service owner |

A symptom at one layer can be caused elsewhere. For example, an application timeout may result from a storage delay, a network issue, a full filesystem, or a code defect.

## 8. Hypotheses, correlation, and safe tests

Write hypotheses down so they can be tested rather than assumed. A simple hypothesis log has:

| Possible cause | Evidence for | Evidence against | Lowest-risk test | Result | Next action |
|---|---|---|---|---|---|
| | | | | | |

Good tests are designed to distinguish alternatives. If a server is unreachable, confirming whether other hosts on the same switch or rack are affected may be more useful than immediately restarting the server. If a service is down but the host is healthy, checking the approved service state and recent logs can distinguish a local service fault from a broader network loss.

Correlation means looking for meaningful timing and shared dependencies. Compare:

- When each alert started.
- Which rack, host, network path, storage system, or service is shared.
- Whether an approved change occurred near the first symptom.
- Whether a "secondary" alert appeared only after another component failed.

Correlation suggests a lead; it does not prove causation.

## 9. Containment, mitigation, recovery, and validation

Containment reduces immediate risk. Mitigation reduces impact. Recovery returns the required service. They are related but not identical.

Examples:

- Isolating a damaged cable area may contain safety or equipment risk.
- Failing traffic to a healthy path may mitigate customer impact.
- Restoring a service from an approved backup may recover it.
- A post-recovery investigation may still be needed to determine why the first path failed.

State-changing actions require the correct authority even in an incident. Emergency changes may have a faster approval route, but they still require a documented decision, owner, impact assessment, and validation plan.

Validation should include the right layer. A green server LED may validate power, but not customer service. A cleared application alert may validate one monitor, but not a full user transaction. Ask the service owner what "restored" means for the incident.

## 10. Escalation and resolver-group ownership

Escalation is a professional control, not an admission of failure. Escalate when:

- Safety, security, or environmental conditions are present.
- The task exceeds authorization or requires a state-changing action not approved in the ticket.
- A fault is in another team's domain.
- Scope, impact, or risk is increasing.
- The next safe diagnostic step is unclear.
- A vendor, facilities team, or service owner needs to make a decision.

Send an escalation that helps the next team start immediately:

- Incident ID, time, target, environment, and confirmed impact.
- Scope and known unaffected comparison points.
- Exact evidence with timestamps.
- Actions already taken and changes explicitly not made.
- Current risk, such as degraded redundancy or a potential wider blast radius.
- A precise ask: validate a switch port, confirm a power-path mapping, approve a restart, assess a temperature alarm, or take ownership.

Do not escalate a vague message such as "Please investigate." Say what evidence you need reviewed and why.

## 11. Timelines, updates, and coordination

An incident timeline is chronological evidence, not a polished story written later. Record:

- Time and source.
- Observation or action.
- Owner.
- Outcome.
- Next decision or update time.

Use a predictable update structure:

    Status:
    Confirmed impact:
    Scope:
    Actions completed:
    Current evidence:
    Risk or blocker:
    Next action and owner:
    Next update:

Technical notes can be detailed. Stakeholder updates should be clear, factual, and free of speculative root cause or invented recovery times. If there is no reliable ETA, say what is happening next and when the next update will be given.

When several teams are involved, identify one coordination path. Parallel evidence gathering can help, but uncontrolled parallel changes can make an incident worse.

## 12. Active-incident handover

An incident can cross shifts. A handover must let the next person continue safely without rereading every message.

Include:

- Incident ID, current severity or priority, and shift time.
- Customer or service impact, scope, and current state.
- Confirmed facts and key evidence references.
- Hypotheses still open and tests already ruled out.
- Changes made, decisions, and validation status.
- Current owner, resolver groups engaged, and outstanding requests.
- Known risks, explicit do-not-do items, and next update time.

The outgoing technician remains responsible for a clear transfer until the receiving person acknowledges it under the local process.

## 13. Blameless review and corrective actions

After recovery, a post-incident review helps prevent recurrence. The goal is to improve systems, documentation, monitoring, and process; it is not to find someone to blame.

A useful review covers:

- What happened and what impact resulted.
- Detection: how the problem was first noticed and whether that was timely.
- A factual timeline.
- What worked well in the response.
- What created delay or uncertainty.
- Confirmed root cause, contributing factors, and unknowns.
- Corrective actions, preventive actions, owners, due dates, and evidence of completion.

Do not label a root cause as confirmed until the evidence supports it. A corrective action should be specific enough to track, such as "Correct rack R12 cable labels and have network owner verify port map by 20 August," not "Improve documentation."

## 14. Professional behavior under pressure

Strong incident behavior is visible in small habits:

- Announce what you are checking before acting.
- State whether an action is observation-only or changes state.
- Say "I do not know yet" when that is the truth, followed by the next safe step.
- Report mistakes or near misses promptly with facts and mitigating action.
- Respect the incident process even when another person pressures you to skip it.
- Keep messages concise enough for a busy shift to use.

The aim is credibility. A junior technician earns trust by preventing avoidable risk and making uncertainty manageable.

---

# Part 2: Week 6 questions and model answers

## Incident foundation and scope

### 1. What is the difference between an alert and an incident?

An alert is a signal that may require investigation. An incident is an unplanned interruption or degradation that needs an operational response. An alert may be harmless, and an incident may be reported by a user before monitoring alerts.

### 2. What should she do first when an incident is reported?

Confirm safety, the exact target, time, reported symptom, initial impact, and current owner. Start a timeline before choosing a technical action.

### 3. What is scope?

Scope describes how far the issue reaches: one component, host, rack, network segment, service, site, or user group.

### 4. What is impact?

Impact describes the effect on users, services, redundancy, safety, or business operations.

### 5. What is the difference between severity and priority?

Severity normally reflects operational impact. Priority also considers urgency and business context. The organization defines the exact rules.

### 6. Why should loss of redundancy be recorded even when service is still available?

The immediate customer effect may be low, but the service is more exposed to the next failure. It is a risk that needs ownership and resolution.

### 7. What is a workaround?

A temporary way to avoid or reduce the symptom without necessarily fixing the underlying cause.

### 8. What is mitigation?

An approved action that reduces impact or stabilizes the incident while investigation or permanent repair continues.

### 9. What is recovery?

Return of the required service level, confirmed with appropriate technical or service-owner validation.

### 10. Does recovery prove root cause?

No. A workaround or restoration can succeed without proving what originally failed.

### 11. What should she do if the target asset is unclear?

Pause technical action, ask for an authoritative hostname, asset tag, rack position, or service identifier, and record the ambiguity.

### 12. Why start a timeline early?

Timestamps help correlate alerts, changes, actions, and recovery. They also support accurate updates and handover.

## Method, evidence, and fault domains

### 13. What is a fact in an incident note?

An observable statement with source and time, such as a specific LED state, monitor value, log message, or customer report.

### 14. What is a hypothesis?

A possible explanation that still needs a safe test or evidence. It should not be written as confirmed cause.

### 15. Why separate facts from hypotheses?

It prevents assumptions from spreading as truth and helps the next technician see what still needs testing.

### 16. What does a good first technical check look like?

It is targeted, low risk, authorized, and able to distinguish between possible causes.

### 17. Why prefer read-only or reversible checks first?

They preserve evidence and reduce the chance of making the outage or investigation worse.

### 18. What is a fault domain?

A layer or shared area where a failure can originate or spread, such as power, hardware, network, operating system, application, rack, or storage.

### 19. Can an application timeout be caused by a physical issue?

Yes. A physical, power, network, storage, or host problem can present to users as an application timeout.

### 20. What is correlation?

It is identifying meaningful timing or shared-dependency relationships between events. It creates a lead but does not prove cause.

### 21. What is confirmation bias in troubleshooting?

It is favoring evidence that supports an early belief while ignoring evidence that weakens it.

### 22. Why change one variable at a time?

It preserves the ability to tell which action changed the result and reduces unnecessary risk.

### 23. What should an evidence entry include?

Time, source, exact target, observation, whether state changed, and a reference or relevance to the investigation.

### 24. Why should large logs be summarized rather than pasted wholesale?

Focused excerpts are easier to review, reduce noise, and are less likely to expose unnecessary or sensitive information.

### 25. What should she do if an observation conflicts with a remote engineer's expectation?

Report the exact evidence and ask for the next approved step. She should not alter the evidence to fit the expectation.

## Escalation and communication

### 26. When should she escalate?

Escalate for safety or security concerns, increasing scope, missing authority, another team's domain, unclear next steps, or a state-changing action that needs approval.

### 27. Is escalation a failure?

No. Timely escalation protects service and gets the correct expertise involved.

### 28. What is a precise escalation ask?

A clear request tied to facts, such as "Please confirm whether SW01 Eth1/18 should be up for asset LAB-103; the cable label and port map disagree."

### 29. Which team should receive a temperature or water concern?

Follow local process, usually facilities or the site lead. The technician should report the exact location, sensor or alarm ID, time, and observed condition.

### 30. Which team owns a suspected service or operating-system issue?

Usually the platform, Linux, or application owner, depending on the service boundary. The technician supplies approved evidence.

### 31. What should an incident update always state?

Status, confirmed impact, scope, completed actions, current evidence, risk or blocker, next owner/action, and next update time.

### 32. Should she give an ETA if she does not know one?

No. She should state the next action and the next update time instead.

### 33. Why avoid blaming a person or team in a live update?

Blame is usually unverified, damages collaboration, and does not help recovery. Report facts and ownership instead.

### 34. What is an active-incident handover?

A structured transfer that states impact, knowns, unknowns, evidence, changes, risks, owners, and the next update time.

### 35. What should she do if two teams propose conflicting changes?

Do not carry out either independently. Surface the conflict to the incident coordinator or approved decision owner.

### 36. Why record actions that were deliberately not taken?

It shows risk was recognized and prevents a later technician from assuming the action has already happened.

## Recovery, review, and scenarios

### 37. What is containment?

An action that limits immediate risk or spread, such as isolating an unsafe area or preventing further changes.

### 38. What is service validation?

Evidence that the intended service outcome is functioning, often confirmed by a service owner or agreed monitor, not just by one device indicator.

### 39. Why is "alert cleared" not always enough for closure?

The alert may have cleared due to a temporary condition, monitor behavior, or partial recovery. The required service still needs validation.

### 40. What is an emergency change?

An expedited, authorized change used to reduce urgent risk or restore service. It still requires a documented decision and later review.

### 41. What is a post-incident review?

A blameless review of impact, timeline, detection, response, causes or contributing factors, and improvement actions after recovery.

### 42. What makes a corrective action useful?

It has a specific outcome, owner, due date, and evidence that completion can be verified.

### 43. What should she do after making a mistake during an incident?

Stop further impact, report the exact facts promptly, record the time and mitigating action, and follow the incident or supervisor process.

### 44. A server is unreachable after an approved cable change. What is the first concern?

Confirm the affected scope and preserve the approved before/after cable and port evidence. Do not assume the new cable is the only cause or make uncontrolled changes.

### 45. A service is restored after a restart. What remains to do?

Validate the service as agreed, record the approval and action, retain relevant evidence, decide whether root-cause investigation is needed, and complete handover or follow-up actions.

### 46. A PSU LED is amber but users report no outage. What should she report?

The exact device, PSU, power-feed mapping, time, service state, and loss-of-redundancy risk. She should escalate to the appropriate hardware or facilities owner.

### 47. A high-temperature alert arrives while a technician is in the rack. What should she do?

Follow site safety and escalation procedure, record the exact location and alarm evidence, avoid unapproved cooling changes, and keep the work area safe.

### 48. A remote engineer asks for an unclear destructive command during an incident. What should she do?

Pause, ask what it does, what it targets, why it is needed, and whether approval is recorded. Escalate if the risk remains unclear.

### 49. A stakeholder asks for a recovery time that no engineer can confirm. What should she say?

State the confirmed impact, current action, and time of the next update. Do not invent a recovery estimate.

### 50. The incident shifts change but the next owner is unclear. What is the risk?

Work can stop, duplicate, or become unsafe. Ownership, next action, and next update time must be explicitly transferred.

### 51. What should she be able to do at the end of Week 6?

Lead a junior-level tabletop response with calm triage, accurate evidence, safe escalation, clear communication, and a useful post-incident record.

---

# Part 3: Lab exercises with hints

## Lab 1: Build an incident classification and severity matrix

### Goal

Practise classifying operational situations without exaggerating or minimising impact.

### Steps

1. Create rows for: single failed disk, loss of one PSU, unreachable production server, temperature alarm, suspicious access attempt, and planned cable change.
2. For each, identify whether it is an alert, incident, service request, change, problem, or a combination.
3. Record possible impact, scope questions, immediate safety considerations, likely owner, and escalation trigger.
4. Leave severity as "per local policy" unless your fictional scenario provides a matrix.

### Hints

- A failed component can be an incident even if redundancy keeps service running.
- Do not classify a planned activity as safe merely because it has a ticket; check approval and impact.

### Expected portfolio output

01-incident-classification-and-severity-matrix.md

## Lab 2: Create a first-five-minutes triage card

### Goal

Create a compact prompt that works under time pressure.

### Steps

1. Include safety, identity, time, symptom, impact, scope, recent change, evidence source, current owner, and next update time.
2. Add specific stop-and-escalate prompts for water, smoke, electrical concern, security issue, wrong target, and unapproved state-changing action.
3. Test it against the report: "Monitoring says a server is down."
4. Improve any question that would produce a vague answer.

### Hints

- The card should help you ask good questions before running a test.

### Expected portfolio output

02-first-five-minutes-triage-card.md

## Lab 3: Build an evidence source and hypothesis log

### Goal

Practise separating what is known from what is possible.

### Scenario

At 10:02, a monitoring system reports that APP-01 cannot reach its database. At 10:04, a storage-latency alert appears. At 10:05, another application on the same virtual host is slow.

### Steps

1. Record each item as evidence with time, source, target, and whether it is an observation or conclusion.
2. List at least three possible fault domains.
3. Write a low-risk test or evidence request for each hypothesis.
4. Mark what cannot yet be claimed.

### Hints

- Do not call the storage alert the root cause without further evidence.

### Expected portfolio output

03-evidence-source-and-hypothesis-log.md

## Lab 4: Build a fault-domain troubleshooting flow

### Goal

Create a decision flow that chooses the next safe check rather than a fixed technical answer.

### Steps

1. Start with "reported service unavailable."
2. Branch through safety, target confirmation, scope, physical/power evidence, network evidence, host/service evidence, and dependency evidence.
3. Add a stop point before every state-changing action.
4. Link each branch to the relevant prior-week runbook rather than duplicating commands.

### Hints

- A flow should allow "unknown" and "escalate" outcomes.

### Expected portfolio output

04-fault-domain-troubleshooting-flow.md

## Lab 5: Run a server-unreachable incident simulation

### Goal

Practise an ordered, multi-domain response.

### Scenario

At 14:00, a remote engineer reports that DC-LAB-WEB-03 is unreachable. The server was installed yesterday. The ticket records that remote validation succeeded at that time.

### Steps

1. Complete the first-five-minutes triage card.
2. Define scope questions that compare the target with similar hosts.
3. Write evidence requests in physical, power, network, and operating-system domains.
4. Create three hypotheses and choose the lowest-risk check first.
5. Write an initial update, escalation request if needed, and a recovery validation statement.

### Hints

- "Installed yesterday" is a lead, not proof that installation caused the issue.

### Expected portfolio output

05-server-unreachable-incident-simulation.md

## Lab 6: Run a link-down and wrong-cabling simulation

### Goal

Use physical evidence and change history without jumping to a conclusion.

### Scenario

After a scheduled cable replacement, SW01 Eth1/18 is down. The new cable label matches the ticket, but the rack port map says the original connection used Eth1/19.

### Steps

1. Record confirmed facts and inconsistency.
2. Define the safety and service-impact boundary before any change.
3. Write a precise escalation request to the network owner.
4. Define approved rollback and validation criteria.
5. Write status updates for initial, progress, and closure states.

### Hints

- The mismatched record may be the fault, or it may reveal a documentation error. Treat both as possible.

### Expected portfolio output

06-link-down-and-wrong-cabling-simulation.md

## Lab 7: Run a hardware or power-alert simulation

### Goal

Practise handling degraded redundancy without making an unsafe physical change.

### Scenario

At 09:17, a dual-PSU server reports PSU 2 failed. The server remains reachable. A rack diagram shows PSU 1 on feed A and PSU 2 on feed B.

### Steps

1. Record impact, current redundancy state, and immediate risks.
2. List physical evidence to collect without moving cables.
3. State who should own hardware replacement and power-path validation.
4. Write a planned-change request outline and escalation note.
5. Define service and redundancy validation after replacement.

### Hints

- A reachable server can still need urgent attention because a second failure may cause an outage.

### Expected portfolio output

07-hardware-or-power-alert-simulation.md

## Lab 8: Write an environmental or access escalation note

### Goal

Practise a response where normal troubleshooting must pause.

### Choose one scenario

1. A water sensor alarm appears near Rack R12.
2. A rack temperature alert is active and the rear cable bundle appears to obstruct airflow.
3. An unknown person requests entry to a restricted cage.

### Steps

1. State the immediate safety or security boundary.
2. Record the exact location, time, source, and observation.
3. Identify the correct local escalation route.
4. State actions deliberately not taken.
5. Write a concise update suitable for the site lead.

### Hints

- Do not reset alarms, bypass access control, or make unapproved cooling changes.

### Expected portfolio output

08-environmental-or-access-escalation-note.md

## Lab 9: Build an incident timeline and status updates

### Goal

Practise clear communication cadence.

### Steps

1. Use any prior scenario and create a 45-minute timeline.
2. Add an entry every 10-15 minutes or whenever a material event happens.
3. Write initial, progress, mitigation, recovery, and closure updates.
4. Keep technical detail in the working notes and stakeholder language factual.
5. State a next update time when recovery is not yet known.

### Hints

- Avoid filling gaps with speculation.

### Expected portfolio output

09-incident-timeline-and-status-updates.md

## Lab 10: Create cross-team escalation packets

### Goal

Tailor the same incident facts to the right resolver group.

### Steps

1. Use the server-unreachable scenario.
2. Draft one escalation to a network team, one to a platform team, and one to facilities only if the facts justify it.
3. For each, include the exact evidence, actions completed, actions not taken, risk, and a specific request.
4. Explain why the asks differ.

### Hints

- Do not copy the same vague message to every team.

### Expected portfolio output

10-cross-team-escalation-packet.md

## Lab 11: Write a decision, mitigation, and validation record

### Goal

Show how an approved state-changing action is controlled during an incident.

### Scenario

The service owner approves a restart of a failed lab service after evidence is collected.

### Steps

1. Record the proposed action, owner, approval source, target, expected effect, risk, and rollback.
2. Record baseline evidence before the action.
3. Write the validation required after the restart.
4. Add an entry for the case where the restart fails to recover service.

### Hints

- The lab action is acceptable only in a lab. In production, use the local approval process.

### Expected portfolio output

11-decision-mitigation-and-validation-record.md

## Lab 12: Write an active-incident handover and post-incident review

### Goal

Practise continuity during and after an incident.

### Steps

1. Create a handover at the 30-minute point of a scenario.
2. Include knowns, unknowns, evidence references, actions, risks, owners, and next update.
3. Assume the service recovers later and write a blameless post-incident review.
4. Add at least three corrective or preventive actions with owner and due date.

### Hints

- Keep "root cause" marked unknown if the scenario does not prove it.

### Expected portfolio output

12-active-incident-handover.md and 13-blameless-post-incident-review.md

## Lab 13: Build a corrective-action register

### Goal

Turn lessons into trackable work.

### Steps

1. Create actions for documentation, monitoring, cable labelling, and runbook improvement from a prior scenario.
2. Give each action a problem addressed, owner, due date, priority, evidence of completion, and status.
3. Mark which actions are preventive versus corrective.
4. Add a review date.

### Hints

- A good action changes a condition; it is not simply "be more careful."

### Expected portfolio output

13-blameless-post-incident-review.md, in the corrective and preventive actions section.

## Lab 14: Write mock incident ticket updates

### Goal

Practise concise, evidence-led communication.

### Scenarios

Write updates for:

1. A failed disk alert with no service impact.
2. A server unreachable after a change window.
3. A high-temperature alarm with unclear scope.
4. A service restart requested without clear approval.
5. An incident handed to the next shift while root cause is unknown.

### For each scenario, include

- Time, target, impact, and scope.
- Facts versus hypothesis.
- Actions completed and actions not taken.
- Risk, escalation, and next update time.

### Expected portfolio output

14-mock-incident-ticket-updates.md

## Lab 15: Build a Week 6 mock interview script

### Goal

Prepare clear spoken answers under pressure.

### Steps

Write 45-90 second answers for:

1. A server is unreachable. What do you do first?
2. How do you decide when to escalate?
3. What information makes an escalation useful?
4. What is the difference between mitigation and root-cause resolution?
5. How do you work under pressure without making mistakes?
6. How do you communicate when there is no confirmed recovery time?
7. What should an incident handover include?
8. What does blameless post-incident review mean?
9. What would you do if you made a mistake?
10. How do you distinguish facts from assumptions?

### Expected portfolio output

15-week-06-interview-script.md

## Lab 16: Final Week 6 self-assessment

### Goal

Check whether the learner can participate safely in a multi-domain incident.

### Self-assessment table

| Skill | Can do without notes | Can do with notes | Need more practice |
|---|---|---|---|
| Establish safety, identity, time, impact, and scope | | | |
| Classify alert, incident, change, and workaround in context | | | |
| Start a factual timeline | | | |
| Separate observations from hypotheses | | | |
| Use fault domains to order evidence gathering | | | |
| Choose a low-risk test before a change | | | |
| Identify a loss-of-redundancy risk | | | |
| Write a useful escalation packet | | | |
| Give a factual update without inventing an ETA | | | |
| Record mitigation, approval, rollback, and validation | | | |
| Hand over an active incident clearly | | | |
| Write a blameless post-incident review | | | |
| Track corrective and preventive actions | | | |
| Stop and escalate outside authorization | | | |

### Expected portfolio output

16-week-06-self-assessment.md

---

# Part 4: Templates to copy into the portfolio

## First-five-minutes incident triage card

    # First Five Minutes

    Incident/ticket:
    Time and time zone:
    Reporter / alert source:
    Exact target:
    Environment:
    Reported symptom:
    Confirmed impact:
    Current known scope:
    Recent approved change:
    Safety / security / environmental concern:
    Current owner:
    Immediate safe next action:
    Next update time:

    Stop and escalate if:
    - Target identity is unclear.
    - There is smoke, water, electrical concern, or a physical-security issue.
    - The next action changes state without recorded approval.
    - Scope or risk is increasing beyond the current owner.

## Evidence and hypothesis log

| Time | Source | Target | Fact observed | State changed? | Hypothesis supported or weakened | Reference |
|---|---|---|---|---|---|---|
| | | | | No | | |

| Hypothesis | Evidence for | Evidence against | Lowest-risk next test | Result | Next owner/action |
|---|---|---|---|---|---|
| | | | | | |

## Incident timeline and status update template

    # Incident Timeline

    | Time | Owner | Observation or action | Outcome | Next action |
    |---|---|---|---|---|
    | | | | | |

    # Status Update

    Status:
    Confirmed impact:
    Scope:
    Actions completed:
    Current evidence:
    Risk or blocker:
    Next action and owner:
    Next update:

## Cross-team escalation packet

    # Escalation Request

    Incident:
    To resolver group:
    Time:
    Target / environment:
    Confirmed impact and scope:
    Evidence:
    Actions completed:
    Changes not made:
    Current risk:
    Specific request:
    Contact / update cadence:

## Decision, mitigation, and validation record

    # Incident Decision Record

    Incident:
    Proposed action:
    Target:
    Decision owner:
    Approval source and time:
    Expected benefit:
    Risk:
    Baseline evidence:
    Rollback:
    Validation method and owner:
    Outcome:
    Follow-up required:

## Active-incident handover template

    # Active Incident Handover

    Incident / severity:
    Shift and prepared by:
    Current owner:
    Customer or service impact:
    Current scope:

    ## Confirmed facts

    ## Open hypotheses and tests already completed

    ## Changes, mitigation, and validation state

    ## Engaged teams and outstanding requests

    ## Risks and do-not-do items

    ## Next action, owner, and update time

## Blameless post-incident review template

    # Post-Incident Review

    Incident:
    Date:
    Services affected:
    Impact:
    Detection:

    ## Timeline

    ## Confirmed cause and contributing factors

    ## What worked well

    ## What created delay or uncertainty

    ## Corrective and preventive actions

    | Action | Type | Owner | Due date | Evidence of completion | Status |
    |---|---|---|---|---|---|
    | | Corrective / Preventive | | | | |

---

# Part 5: Week 6 final exam

## Written exam

Answer these without looking at notes:

1. Explain the difference between an alert, incident, change, problem, workaround, mitigation, recovery, and root cause.
2. List the first-five-minutes checks for a reported outage.
3. Explain scope, impact, severity, and priority.
4. Explain why facts and hypotheses must be separated.
5. Describe a low-risk troubleshooting test.
6. List the main physical-to-service fault domains.
7. Explain why correlation does not prove root cause.
8. Write a useful escalation request for a suspected link issue.
9. Explain why an emergency change still needs an approval record.
10. Explain the difference between containment, mitigation, and recovery.
11. Describe suitable service validation.
12. List the required contents of an active-incident handover.
13. Explain blameless post-incident review.
14. Write two specific corrective actions after a documentation-related incident.

## Practical exam

Use this tabletop:

At 11:00, shortly after an approved cable-change window, a web service becomes unavailable. One server reports an amber PSU LED, the switch port map has a discrepancy, and a monitoring alert shows a dependency timeout. No root cause is supplied.

Complete these tasks:

1. Fill in the first-five-minutes triage card.
2. State safety and authorization boundaries.
3. Establish impact and scope questions.
4. Build a fact and hypothesis log across physical, power, network, and service domains.
5. Choose the lowest-risk next checks.
6. Write an initial update and a cross-team escalation packet.
7. Define an approved mitigation decision and recovery validation.
8. Write a shift handover at the 30-minute mark.
9. Draft the outline of a post-incident review without claiming an unproven root cause.

## Passing standard

She passes Week 6 if she can:

- Stay structured when the symptom is ambiguous.
- Confirm identity, safety, impact, scope, and time before improvising a fix.
- Collect concise, timestamped evidence and separate it from hypotheses.
- Use prior technical skills in a low-risk order.
- Escalate to the appropriate owner with a precise, evidence-led request.
- Communicate current state and uncertainty without overstating confidence.
- Record approved mitigation, validation, handover, and follow-up actions.
- Participate constructively in a blameless review.

---

# Part 6: Interview positioning for Week 6

Week 6 gives her a professional troubleshooting story. She should not claim to have led production incidents if she has practised tabletop scenarios. She can say that she has trained herself to use a controlled incident process and has built evidence, escalation, and handover templates.

## Strong interview themes

- I start by confirming safety, target identity, time, impact, and scope.
- I distinguish facts from hypotheses and choose the least risky check first.
- I use previous hardware, network, Linux, and physical runbooks rather than guessing.
- I escalate early when a task crosses my authorization or another team owns the dependency.
- I give clear updates with impact, actions, risk, owner, and next update time.
- I understand that recovery and root-cause confirmation are different outcomes.
- I hand over active work with knowns, unknowns, risks, and next steps.

## Example answer: a server is unreachable

"I would first confirm the exact host or asset, environment, time of the report, and customer or service impact. I would check whether the issue is isolated or affects a shared rack, network path, or service. I would collect approved, low-risk evidence across the relevant physical, power, network, and service layers and record facts separately from hypotheses. If the next action needs another team's authority, I would send an escalation with the exact evidence and a clear ask. I would not restart or move anything without approval."

## Example answer: deciding when to escalate

"I escalate when there is a safety or security concern, the impact or scope is growing, the fault belongs to another resolver group, or the next safe action needs authority I do not have. I would include the incident ID, target, impact, evidence, actions taken, actions not taken, current risk, and the exact help needed. Escalating early is how I protect service and avoid unsafe guesses."

## Example answer: working under pressure

"Under pressure I use a short triage structure: safety, target, time, impact, scope, evidence, next action, and next update. I keep a timestamped timeline and state what is known and unknown. That helps me stay calm, communicate clearly, and avoid making several uncontrolled changes at once."

---

# Part 7: Week 6 completion checklist

- [ ] I created a Week 6 portfolio folder.
- [ ] I built an incident classification and severity matrix.
- [ ] I created a first-five-minutes triage card.
- [ ] I can distinguish fact, hypothesis, and assumption.
- [ ] I created an evidence source and hypothesis log.
- [ ] I built a fault-domain troubleshooting flow that links to earlier runbooks.
- [ ] I completed a server-unreachable simulation.
- [ ] I completed a link-down and wrong-cabling simulation.
- [ ] I completed a hardware or power-alert simulation.
- [ ] I wrote an environmental or access escalation note.
- [ ] I created a timeline and status-update pack.
- [ ] I created resolver-group-specific escalation packets.
- [ ] I recorded an approved mitigation, rollback, and validation plan.
- [ ] I wrote an active-incident handover.
- [ ] I completed a blameless post-incident review and corrective-action register.
- [ ] I completed the Week 6 mock interview script.
- [ ] I completed the Week 6 final exam and self-assessment.
- [ ] I can stop and escalate rather than making an unauthorized change.
