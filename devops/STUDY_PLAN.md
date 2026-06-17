# Certification-Style Study Plan: DevOps Engineer

## Target outcome

This plan prepares a complete beginner for entry-level roles such as:

- Junior DevOps Engineer
- Cloud Operations Engineer, junior level
- Platform Engineer, junior level
- Build and Release Engineer, junior level
- Infrastructure Automation Engineer, junior level
- Technical Support Engineer with DevOps responsibilities

The plan is designed to reach **one grade above entry level**. By the end, she should not only know basic commands, but be able to build, deploy, monitor, troubleshoot, and explain a small production-like application environment using cloud, Linux, Git, CI/CD, Docker, Terraform, and basic Kubernetes concepts.

## Duration and workload

- **Length:** 10 weeks minimum
- **Time:** 3-5 hours per day, 5-6 days per week
- **Total effort:** about 180-250 hours
- **Style:** certification program with hands-on labs, weekly assessments, capstone project, and mock interviews

DevOps is broader than a typical entry role. A newbie can become employable only by building a visible portfolio and learning fundamentals deeply.

## Role reality in Dublin / Ireland

Junior DevOps roles often receive many applications. Many “junior” job descriptions still ask for cloud, CI/CD, Docker, Kubernetes, Terraform, scripting, Linux, and monitoring. To compete, she should demonstrate:

- Strong Linux and networking basics.
- Git and GitHub confidence.
- One cloud provider, preferably AWS or Azure.
- CI/CD pipeline built by herself.
- Dockerized application.
- Infrastructure as Code with Terraform.
- Basic Kubernetes understanding.
- Monitoring/logging and incident troubleshooting awareness.
- Clear documentation and communication.

## What “one grade above entry level” means

An entry-level DevOps candidate can follow tutorials. A junior-plus candidate can:

- Explain each component in her own architecture.
- Debug failed builds and deployments.
- Secure secrets and credentials properly.
- Understand the difference between dev, staging, and production.
- Use Git branches and pull requests.
- Write simple Bash or Python automation.
- Create Terraform for repeatable infrastructure.
- Set up basic alerts and logs.
- Discuss trade-offs, cost, security, reliability, and rollback.

## Recommended optional certifications

Priority order:

1. **AWS Certified Cloud Practitioner** or **Microsoft Azure Fundamentals AZ-900**.
2. **AWS Solutions Architect Associate** or **Azure Administrator AZ-104** after the basics.
3. **HashiCorp Terraform Associate**.
4. Optional later: **Certified Kubernetes Application Developer (CKAD)** or **Kubernetes and Cloud Native Associate (KCNA)**.

For this plan, portfolio quality is more important than exam badges.

## Tools and low-cost lab setup

- Windows laptop with WSL2 Ubuntu, or Linux VM.
- Git and GitHub account.
- VS Code.
- Docker Desktop.
- Free-tier AWS or Azure account with strict budget alerts.
- Terraform.
- GitHub Actions.
- A simple sample application: Node.js, Python Flask, or static website.
- Prometheus/Grafana locally or cloud-native monitoring.
- Diagrams.net for architecture diagrams.

Important: Always set cloud budgets and delete unused resources.

## Portfolio deliverables

By the end, create a GitHub portfolio with:

1. Linux command notes and troubleshooting runbook.
2. Git/GitHub workflow demo repository.
3. Dockerized sample app.
4. CI/CD pipeline using GitHub Actions.
5. Terraform infrastructure repository.
6. Cloud deployment diagram.
7. Monitoring/logging notes.
8. Incident and rollback runbook.
9. Final capstone: production-like app deployment.

---

# Week 1: Foundations: how the internet, Linux, and software delivery work

## Goal

Understand the environment DevOps supports: applications, servers, networks, DNS, HTTP, and Linux.

## Topics

- What DevOps means: culture, automation, collaboration, feedback.
- SDLC: plan, code, build, test, release, deploy, operate, monitor.
- Client/server model.
- HTTP/HTTPS basics.
- DNS basics.
- IP addresses, ports, firewalls.
- Linux filesystem and command line.
- Processes, services, logs.
- Package managers.
- SSH concept.

## Hands-on labs

1. **Install WSL2 Ubuntu or Ubuntu VM**
   - Create user.
   - Update packages.
   - Install basic tools.

2. **Linux navigation lab**
   - Create files and directories.
   - Practice permissions.
   - Search logs and text.

3. **Run a local web server**
   - Use Python or nginx.
   - Access it from browser.
   - Identify listening port.

4. **Internet request flow diagram**
   - Draw what happens when a user visits a website.
   - Include DNS, browser, server, TLS, load balancer conceptually.

## Commands to learn

```bash
pwd
ls -lah
cd
cat
grep
find
chmod
chown
sudo apt update
sudo apt install
ps aux
top
df -h
free -h
systemctl status
journalctl --no-pager
curl -I https://example.com
ip addr
ip route
ss -tulpn
```

## Interview practice

- What is DevOps?
- What happens when you open a website?
- What is DNS?
- What is a port?
- How do you check whether a Linux service is running?

## Checkpoint

She should be able to run a local web server, inspect the process, and explain the request path.

## Portfolio artifact

Publish: Linux basics notes and internet request flow diagram.

---

# Week 2: Git, GitHub, and collaboration

## Goal

Become comfortable with version control, because DevOps work is code-based and collaborative.

## Topics

- Repository, commit, branch, merge, pull request.
- Working tree, staging area, remote.
- `.gitignore`.
- Good commit messages.
- Pull request review process.
- Merge conflicts.
- Tags and releases.
- Semantic versioning.
- Markdown documentation.

## Hands-on labs

1. **Create GitHub account and first repository**
   - Add README.
   - Clone locally.
   - Commit and push changes.

2. **Branching workflow**
   - Create feature branch.
   - Open pull request.
   - Merge into main.

3. **Merge conflict lab**
   - Create conflicting edits.
   - Resolve them manually.

4. **Release notes lab**
   - Create a tag.
   - Write simple release notes.

## Commands to learn

```bash
git status
git init
git clone
git add
git commit -m "message"
git branch
git switch -c feature/name
git pull
git push
git log --oneline --graph
git diff
git merge
git tag
```

## Interview practice

- What is Git used for?
- What is a pull request?
- How do you resolve a merge conflict?
- What makes a good commit message?
- Why should infrastructure be stored in Git?

## Checkpoint

She should be able to create a repo, use branches, and explain a pull request.

## Portfolio artifact

Publish: Git workflow demo repository with README and screenshots.

---

# Week 3: Scripting and automation with Bash and Python basics

## Goal

Automate repetitive tasks and read simple scripts confidently.

## Topics

- Shell scripts.
- Variables, conditionals, loops.
- Exit codes.
- Environment variables.
- Reading command output.
- Python basics: variables, lists, dictionaries, functions.
- JSON and YAML basics.
- Working with files.
- Error handling mindset.

## Hands-on labs

1. **Bash health check script**
   - Print hostname, uptime, disk, memory, IP.
   - Save output to a log file.

2. **Log search script**
   - Search a file for error patterns.
   - Count errors.

3. **Python inventory parser**
   - Read a CSV of servers.
   - Print servers by environment.

4. **Environment variables lab**
   - Store config in env vars instead of hardcoding.

## Example Bash script idea

```bash
#!/usr/bin/env bash
set -euo pipefail

echo "Host: $(hostname)"
echo "Uptime: $(uptime -p)"
df -h /
free -h
ip addr show
```

## Interview practice

- Why is automation important?
- What is an environment variable?
- What is an exit code?
- How do you make a script safer?
- Bash vs Python: when would you use each?

## Checkpoint

She should be able to write and explain a simple health-check script.

## Portfolio artifact

Publish: `ops-scripts` repository with Bash and Python scripts plus README.

---

# Week 4: Cloud fundamentals, IAM, networking, and compute

## Goal

Learn one cloud provider well enough to deploy and explain basic infrastructure.

## Choose one primary cloud

Recommended:

- **AWS** if targeting many general DevOps jobs.
- **Azure** if targeting Microsoft-heavy Dublin employers.

Do not study all clouds at the start. Learn one deeply and know how to compare later.

## Topics

- Cloud regions and availability zones.
- Shared responsibility model.
- IAM users, groups, roles, policies.
- Virtual networks: VPC/VNet, subnet, route table, internet gateway.
- Security groups / NSGs.
- Compute instances: EC2 / Azure VM.
- Object storage: S3 / Blob Storage.
- Managed databases conceptually.
- Cost management and budgets.

## Hands-on labs

1. **Cloud account safety**
   - Enable MFA.
   - Create budget alert.
   - Avoid root/admin daily use.

2. **Create a simple VM**
   - Deploy Ubuntu VM.
   - SSH into it.
   - Install nginx.
   - Access web page.

3. **Security group lab**
   - Allow HTTP.
   - Block HTTP.
   - Observe behavior.

4. **Object storage lab**
   - Upload static file.
   - Understand public vs private access.

5. **Architecture diagram**
   - Draw user -> internet -> security group -> VM -> app.

## Interview practice

- What is the shared responsibility model?
- What is IAM?
- What is a security group?
- What is a region vs availability zone?
- How do you avoid unexpected cloud costs?

## Checkpoint

She should be able to deploy a VM securely and explain every cloud component used.

## Portfolio artifact

Publish: cloud VM deployment notes and architecture diagram.

---

# Week 5: Docker and container fundamentals

## Goal

Package an application consistently and understand why containers are used.

## Topics

- What problem Docker solves.
- Image vs container.
- Dockerfile.
- Build context.
- Ports and volumes.
- Environment variables.
- Docker Compose.
- Container logs and troubleshooting.
- Image tags and registries.
- Basic container security: small images, no secrets in images, non-root users.

## Hands-on labs

1. **Run existing containers**
   - nginx, redis, or postgres.
   - Inspect logs and ports.

2. **Dockerize a small app**
   - Use Python Flask, Node.js, or static nginx site.
   - Build image.
   - Run locally.

3. **Docker Compose lab**
   - App + database or app + redis.
   - Use environment variables.

4. **Debug broken container**
   - Wrong port, missing env var, failing command.
   - Inspect logs and fix.

## Commands to learn

```bash
docker ps
docker images
docker build -t myapp:local .
docker run -p 8080:80 myapp:local
docker logs <container>
docker exec -it <container> sh
docker stop <container>
docker rm <container>
docker compose up
docker compose down
```

## Interview practice

- What is the difference between an image and a container?
- Why use Docker?
- What is a Dockerfile?
- How do you troubleshoot a container that exits immediately?
- Where should secrets be stored?

## Checkpoint

She should be able to build and run a containerized app and troubleshoot logs.

## Portfolio artifact

Publish: Dockerized app repository with README and run instructions.

---

# Week 6: CI/CD with GitHub Actions

## Goal

Automate build, test, and deployment steps.

## Topics

- CI vs CD.
- Pipeline stages.
- Runners.
- Workflow YAML.
- Secrets in CI.
- Build artifacts.
- Unit tests conceptually.
- Linting conceptually.
- Deployment strategies: manual, automatic, blue/green, canary conceptually.
- Rollback basics.

## Hands-on labs

1. **First GitHub Actions workflow**
   - Trigger on push.
   - Run simple commands.

2. **Build Docker image in CI**
   - Build image on pull request.
   - Fail pipeline intentionally and fix it.

3. **Add tests or linting**
   - Use a minimal test command.
   - Make failure visible.

4. **Deploy to VM manually from CI or document safe deployment**
   - If using cloud, keep it simple and secure.
   - Alternative: deployment artifact only.

## Example workflow skeleton

```yaml
name: ci

on:
  push:
    branches: [main]
  pull_request:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Build Docker image
        run: docker build -t demo-app:${{ github.sha }} .
```

## Interview practice

- What is CI/CD?
- What should happen in a pipeline?
- How do you handle secrets in CI?
- What would you do if a pipeline suddenly fails?
- What is rollback?

## Checkpoint

She should be able to explain and demonstrate a working CI pipeline.

## Portfolio artifact

Publish: GitHub Actions pipeline in the Dockerized app repository.

---

# Week 7: Infrastructure as Code with Terraform

## Goal

Create repeatable cloud infrastructure using code.

## Topics

- Why Infrastructure as Code exists.
- Terraform providers, resources, variables, outputs.
- State file and why it matters.
- Plan and apply workflow.
- Remote state conceptually.
- Modules conceptually.
- Idempotency.
- Drift.
- Security: never commit secrets or state with sensitive data.

## Hands-on labs

1. **Local Terraform basics**
   - Use a simple provider if cloud cost is a concern.
   - Practice `init`, `plan`, `apply`, `destroy`.

2. **Provision cloud network and VM**
   - VPC/VNet, subnet, security group/NSG, VM.
   - Output public IP.

3. **Variables and outputs**
   - Parameterize region, instance size, tags.

4. **Destroy resources**
   - Verify no cloud charges continue.

5. **README documentation**
   - Explain prerequisites, commands, architecture, cost warning.

## Commands to learn

```bash
terraform fmt
terraform init
terraform validate
terraform plan
terraform apply
terraform destroy
terraform state list
```

## Interview practice

- What is Infrastructure as Code?
- What is Terraform state?
- What is the difference between `plan` and `apply`?
- How do you avoid committing secrets?
- What is infrastructure drift?

## Checkpoint

She should be able to provision and destroy simple infrastructure safely.

## Portfolio artifact

Publish: Terraform repository with architecture diagram and cost-safety notes.

---

# Week 8: Monitoring, logging, reliability, and operations

## Goal

Learn how DevOps supports running systems, not just deploying them.

## Topics

- Metrics, logs, traces.
- Golden signals: latency, traffic, errors, saturation.
- Dashboards and alerts.
- Health checks.
- Log levels.
- Incident response.
- Runbooks.
- Post-incident review.
- SLO basics.
- Capacity and scaling basics.

## Hands-on labs

1. **Application logging lab**
   - Add structured-ish logs to sample app.
   - Generate success and error logs.

2. **Health endpoint**
   - Add `/health` endpoint or static health check.
   - Document expected response.

3. **Monitoring lab**
   - Use cloud monitoring or local Prometheus/Grafana if comfortable.
   - Track CPU/memory or HTTP status.

4. **Incident runbook**
   - “Application is down.”
   - Include detection, triage, rollback, escalation, communication.

5. **Post-incident review**
   - Simulate failed deployment and write review.

## Interview practice

- What is the difference between metrics and logs?
- What alerts would you create for a web app?
- What is a runbook?
- How do you investigate a failed deployment?
- What is an SLO?

## Checkpoint

She should be able to detect, explain, and document an application issue.

## Portfolio artifact

Publish: monitoring notes, runbook, and incident review.

---

# Week 9: Kubernetes fundamentals and platform thinking

## Goal

Understand Kubernetes enough to discuss it intelligently and run simple workloads.

## Topics

- Why Kubernetes exists.
- Cluster, node, pod, deployment, service, ingress, namespace.
- Declarative YAML.
- ConfigMaps and Secrets.
- Rolling updates.
- Resource requests and limits.
- Liveness and readiness probes.
- Helm conceptually.
- Managed Kubernetes: EKS, AKS, GKE conceptually.

## Hands-on labs

Use Docker Desktop Kubernetes, minikube, or kind.

1. **Deploy sample app**
   - Create deployment.
   - Expose service.

2. **Scale app**
   - Change replicas.
   - Observe pods.

3. **Rolling update**
   - Change image tag.
   - Watch rollout.

4. **Break and fix**
   - Wrong image name or port.
   - Inspect pod events and logs.

## Commands to learn

```bash
kubectl get nodes
kubectl get pods
kubectl get deployments
kubectl get services
kubectl describe pod <pod>
kubectl logs <pod>
kubectl apply -f file.yaml
kubectl rollout status deployment/<name>
kubectl scale deployment/<name> --replicas=3
kubectl delete -f file.yaml
```

## Interview practice

- What is a pod?
- What is a deployment?
- What is a service?
- How do you troubleshoot a pod that is CrashLoopBackOff?
- What are readiness and liveness probes?

## Checkpoint

She should be able to deploy, scale, update, and troubleshoot a simple Kubernetes app.

## Portfolio artifact

Publish: Kubernetes YAML and troubleshooting notes.

---

# Week 10: Capstone, job applications, and interview readiness

## Goal

Assemble a portfolio strong enough for junior DevOps interviews in a competitive market.

## Capstone project: production-like app delivery platform

Build and document:

- A simple web application.
- Dockerfile and Docker Compose for local development.
- GitHub Actions CI pipeline.
- Terraform infrastructure for cloud VM/network or static hosting.
- Deployment documentation.
- Monitoring/logging basics.
- Incident runbook and rollback plan.
- Architecture diagram.
- Cost and security notes.

Minimum accepted capstone:

```text
User -> DNS/domain optional -> Cloud VM/security group -> Dockerized app -> Logs/health check -> Runbook
```

Stronger capstone:

```text
User -> Load balancer -> Cloud VM or container platform -> Dockerized app -> CI/CD -> Terraform -> Monitoring -> Incident runbook
```

## CV focus

Add a “DevOps Lab Portfolio” section:

```text
DevOps Lab Portfolio
- Built a Dockerized web application with GitHub Actions CI pipeline for automated build validation.
- Provisioned cloud infrastructure using Terraform, including network, security rules, and compute resources.
- Created Linux operational runbooks for service health checks, logs, disk, memory, and network troubleshooting.
- Practiced incident response by simulating failed deployments, documenting rollback steps, and writing post-incident reviews.
- Deployed and troubleshot basic Kubernetes workloads locally using deployments, services, logs, and rollout commands.
```

## LinkedIn headline examples

- Junior DevOps Candidate | Linux, AWS/Azure, Docker, Terraform, GitHub Actions
- Aspiring DevOps Engineer in Dublin | Cloud, CI/CD, Containers, IaC Portfolio

## Mock interview set

She must answer these aloud and support answers with portfolio examples:

1. Tell me about yourself.
2. Why DevOps?
3. Explain your capstone architecture.
4. What happens when a user opens your application?
5. How does your CI pipeline work?
6. What is Docker and why did you use it?
7. What is Terraform state?
8. How do you secure cloud credentials?
9. How do you troubleshoot a failed deployment?
10. How do you troubleshoot a Linux server running out of disk?
11. What is the difference between metrics and logs?
12. What is Kubernetes used for?
13. Explain pod vs deployment vs service.
14. How would you roll back a bad release?
15. What is the difference between dev, staging, and production?
16. What would you monitor for a web application?
17. What is least privilege?
18. How do you handle not knowing something?
19. Describe a time you solved a difficult problem.
20. Why should we hire you over another junior candidate?

## Final readiness checklist

- [ ] Can use Linux confidently for basic operations.
- [ ] Can use Git branches, pull requests, and commits.
- [ ] Can write simple Bash/Python automation.
- [ ] Can explain DNS, HTTP, ports, firewalls, and security groups.
- [ ] Can deploy a VM in AWS or Azure safely.
- [ ] Can Dockerize and run an application.
- [ ] Can create a GitHub Actions pipeline.
- [ ] Can write and apply Terraform safely.
- [ ] Can explain monitoring, logging, incidents, and rollback.
- [ ] Can deploy and debug simple Kubernetes workloads.
- [ ] Has a completed capstone with diagrams and README files.
- [ ] Has tailored CV and LinkedIn for junior DevOps roles.
- [ ] Has completed at least five mock interviews.

## Extra work to stand out

- Add unit tests to the sample app.
- Add a real domain name if affordable.
- Add HTTPS using Caddy, nginx, or cloud certificate service.
- Use Ansible for VM configuration.
- Add Dependabot or security scanning.
- Add pre-commit hooks.
- Create a small cost dashboard or monthly cloud cost note.
- Attend Dublin cloud/DevOps meetups and write short summaries.
- Apply also for Cloud Support, Technical Support, NOC, and Release Engineer roles as stepping stones.
