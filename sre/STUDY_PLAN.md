# Certification-Style Study Plan: Site Reliability Engineer, SRE

## Target outcome

This plan prepares a complete beginner for entry-level roles such as:

- Junior Site Reliability Engineer
- Reliability Engineer, junior level
- Production Operations Engineer
- Cloud Operations Engineer with reliability focus
- Platform Operations Engineer
- NOC / Incident Response Engineer moving toward SRE

The plan is designed to reach **one grade above entry level**. By the end, she should understand not only Linux, cloud, and deployment basics, but also reliability engineering: SLIs, SLOs, error budgets, monitoring, alerting, incident response, capacity, automation, and post-incident improvement.

## Duration and workload

- **Length:** 10 weeks minimum
- **Time:** 3-5 hours per day, 5-6 days per week
- **Total effort:** about 180-260 hours
- **Style:** certification program with reliability labs, incident simulations, runbooks, and a final production-readiness capstone

SRE is usually less beginner-friendly than data center or DevOps. If she is fully new, she should consider completing the DevOps plan first or studying the first 5 weeks of DevOps in parallel.

## Role reality in Dublin / Ireland

SRE roles, even junior ones, often expect candidates to understand production systems. Dublin employers may expect:

- Strong Linux fundamentals.
- Networking and HTTP basics.
- Cloud and container awareness.
- Monitoring/logging tools.
- Incident response communication.
- Scripting/automation.
- Understanding of reliability, scalability, and operational risk.
- Ability to stay calm during incidents.
- Documentation and postmortem writing.

## What “one grade above entry level” means

An entry-level SRE candidate knows tools. A junior-plus SRE candidate can:

- Define user-focused reliability using SLIs and SLOs.
- Explain alert quality and reduce noisy alerts.
- Triage production incidents systematically.
- Write runbooks and postmortems.
- Use Linux and logs to identify symptoms.
- Understand deployment risk and rollback.
- Automate repetitive checks.
- Discuss capacity, saturation, latency, errors, and availability.
- Communicate clearly with engineering, support, and business stakeholders.

## Recommended optional certifications

Certifications are useful but portfolio and incident practice matter more.

Priority order:

1. **AWS Cloud Practitioner** or **Azure Fundamentals AZ-900**.
2. **Linux Foundation Certified IT Associate (LFCA)** or Linux Essentials.
3. **Kubernetes and Cloud Native Associate (KCNA)**.
4. Optional later: **Prometheus Certified Associate** or cloud associate certification.

## Tools and low-cost lab setup

- WSL2 Ubuntu or Linux VM.
- GitHub account.
- Docker Desktop.
- Python or Node.js sample app.
- Prometheus and Grafana locally, or simpler monitoring first.
- Loki or basic file logs if advanced logging is too much.
- GitHub Actions.
- Optional: AWS/Azure free tier with budget alerts.
- Diagrams.net.

## Portfolio deliverables

By the end, create:

1. Reliability glossary.
2. Linux troubleshooting runbook.
3. Web app with health endpoint.
4. Monitoring dashboard screenshots.
5. Alert rules and alert-quality notes.
6. SLI/SLO document for the sample app.
7. Incident response runbook.
8. Two postmortems for simulated incidents.
9. Automation scripts for health checks.
10. Final capstone: production-readiness review for a small service.

---

# Week 1: SRE foundations and production mindset

## Goal

Understand what SRE is and how it differs from general DevOps or support.

## Topics

- What SRE means: applying software engineering to operations.
- Reliability vs availability vs durability.
- User expectations and business impact.
- Toil and automation.
- Risk management.
- Service ownership.
- Incident lifecycle.
- Blameless culture.
- Documentation and runbooks.
- Production readiness.

## Hands-on labs

1. **Reliability glossary**
   - Define 50 terms: SLI, SLO, SLA, error budget, latency, saturation, MTTR, MTTD, toil, runbook, postmortem.

2. **Service map exercise**
   - Pick a familiar service like online shopping.
   - Draw dependencies: user, web, API, database, payment, email, DNS.

3. **Impact analysis**
   - For each dependency, write what users experience if it fails.

4. **Runbook template**
   - Create a reusable runbook format.

## Interview practice

- What is SRE?
- What is reliability?
- What is toil?
- What is a runbook?
- Why are postmortems blameless?

## Checkpoint

She should be able to explain SRE in simple business-focused terms.

## Portfolio artifact

Publish: reliability glossary, service map, and runbook template.

---

# Week 2: Linux, networking, and web service troubleshooting

## Goal

Build the technical foundation required to debug production symptoms.

## Topics

- Linux filesystem and permissions.
- Processes, services, systemd.
- Logs with journalctl.
- CPU, memory, disk, network checks.
- HTTP status codes.
- DNS and TLS basics.
- Ports and sockets.
- Firewalls/security groups conceptually.
- Common failure modes: service down, disk full, high CPU, DNS failure.

## Hands-on labs

1. **Install Ubuntu environment**
   - Use WSL2 or VM.
   - Install nginx or a simple app.

2. **Break/fix service**
   - Stop service and observe symptoms.
   - Change config incorrectly and inspect logs.

3. **Resource pressure simulation**
   - Fill a test directory with files.
   - Observe disk usage.
   - Clean up safely.

4. **DNS/HTTP troubleshooting**
   - Use curl, dig/nslookup, ping, traceroute.

## Commands to learn

```bash
systemctl status nginx
journalctl -u nginx --no-pager
ps aux
top
df -h
du -sh *
free -h
uptime
ip addr
ip route
ss -tulpn
curl -v http://localhost
dig example.com
ping -c 4 8.8.8.8
```

## Interview practice

- A website is down. What do you check first?
- How do you check if a process is listening on a port?
- What does HTTP 500 mean?
- What does DNS do?
- How do you check disk usage?

## Checkpoint

She should be able to triage a simple web service outage locally.

## Portfolio artifact

Publish: Linux/web troubleshooting runbook with screenshots.

---

# Week 3: Git, scripting, and automation against toil

## Goal

Learn the basic engineering skills SREs use to reduce manual work.

## Topics

- Git basics.
- Markdown documentation.
- Bash scripting.
- Python basics.
- Exit codes.
- Environment variables.
- Cron/scheduled jobs conceptually.
- Idempotent scripts.
- Safe automation and dry runs.
- Toil identification.

## Hands-on labs

1. **GitHub reliability repository**
   - Create a repository for SRE labs.
   - Use branches and pull requests.

2. **Health-check script**
   - Check service status, disk, memory, HTTP endpoint.
   - Print OK/WARN/CRITICAL.

3. **Log parser**
   - Count HTTP 500s in a sample log file.
   - Print error rate.

4. **Toil report**
   - Choose a repetitive manual task and describe how automation helps.

## Interview practice

- What is toil?
- How can automation be dangerous?
- What is an exit code?
- What would you automate first in operations?
- How do you test an automation script safely?

## Checkpoint

She should be able to write a small script and explain how it reduces toil.

## Portfolio artifact

Publish: health-check script, log parser, and toil report.

---

# Week 4: Metrics, logs, traces, and observability

## Goal

Understand how production systems are observed and how alerts should be designed.

## Topics

- Monitoring vs observability.
- Metrics, logs, traces.
- RED method: Rate, Errors, Duration.
- USE method: Utilization, Saturation, Errors.
- Golden signals: latency, traffic, errors, saturation.
- Log levels: debug, info, warn, error, fatal.
- Dashboards vs alerts.
- Alert fatigue.
- Actionable alerts.
- Basic Prometheus and Grafana concepts.

## Hands-on labs

1. **Instrument simple app conceptually**
   - Add `/health` endpoint.
   - Add basic request logging.

2. **Prometheus/Grafana local lab**
   - Run with Docker Compose if possible.
   - Scrape a simple endpoint or node exporter.
   - Create dashboard panel.

3. **Log analysis lab**
   - Generate normal and error logs.
   - Search and summarize errors.

4. **Alert design exercise**
   - Write five alerts.
   - Mark which are actionable and which are noisy.

## Interview practice

- What is the difference between monitoring and observability?
- What are the golden signals?
- What makes a good alert?
- Why are logs not enough?
- How would you monitor a web API?

## Checkpoint

She should be able to propose useful metrics and alerts for a simple service.

## Portfolio artifact

Publish: dashboard screenshots, alert rules draft, and observability notes.

---

# Week 5: SLIs, SLOs, SLAs, and error budgets

## Goal

Learn the core reliability language that differentiates SRE from general operations.

## Topics

- SLA: external promise.
- SLO: internal reliability target.
- SLI: measurement.
- Error budget.
- Availability calculations.
- Latency percentiles: p50, p90, p95, p99.
- Request success rate.
- Burn rate conceptually.
- Reliability vs feature velocity.

## Hands-on labs

1. **Define SLIs for sample app**
   - Availability SLI.
   - Latency SLI.
   - Error-rate SLI.

2. **Write SLO document**
   - Example: 99.5% successful requests over 30 days.
   - Explain why not 100%.

3. **Error budget calculation**
   - Calculate allowed downtime for 99%, 99.5%, 99.9% monthly.

4. **Decision exercise**
   - Error budget nearly exhausted: should team launch risky feature?

## Interview practice

- What is the difference between SLI, SLO, and SLA?
- Why is 100% availability usually unrealistic?
- What is an error budget?
- What is p95 latency?
- How do SLOs help engineering teams make decisions?

## Checkpoint

She should be able to create a basic SLO document for a web service.

## Portfolio artifact

Publish: SLI/SLO/error-budget document for the sample app.

---

# Week 6: Incident response and communication

## Goal

Practice the behavior expected during real production incidents.

## Topics

- Incident severity levels.
- Incident commander role.
- Communications lead role.
- Technical lead role.
- Timeline keeping.
- Stakeholder updates.
- Escalation.
- Mitigation vs root cause.
- Rollback.
- Post-incident review.
- Psychological safety and calm communication.

## Hands-on labs

1. **Incident simulation 1: app down**
   - Stop the app.
   - Detect with curl or monitoring.
   - Triage and recover.
   - Write timeline.

2. **Incident simulation 2: high error rate**
   - Add a broken endpoint or config.
   - Identify symptoms from logs.
   - Roll back.

3. **Stakeholder updates**
   - Write initial, progress, and resolved updates.

4. **Postmortem**
   - Write what happened, impact, detection, resolution, contributing factors, action items.

## Interview practice

- What do you do first during an incident?
- What is the difference between mitigation and root cause?
- How often should you communicate during an incident?
- What makes a good postmortem?
- How do you stay calm under pressure?

## Checkpoint

She should be able to run a mock incident and produce a clear postmortem.

## Portfolio artifact

Publish: two incident timelines, stakeholder updates, and postmortems.

---

# Week 7: Deployment reliability, CI/CD, rollback, and change management

## Goal

Understand how releases cause incidents and how SREs reduce deployment risk.

## Topics

- CI/CD basics.
- Deployment pipeline stages.
- Release strategies: rolling, blue/green, canary.
- Feature flags.
- Rollback and roll-forward.
- Change failure rate.
- DORA metrics conceptually.
- Pre-deployment checks.
- Post-deployment validation.
- Change freezes and maintenance windows.

## Hands-on labs

1. **GitHub Actions CI**
   - Build/test sample app.
   - Fail pipeline intentionally.
   - Fix it.

2. **Deployment checklist**
   - Pre-checks, deployment, validation, rollback.

3. **Bad release simulation**
   - Deploy broken version locally.
   - Detect error.
   - Roll back to previous version.

4. **Change review**
   - Write risk assessment for a deployment.

## Interview practice

- How do deployments cause incidents?
- What is rollback?
- What is a canary deployment?
- What checks should happen before and after deployment?
- What are DORA metrics?

## Checkpoint

She should be able to explain safe deployment and rollback for a small service.

## Portfolio artifact

Publish: CI workflow, deployment checklist, and rollback report.

---

# Week 8: Containers, Kubernetes basics, and cloud reliability

## Goal

Understand modern production platforms enough to troubleshoot and communicate.

## Topics

- Docker image vs container.
- Container logs and environment variables.
- Kubernetes cluster, node, pod, deployment, service, namespace.
- Liveness and readiness probes.
- Resource requests and limits.
- Horizontal scaling conceptually.
- Managed Kubernetes conceptually.
- Cloud regions and availability zones.
- Load balancing.
- Autoscaling conceptually.

## Hands-on labs

1. **Dockerize sample app**
   - Build and run locally.
   - Inspect logs.

2. **Run app with Docker Compose**
   - Add dependency if possible.
   - Use environment variables.

3. **Kubernetes local lab**
   - Deploy app to minikube/kind/Docker Desktop Kubernetes.
   - Add service.
   - Scale replicas.
   - Break and fix image or port.

4. **Probe design**
   - Write readiness and liveness probe examples.

## Interview practice

- Why use containers?
- What is a Kubernetes pod?
- What is a readiness probe?
- What is the difference between scaling up and scaling out?
- How does multi-AZ improve reliability?

## Checkpoint

She should be able to deploy and troubleshoot a simple containerized workload.

## Portfolio artifact

Publish: Dockerfile, Kubernetes YAML, and troubleshooting notes.

---

# Week 9: Capacity, performance, security, and production readiness

## Goal

Learn how SREs think proactively before incidents happen.

## Topics

- Capacity planning basics.
- Load testing conceptually.
- Bottlenecks: CPU, memory, disk I/O, network, database.
- Caching conceptually.
- Rate limiting conceptually.
- Backups and restore testing.
- Disaster recovery: RTO and RPO.
- Security fundamentals: least privilege, secrets, patching, vulnerability scanning.
- Production readiness checklist.

## Hands-on labs

1. **Simple load test**
   - Use a basic tool such as `hey`, `ab`, or a small script.
   - Observe latency and errors.

2. **Capacity note**
   - Write what happens as traffic grows 10x.

3. **Backup/restore exercise**
   - Backup a local config or small database/file.
   - Restore it.
   - Document verification.

4. **Production readiness review**
   - Review sample app for monitoring, logs, alerts, rollback, security, documentation.

## Interview practice

- What is capacity planning?
- What is RTO vs RPO?
- Why must backups be tested?
- What is least privilege?
- What would you check before calling a service production-ready?

## Checkpoint

She should be able to identify operational risks before launch.

## Portfolio artifact

Publish: production readiness checklist and capacity/performance notes.

---

# Week 10: Capstone, CV, LinkedIn, and interview readiness

## Goal

Create a final SRE hiring package with technical evidence and interview stories.

## Capstone project: production-readiness review and reliability pack

Build or use a simple web app and produce:

- Architecture diagram.
- Health endpoint.
- Dockerfile.
- CI pipeline.
- Basic monitoring dashboard.
- Log examples.
- SLI/SLO document.
- Alert rules.
- Incident response runbook.
- Deployment and rollback checklist.
- Two postmortems from simulated incidents.
- Production readiness review.

Final presentation:

- 10 minutes explaining the service.
- 5 minutes explaining reliability risks.
- 5 minutes walking through one incident and postmortem.

## CV focus

Add a “Reliability Engineering Lab Portfolio” section:

```text
Reliability Engineering Lab Portfolio
- Built a production-readiness pack for a containerized web service including health checks, monitoring notes, SLI/SLO definitions, alert rules, and incident runbooks.
- Simulated service outage and high-error-rate incidents, produced timelines, stakeholder updates, rollback notes, and blameless postmortems.
- Created Linux troubleshooting scripts and runbooks for CPU, memory, disk, network, process, and HTTP checks.
- Practiced CI/CD failure diagnosis, deployment validation, and rollback planning using GitHub Actions and Docker.
- Deployed and troubleshot simple Kubernetes workloads using pods, deployments, services, logs, rollout status, and scaling commands.
```

## LinkedIn headline examples

- Junior SRE Candidate | Linux, Observability, Incident Response, Docker, Kubernetes
- Aspiring Site Reliability Engineer in Dublin | SLOs, Monitoring, Automation, Cloud Ops

## Mock interview set

She must answer these aloud and connect answers to portfolio artifacts:

1. Tell me about yourself.
2. Why SRE?
3. What is the difference between SRE and DevOps?
4. Explain your capstone service architecture.
5. What are SLIs, SLOs, and SLAs?
6. What is an error budget?
7. What are the golden signals?
8. How do you design a good alert?
9. A service is down. What do you do first?
10. A deployment caused errors. What do you do?
11. How do you write a postmortem?
12. What is toil and how would you reduce it?
13. How do you check Linux disk, CPU, memory, and ports?
14. How do you troubleshoot a Kubernetes pod that keeps restarting?
15. What is readiness vs liveness?
16. What is RTO vs RPO?
17. How would you prepare a service for production?
18. How do you communicate with non-technical stakeholders during an incident?
19. Tell me about a time you learned something difficult.
20. Why should we hire you for a junior SRE role?

## Final readiness checklist

- [ ] Can explain SRE, toil, reliability, and production ownership.
- [ ] Can troubleshoot Linux and HTTP service problems.
- [ ] Can write basic Bash/Python automation.
- [ ] Can explain metrics, logs, traces, and golden signals.
- [ ] Can define SLIs, SLOs, and error budgets for a web service.
- [ ] Can run a mock incident and communicate clearly.
- [ ] Can write a blameless postmortem.
- [ ] Can explain CI/CD, deployment risk, and rollback.
- [ ] Can Dockerize and run a simple service.
- [ ] Can deploy and troubleshoot basic Kubernetes workloads.
- [ ] Can discuss capacity, backups, RTO/RPO, and production readiness.
- [ ] Has completed the capstone reliability pack.
- [ ] Has a targeted CV and LinkedIn profile.
- [ ] Has completed at least five mock interviews.

## Extra work to stand out

- Read selected chapters from Google SRE books: SLOs, monitoring, incident response, eliminating toil.
- Create Prometheus alert rules with burn-rate style examples.
- Add structured JSON logging to the sample app.
- Add OpenTelemetry tracing conceptually or in a small demo.
- Add chaos testing basics: intentionally kill a container and observe recovery.
- Add a status page template.
- Attend Dublin SRE, cloud, DevOps, or cybersecurity meetups and summarize lessons.
- Apply also for NOC, Cloud Operations, Technical Support, and Junior DevOps roles as stepping stones into SRE.
