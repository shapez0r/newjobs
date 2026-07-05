# Week 4 Detailed Workbook: Linux Basics and Remote Troubleshooting

## Table of contents

- [Purpose of this workbook](#purpose-of-this-workbook)
- [Week 4 target level](#week-4-target-level)
- [Suggested weekly schedule](#suggested-weekly-schedule)
- [Day-by-day Week 4 study order](#day-by-day-week-4-study-order)
- [Required Week 4 portfolio artifacts](#required-week-4-portfolio-artifacts)
- [Part 1: Comprehensive Week 4 topics](#part-1-comprehensive-week-4-topics)
  - [1. Linux mindset for data center technicians](#1-linux-mindset-for-data-center-technicians)
  - [2. Ubuntu Server VM setup](#2-ubuntu-server-vm-setup)
  - [3. Shell navigation and filesystem layout](#3-shell-navigation-and-filesystem-layout)
  - [4. Files directories and safe editing](#4-files-directories-and-safe-editing)
  - [5. Users groups sudo and permissions](#5-users-groups-sudo-and-permissions)
  - [6. Package management with apt](#6-package-management-with-apt)
  - [7. Processes CPU and memory checks](#7-processes-cpu-and-memory-checks)
  - [8. Disk and filesystem checks](#8-disk-and-filesystem-checks)
  - [9. Linux network checks](#9-linux-network-checks)
  - [10. Services and systemd](#10-services-and-systemd)
  - [11. Logs and journalctl](#11-logs-and-journalctl)
  - [12. SSH and remote access basics](#12-ssh-and-remote-access-basics)
  - [13. File transfer with scp and sftp](#13-file-transfer-with-scp-and-sftp)
  - [14. Safe command execution](#14-safe-command-execution)
  - [15. Evidence ticket updates and handover notes](#15-evidence-ticket-updates-and-handover-notes)
- [Part 2: Week 4 questions and model answers](#part-2-week-4-questions-and-model-answers)
  - [Linux basics](#linux-basics)
  - [Files users and permissions](#files-users-and-permissions)
  - [Processes resources and disks](#processes-resources-and-disks)
  - [Services logs and troubleshooting](#services-logs-and-troubleshooting)
  - [SSH remote work and safe commands](#ssh-remote-work-and-safe-commands)
  - [Scenario questions](#scenario-questions)
- [Part 3: Lab exercises with hints](#part-3-lab-exercises-with-hints)
  - [Lab 1: Install and prepare an Ubuntu Server VM](#lab-1-install-and-prepare-an-ubuntu-server-vm)
  - [Lab 2: Practice command-line navigation](#lab-2-practice-command-line-navigation)
  - [Lab 3: Create files directories and permissions notes](#lab-3-create-files-directories-and-permissions-notes)
  - [Lab 4: Practice users groups and sudo checks](#lab-4-practice-users-groups-and-sudo-checks)
  - [Lab 5: Install nginx and record package evidence](#lab-5-install-nginx-and-record-package-evidence)
  - [Lab 6: Troubleshoot a systemd service](#lab-6-troubleshoot-a-systemd-service)
  - [Lab 7: Inspect logs with journalctl and var log](#lab-7-inspect-logs-with-journalctl-and-var-log)
  - [Lab 8: Build a Linux resource health runbook](#lab-8-build-a-linux-resource-health-runbook)
  - [Lab 9: Build a disk usage investigation note](#lab-9-build-a-disk-usage-investigation-note)
  - [Lab 10: Build a Linux network check note](#lab-10-build-a-linux-network-check-note)
  - [Lab 11: Practice SSH safely in a lab](#lab-11-practice-ssh-safely-in-a-lab)
  - [Lab 12: Practice safe text editing](#lab-12-practice-safe-text-editing)
  - [Lab 13: Run a remote-hands simulation](#lab-13-run-a-remote-hands-simulation)
  - [Lab 14: Write mock Linux troubleshooting ticket updates](#lab-14-write-mock-linux-troubleshooting-ticket-updates)
  - [Lab 15: Build a Week 4 mock interview script](#lab-15-build-a-week-4-mock-interview-script)
  - [Lab 16: Final Week 4 self-assessment](#lab-16-final-week-4-self-assessment)
- [Part 4: Templates to copy into the portfolio](#part-4-templates-to-copy-into-the-portfolio)
  - [Linux health check runbook template](#linux-health-check-runbook-template)
  - [Command evidence log template](#command-evidence-log-template)
  - [Service troubleshooting ticket template](#service-troubleshooting-ticket-template)
  - [SSH access checklist](#ssh-access-checklist)
  - [Linux handover template](#linux-handover-template)
  - [Safe command review checklist](#safe-command-review-checklist)
- [Part 5: Week 4 final exam](#part-5-week-4-final-exam)
  - [Written exam](#written-exam)
  - [Practical exam](#practical-exam)
  - [Passing standard](#passing-standard)
- [Part 6: Interview positioning for Week 4](#part-6-interview-positioning-for-week-4)
  - [Strong interview themes](#strong-interview-themes)
  - [Example answer: checking service health](#example-answer-checking-service-health)
  - [Example answer: checking disk space](#example-answer-checking-disk-space)
  - [Example answer: safe command execution](#example-answer-safe-command-execution)
- [Part 7: Week 4 completion checklist](#part-7-week-4-completion-checklist)

## Purpose of this workbook

This workbook expands **Week 4** of the Data Center Engineer / Data Center Technician study plan. It is written for a complete beginner who needs to become comfortable with Linux command-line work requested by remote engineers.

The goal is not to become a Linux administrator in one week. The goal is to build practical operational confidence: log in, navigate safely, run evidence-gathering commands, inspect services and logs, check resource usage, follow instructions exactly, and document findings clearly.

By the end of this week, she should be able to use a Linux VM as a safe lab, explain what common commands prove, and write professional ticket updates without making unauthorized changes.

## Week 4 target level

The target is not "I typed a few commands." The target is:

- She can install or use an Ubuntu Server VM for practice.
- She can navigate the Linux filesystem and explain common directories.
- She can use basic commands such as `pwd`, `ls`, `cd`, `cat`, `less`, `grep`, `find`, `touch`, `mkdir`, `cp`, `mv`, and `rm` safely.
- She can explain users, groups, `sudo`, file ownership, and permissions at a junior level.
- She can check CPU, memory, disk, uptime, processes, and network state.
- She can start, stop, restart, and check a service with `systemctl` in a lab.
- She can inspect logs with `journalctl` and files under `/var/log`.
- She can explain SSH, SCP, and SFTP conceptually.
- She can follow remote instructions exactly and pause when a command is unclear or risky.
- She can collect command evidence and write clear ticket updates, escalation notes, and handover notes.

## Suggested weekly schedule

| Day | Focus | Main output |
|---|---|---|
| Day 1 | Ubuntu VM, shell navigation, filesystem layout | VM notes and navigation command sheet |
| Day 2 | Files, users, groups, sudo, and permissions | Permissions notes and safe command examples |
| Day 3 | Processes, CPU, memory, disk, and network checks | Resource health runbook |
| Day 4 | Services, systemd, nginx lab, logs, SSH, and file transfer | Service troubleshooting notes and log evidence |
| Day 5 | Remote-hands simulation, ticket updates, escalation, and interview practice | Mock tickets, handover, and interview script |
| Day 6 optional | Repeat commands without notes | Screenshots and corrected command notes |
| Day 7 optional | Rest or catch-up | Clean Week 4 portfolio |

## Day-by-day Week 4 study order

Use this as the working order for the week. The detailed reference sections, questions, labs, and templates remain below, but the learner should complete them in this sequence.

| Day | Study sections | Practice | Portfolio output |
|---|---|---|---|
| Day 1 | Sections 1-4: Linux mindset, Ubuntu VM setup, shell navigation, filesystem, files, directories, and editing basics | Labs 1-3; Questions 1-16 | VM setup notes, navigation sheet, and file practice notes |
| Day 2 | Sections 5-6 and 14: users, groups, sudo, permissions, packages, and safe command execution | Labs 4-5 and 12; Questions 17-28 and 49-56 | Permissions notes, package evidence, and safe editing notes |
| Day 3 | Sections 7-9: processes, CPU, memory, disk, filesystems, and network checks | Labs 8-10; Questions 29-40 | Resource health runbook, disk investigation note, and network check note |
| Day 4 | Sections 10-13: services, systemd, logs, SSH, SCP, and SFTP | Labs 6-7 and 11; Questions 41-48 | Service troubleshooting notes, log evidence, and SSH checklist |
| Day 5 | Section 15: evidence, ticket updates, handovers, escalation, and interview readiness | Labs 13-16; Questions 57-70 | Remote-hands simulation, mock tickets, interview script, and self-assessment |
| Day 6 optional | Repeat practical checks from memory and improve weak notes | Re-run health checks and service troubleshooting | Screenshots, corrected notes, and command evidence |
| Day 7 optional | Rest or catch-up | Fill missing portfolio files | Ready-to-review Week 4 portfolio |

## Required Week 4 portfolio artifacts

Create a folder called `week-04-linux-remote-troubleshooting` and include:

```text
week-04-linux-remote-troubleshooting/
  README.md
  01-ubuntu-server-vm-setup.md
  02-linux-navigation-command-sheet.md
  03-files-directories-permissions-notes.md
  04-users-groups-sudo-notes.md
  05-package-management-evidence.md
  06-systemd-nginx-service-lab.md
  07-log-inspection-notes.md
  08-linux-resource-health-runbook.md
  09-disk-usage-investigation-note.md
  10-linux-network-check-note.md
  11-ssh-access-checklist.md
  12-safe-text-editing-notes.md
  13-remote-hands-simulation.md
  14-mock-linux-ticket-updates.md
  15-week-04-interview-script.md
  16-week-04-self-assessment.md
```

---

# Part 1: Comprehensive Week 4 topics

## 1. Linux mindset for data center technicians

Linux is common in data centers because many servers, appliances, monitoring systems, storage systems, and network tools run on Linux or Linux-like operating systems.

A data center technician does not always administer Linux systems directly, but remote engineers may ask her to:

- Log in to a console or SSH session.
- Check service status.
- Run health-check commands.
- Collect logs or command output.
- Confirm disk, memory, CPU, or network state.
- Edit a lab configuration file.
- Follow a runbook during an incident.

The core mindset is: **observe carefully, run only authorized commands, record evidence, and avoid changing state unless instructed and approved**.

## 2. Ubuntu Server VM setup

Ubuntu Server is a good lab environment because it is common, free, and well documented. A VM is safer than practicing on a real production system.

### Recommended VM settings

- 2 CPUs if the laptop can handle it.
- 2-4 GB RAM.
- 20 GB virtual disk.
- NAT networking to start.
- Hostname such as `week04-linux-lab`.
- Non-root user account.
- OpenSSH server optional but useful for SSH practice.

### What to document

- VM name.
- CPU, RAM, disk size.
- Username created.
- Hostname.
- Network mode.
- IP address.
- How to access the console.

## 3. Shell navigation and filesystem layout

The shell is the command-line environment. The learner should get comfortable moving around and reading information without changing anything.

### Essential navigation commands

```bash
pwd
ls
ls -lah
cd
cd ..
cd ~
```

### Common directories

| Directory | Plain meaning |
|---|---|
| `/` | Root of the filesystem |
| `/home` | User home directories |
| `/etc` | System configuration files |
| `/var` | Variable data such as logs and caches |
| `/var/log` | Log files |
| `/tmp` | Temporary files |
| `/usr` | Userland programs and libraries |
| `/bin` and `/sbin` | Essential system commands |
| `/dev` | Device files |
| `/proc` | Runtime kernel/process information |
| `/mnt` and `/media` | Mount points for filesystems |

### Safe beginner rule

Reading is usually safer than writing. Commands like `ls`, `cat`, `less`, `df`, `free`, `uptime`, and `systemctl status` are observation commands. Commands like `rm`, `mv`, `chmod`, `chown`, `systemctl restart`, and editing files can change state and need care.

## 4. Files directories and safe editing

### File viewing commands

```bash
cat file.txt
less file.txt
head file.txt
tail file.txt
tail -f /var/log/syslog
grep "error" file.txt
```

### File and directory commands

```bash
touch notes.txt
mkdir lab
cp source.txt copy.txt
mv oldname.txt newname.txt
rm unwanted.txt
```

### Safe editing

Beginners can use `nano` because the commands are visible at the bottom of the screen. `vim` is useful but requires practice to avoid getting stuck.

Before editing configuration:

- Confirm the file path.
- Confirm the requested change.
- Make a backup if approved.
- Use a lab first.
- Record before and after state.
- Validate the service or command after editing.

## 5. Users groups sudo and permissions

Linux controls access through users, groups, ownership, and permissions.

### Useful commands

```bash
whoami
id
groups
sudo -l
ls -l
chmod
chown
```

### Permission basics

Example:

```text
-rw-r--r-- 1 root root 1200 Jul  5 10:00 config.txt
```

- First character indicates file type.
- `rw-` means owner can read and write.
- `r--` means group can read.
- `r--` means others can read.
- Owner is `root`.
- Group is `root`.

### Sudo

`sudo` allows an authorized user to run a command with elevated privileges. It is powerful and should be treated as a risk boundary. A beginner should understand that `sudo` can change the system.

## 6. Package management with apt

Ubuntu uses `apt` for package management.

### Common commands

```bash
sudo apt update
sudo apt install nginx
apt list --installed
apt show nginx
```

### Operational caution

Installing or updating packages changes the system. In production, this normally requires approval or a change window. In the Week 4 lab VM, package installation is safe practice.

### What to document

- Package name.
- Command run.
- Version installed if visible.
- Service created or changed.
- Validation result.

## 7. Processes CPU and memory checks

### Commands

```bash
ps aux
top
uptime
free -h
lscpu
```

### What they show

- `ps aux`: running processes.
- `top`: live process and resource view.
- `uptime`: how long the system has been up and load averages.
- `free -h`: memory usage.
- `lscpu`: CPU information.

### Data center use

Remote engineers may ask for CPU/memory checks during a performance issue. A technician should record the output and time, not guess whether it is "bad" unless she has thresholds or guidance.

## 8. Disk and filesystem checks

### Commands

```bash
lsblk
df -h
du -sh *
mount
find /var/log -type f -size +100M
```

### What they show

- `lsblk`: block devices and partitions.
- `df -h`: mounted filesystem usage.
- `du -sh *`: space used by files/directories in the current location.
- `mount`: mounted filesystems.
- `find`: search for files matching conditions.

### Safe disk troubleshooting

Checking disk usage is usually safe. Deleting files is not safe without approval. A junior technician should identify where space is used and escalate before removing anything.

## 9. Linux network checks

### Commands

```bash
ip addr
ip link
ip route
ping -c 4 8.8.8.8
resolvectl status
ss -tulpn
```

### What they show

- `ip addr`: IP addresses on interfaces.
- `ip link`: interface state and MAC information.
- `ip route`: routing table and default gateway.
- `ping`: basic connectivity test.
- `resolvectl status`: DNS resolver information on many systems.
- `ss -tulpn`: listening TCP/UDP sockets and associated processes.

### Safe boundary

Commands such as `ip link set`, `systemctl restart networking`, or editing network configuration can disconnect the system. Do not run them in production without explicit authorization.

## 10. Services and systemd

Many Linux services are managed by `systemd`.

### Common commands

```bash
systemctl status nginx
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl enable nginx
sudo systemctl disable nginx
```

### Observation versus change

`systemctl status nginx` observes. `start`, `stop`, `restart`, `enable`, and `disable` change state.

### Data center use

A remote engineer might ask a technician to confirm whether a service is running, collect the last log lines, or restart a lab service. In production, restarting services can cause impact and needs approval.

## 11. Logs and journalctl

Logs provide evidence of what happened.

### Common log locations

- `/var/log/syslog`
- `/var/log/auth.log`
- `/var/log/kern.log`
- `/var/log/nginx/access.log`
- `/var/log/nginx/error.log`

### Journal commands

```bash
journalctl --no-pager
journalctl -u nginx --no-pager
journalctl -u nginx --since "1 hour ago" --no-pager
```

### Good log evidence

Useful log evidence includes:

- Timestamp.
- Service name.
- Exact error line.
- What action happened before the error.
- Whether the error repeats.

Avoid pasting huge logs into tickets. Include relevant excerpts and attach full logs if the process allows it.

## 12. SSH and remote access basics

SSH provides secure remote command-line access.

### Concepts

- SSH server: service accepting connections.
- SSH client: tool used to connect.
- Username: account used to log in.
- Hostname/IP: target system.
- Port: usually `22`.
- Key-based authentication: uses public/private keys.
- Password authentication: uses a password, if allowed.

### Example

```bash
ssh username@192.168.56.10
```

### Safety

Before logging in:

- Confirm the hostname/IP.
- Confirm authorization.
- Confirm whether the system is production or lab.
- Record what commands are requested.
- Avoid storing or exposing passwords.

## 13. File transfer with scp and sftp

SCP and SFTP move files over SSH.

### Examples

```bash
scp report.txt username@192.168.56.10:/home/username/
sftp username@192.168.56.10
```

### Data center use

Remote engineers may ask for logs or screenshots. A technician should follow approved data-handling rules and avoid copying sensitive customer data into personal locations.

## 14. Safe command execution

Before running a command from a remote engineer, she should understand:

- What system is targeted.
- What the command does.
- Whether it changes state.
- Whether approval is recorded.
- What output to capture.
- What success or failure looks like.
- What rollback or escalation path exists.

### Commands that deserve extra caution

```bash
rm
mv
chmod
chown
dd
mkfs
mount
umount
reboot
shutdown
systemctl restart
ip link set
apt upgrade
```

### Good response to unclear commands

"Before I run this, can you confirm what the command is expected to change and whether approval is recorded in the ticket?"

## 15. Evidence ticket updates and handover notes

Good Linux troubleshooting notes are specific and reproducible.

### Evidence update structure

```text
Time:
Host:
Access method:
Commands run:
Key output:
Interpretation:
Changes made:
Current status:
Blocker/risk:
Next step:
```

### Handover structure

```text
Ticket:
Host:
Summary:
Timeline:
Commands run:
Findings:
Changes made:
Current state:
Open risks:
Next recommended action:
Do not do:
```

### Strong junior behavior

She should be honest about what she knows. It is better to write "I confirmed `nginx` is inactive and captured the journal error below" than to claim "the web server is broken" without evidence.

---

# Part 2: Week 4 questions and model answers

Use these as flashcards and mock interview practice. She should answer aloud first, then compare with the model answer.

## Linux basics

### 1. Why does a data center technician need Linux basics?

**Answer:** Many servers and tools in data centers run Linux. A technician may need to log in, run checks, collect evidence, inspect logs, and follow remote engineer instructions.

### 2. What is a shell?

**Answer:** A shell is a command-line environment where a user can run commands and interact with the operating system.

### 3. What does `pwd` show?

**Answer:** It shows the current working directory.

### 4. What does `ls -lah` show?

**Answer:** It lists files with details, including hidden files, permissions, owner, size, and timestamps in human-readable format.

### 5. What does `cd ..` do?

**Answer:** It moves up one directory.

### 6. What is `/etc` used for?

**Answer:** `/etc` commonly stores system and service configuration files.

### 7. What is `/var/log` used for?

**Answer:** `/var/log` stores many system and application log files.

### 8. What is `/home` used for?

**Answer:** `/home` contains user home directories.

### 9. What is the difference between an observation command and a change command?

**Answer:** An observation command reads information, like `df -h` or `systemctl status`. A change command modifies state, like `rm`, `chmod`, or `systemctl restart`.

### 10. Why is a lab VM useful?

**Answer:** It allows safe practice without risking production systems.

## Files users and permissions

### 11. What does `cat` do?

**Answer:** It prints a file's contents to the terminal.

### 12. When is `less` better than `cat`?

**Answer:** `less` is better for reading longer files because it allows scrolling and searching.

### 13. What does `grep` do?

**Answer:** It searches text for matching patterns.

### 14. What does `find` do?

**Answer:** It searches for files or directories based on criteria such as name, type, size, or location.

### 15. What does `touch notes.txt` do?

**Answer:** It creates an empty file if it does not exist, or updates its timestamp if it does.

### 16. What does `mkdir lab` do?

**Answer:** It creates a directory called `lab`.

### 17. What does `whoami` show?

**Answer:** It shows the current username.

### 18. What does `id` show?

**Answer:** It shows the current user's UID, GID, and group memberships.

### 19. What is `sudo`?

**Answer:** `sudo` lets an authorized user run commands with elevated privileges. It can change important system state, so it must be used carefully.

### 20. What does `chmod` do?

**Answer:** It changes file or directory permissions.

### 21. What does `chown` do?

**Answer:** It changes file or directory ownership.

### 22. What does `-rw-r--r--` mean?

**Answer:** It means the owner can read/write, the group can read, and others can read.

### 23. Why should she be careful with `rm`?

**Answer:** `rm` deletes files. In production, deleting the wrong file can cause data loss or service failure.

### 24. Why make a backup before editing a config file?

**Answer:** A backup allows comparison or rollback if the edit breaks the service or is incorrect.

## Processes resources and disks

### 25. What does `ps aux` show?

**Answer:** It shows running processes and details such as user, CPU, memory, and command.

### 26. What does `top` show?

**Answer:** It shows a live view of processes and resource usage.

### 27. What does `uptime` show?

**Answer:** It shows how long the system has been running and the load averages.

### 28. What does `free -h` show?

**Answer:** It shows memory usage in human-readable units.

### 29. What does `df -h` show?

**Answer:** It shows disk usage for mounted filesystems.

### 30. What does `du -sh *` show?

**Answer:** It estimates disk usage for files and directories in the current directory.

### 31. What does `lsblk` show?

**Answer:** It shows block devices, partitions, and mount points.

### 32. Why is a full filesystem dangerous?

**Answer:** Services may fail to write logs, databases may stop, and the operating system can become unstable.

### 33. Should she delete logs to free space without approval?

**Answer:** No. Logs may be evidence. She should identify large files and escalate for approval before deleting anything.

### 34. What does `ip addr` show?

**Answer:** It shows network interfaces and IP addresses.

### 35. What does `ip route` show?

**Answer:** It shows routes, including the default gateway.

### 36. What does `ss -tulpn` show?

**Answer:** It shows listening TCP/UDP sockets and associated processes, where permissions allow.

## Services logs and troubleshooting

### 37. What is `systemd`?

**Answer:** `systemd` is a common Linux system and service manager.

### 38. What does `systemctl status nginx` do?

**Answer:** It shows the current status of the `nginx` service without changing it.

### 39. What does `sudo systemctl restart nginx` do?

**Answer:** It restarts the `nginx` service and changes system state. In production it needs approval.

### 40. What is `journalctl` used for?

**Answer:** It reads logs from the systemd journal.

### 41. How can she view logs for one service?

**Answer:** She can use a command such as `journalctl -u nginx --no-pager`.

### 42. What should a useful log excerpt include?

**Answer:** Timestamp, service name, exact error line, and nearby context if needed.

### 43. Why should she avoid pasting huge logs into tickets?

**Answer:** Huge logs are hard to read and may contain sensitive information. She should include relevant excerpts and attach full logs only according to process.

### 44. What does it mean if a service is `inactive`?

**Answer:** It means the service is not currently running. Whether that is bad depends on whether the service is expected to run.

### 45. What does it mean if a service is `failed`?

**Answer:** It means the service attempted to run but entered a failed state, usually with errors available in status output or logs.

### 46. Why record the exact command output?

**Answer:** It allows engineers to verify evidence, correlate with logs, and continue troubleshooting without repeating work.

## SSH remote work and safe commands

### 47. What is SSH?

**Answer:** SSH is a secure protocol for remote command-line access.

### 48. What is SCP?

**Answer:** SCP is a way to copy files over SSH.

### 49. What is SFTP?

**Answer:** SFTP is an interactive file transfer protocol that uses SSH.

### 50. What should she confirm before logging into a server?

**Answer:** Correct hostname/IP, authorization, environment, account, access method, and requested task.

### 51. Why should passwords not be pasted into tickets?

**Answer:** Tickets may be visible to many people and retained for audit. Passwords must be handled through approved secure channels.

### 52. Why is `sudo` a risk boundary?

**Answer:** It can run commands with elevated privileges and change important system files, services, or data.

### 53. What should she do if she does not understand a command?

**Answer:** Pause and ask what the command does, what it changes, and whether approval is recorded.

### 54. Why can `systemctl restart` be risky?

**Answer:** Restarting a service can interrupt users or production workloads.

### 55. Why can network commands that change interface state be risky?

**Answer:** They can disconnect the server or break remote access.

### 56. What is the safest way to execute remote instructions?

**Answer:** Confirm the target, copy the command exactly, understand whether it changes state, run it only if authorized, capture output, and report results.

## Scenario questions

### 57. A remote engineer asks her to run `df -h`. Is that safe?

**Answer:** Yes, it is an observation command that shows filesystem usage. She should still run it on the correct host and capture output.

### 58. A remote engineer asks her to run `rm -rf /var/log/*`. What should she do?

**Answer:** Stop and escalate. That command deletes logs and could remove evidence or harm troubleshooting. It needs explicit approval and a safer plan.

### 59. Nginx is down in the lab. What should she check?

**Answer:** Run `systemctl status nginx`, inspect `journalctl -u nginx --no-pager`, check configuration if instructed, and document exact errors.

### 60. Disk usage is 100%. What should she do first?

**Answer:** Record `df -h`, identify large directories with approved read-only checks such as `du -sh *`, and escalate before deleting anything.

### 61. A command output differs from what the remote engineer expected. What should she do?

**Answer:** Report the exact output and ask for the next instruction. She should not improvise.

### 62. She logs into the wrong host by mistake but has not run commands. What should she do?

**Answer:** Disconnect, document the mistake if required by process, notify the engineer or supervisor, and reconnect to the correct host only after verification.

### 63. A service restart is requested in chat but not in the ticket. What should she do?

**Answer:** Ask for the instruction and approval to be recorded in the ticket or approved channel before restarting.

### 64. She sees permission denied while reading a log. What should she do?

**Answer:** Report the permission issue and ask whether `sudo` is approved or whether another team should collect the log.

### 65. The command prompt shows she is root. Why does that matter?

**Answer:** Root has full control of the system. Mistakes can be more damaging, so she should be extra careful and confirm commands before running them.

### 66. How should she update a ticket after running health checks?

**Answer:** Include time, host, commands run, key output, interpretation, changes made or none made, current status, and next step.

### 67. What should a handover note include?

**Answer:** Ticket, host, summary, timeline, commands run, findings, changes made, current state, open risks, next action, and warnings about what not to do.

### 68. How can she collect evidence without changing the system?

**Answer:** Use read-only commands like `status`, `df -h`, `free -h`, `ip addr`, `ip route`, `journalctl`, `cat`, `less`, and `grep`.

### 69. Why is exact spelling important in Linux?

**Answer:** Linux commands, paths, and filenames are case-sensitive and exact. A small typo can refer to a different file or fail entirely.

### 70. What should she be able to do at the end of Week 4?

**Answer:** Log into a Linux lab system, run basic health checks, inspect service status and logs, explain command output, follow safe instructions, and write clear ticket updates.

---

# Part 3: Lab exercises with hints

Each lab should produce a portfolio artifact. The hints are there to guide her, but she should try first without looking.

## Lab 1: Install and prepare an Ubuntu Server VM

### Goal

Create a safe Linux lab environment.

### Steps

1. Create a VM in VirtualBox or VMware.
2. Install Ubuntu Server or use an existing Ubuntu Server VM.
3. Set hostname to `week04-linux-lab`.
4. Create a non-root user.
5. Record CPU, RAM, disk size, username, and network mode.
6. Log in successfully.
7. Run `hostname`, `whoami`, `ip addr`, and `df -h`.

### Hints

- NAT networking is fine for the first install.
- Do not use a real personal password in portfolio notes.
- Screenshots are useful evidence.

### Expected portfolio output

`01-ubuntu-server-vm-setup.md`

## Lab 2: Practice command-line navigation

### Goal

Become comfortable moving around the filesystem.

### Steps

Run and explain:

```bash
pwd
ls
ls -lah
cd /
ls
cd /var/log
ls
cd ~
```

Create a command sheet with each command, what it does, and example output.

### Hints

- Do not memorize blindly. Say what changed after each command.
- Notice the difference between relative and absolute paths.

### Expected portfolio output

`02-linux-navigation-command-sheet.md`

## Lab 3: Create files directories and permissions notes

### Goal

Practice basic file operations in a safe lab folder.

### Steps

```bash
mkdir ~/week04-file-lab
cd ~/week04-file-lab
touch notes.txt
echo "Linux practice" > notes.txt
cat notes.txt
cp notes.txt notes-copy.txt
mv notes-copy.txt notes-renamed.txt
ls -l
rm notes-renamed.txt
```

Write what each command did.

### Hints

- Only use `rm` inside the lab folder.
- Always run `pwd` if unsure where you are.

### Expected portfolio output

`03-files-directories-permissions-notes.md`

## Lab 4: Practice users groups and sudo checks

### Goal

Understand identity and permissions.

### Steps

Run:

```bash
whoami
id
groups
sudo -l
ls -l /etc/passwd
```

Explain what each command shows.

### Hints

- `sudo -l` may ask for a password.
- Do not change users or permissions unless a lab instruction specifically asks.

### Expected portfolio output

`04-users-groups-sudo-notes.md`

## Lab 5: Install nginx and record package evidence

### Goal

Practice package installation in a lab and document the change.

### Steps

In the lab VM only:

```bash
sudo apt update
sudo apt install nginx
apt show nginx
systemctl status nginx
```

Record:

- Commands run.
- Whether installation succeeded.
- Service status.
- Any errors.

### Hints

- This changes the lab VM, which is acceptable.
- In production, package installation requires approval.

### Expected portfolio output

`05-package-management-evidence.md`

## Lab 6: Troubleshoot a systemd service

### Goal

Practice service checks and a safe lab restart.

### Steps

In the lab VM:

```bash
systemctl status nginx
sudo systemctl stop nginx
systemctl status nginx
sudo systemctl start nginx
systemctl status nginx
```

Write a ticket-style note describing before state, action, and after state.

### Optional break/fix

If comfortable, make a backup of the nginx default config, introduce a small config error, run `sudo nginx -t`, inspect the error, then restore the backup.

### Hints

- Restarting services changes state. Keep it to the lab.
- `nginx -t` tests configuration without starting the service.

### Expected portfolio output

`06-systemd-nginx-service-lab.md`

## Lab 7: Inspect logs with journalctl and var log

### Goal

Practice finding service and system logs.

### Steps

Run:

```bash
journalctl -u nginx --no-pager | tail -30
sudo journalctl -u nginx --since "1 hour ago" --no-pager
ls -lah /var/log
sudo tail -50 /var/log/syslog
```

Record useful lines and explain what they show.

### Hints

- Do not paste hundreds of lines into notes.
- Include timestamps and service names.

### Expected portfolio output

`07-log-inspection-notes.md`

## Lab 8: Build a Linux resource health runbook

### Goal

Create a repeatable health-check process.

### Commands to include

```bash
uptime
free -h
df -h
lsblk
ps aux --sort=-%cpu | head
ps aux --sort=-%mem | head
ip addr
ip route
systemctl --failed
```

For each command, write what it checks and what output matters.

### Hints

- Keep it readable enough to use during an incident.
- Include "what to do if abnormal" notes.

### Expected portfolio output

`08-linux-resource-health-runbook.md`

## Lab 9: Build a disk usage investigation note

### Goal

Practice safe disk usage investigation.

### Steps

Run:

```bash
df -h
cd /var
sudo du -sh * 2>/dev/null | sort -h
```

Then write:

- Which filesystem has the most usage.
- Which `/var` directory appears largest.
- What evidence you would send to an engineer.
- Why you should not delete files without approval.

### Hints

- `du` may take time.
- Permission errors are normal; document them if they matter.

### Expected portfolio output

`09-disk-usage-investigation-note.md`

## Lab 10: Build a Linux network check note

### Goal

Practice Linux network checks from Week 3 in a Linux context.

### Steps

Run:

```bash
ip addr
ip link
ip route
ping -c 4 8.8.8.8
resolvectl status
ss -tulpn
```

Write what each command proves.

### Hints

- If internet ping fails, record the failure and continue.
- `ss -tulpn` may show more details with `sudo`.

### Expected portfolio output

`10-linux-network-check-note.md`

## Lab 11: Practice SSH safely in a lab

### Goal

Understand remote access without risking production systems.

### Steps

If SSH is installed and reachable:

1. Confirm the VM IP address.
2. From the host or another VM, connect with `ssh username@ip-address`.
3. Run `hostname`, `whoami`, and `pwd`.
4. Exit the session.
5. Document the steps.

If SSH is not reachable, create a checklist explaining what would need to be checked.

### Hints

- Use only lab systems.
- Do not publish passwords or private keys.

### Expected portfolio output

`11-ssh-access-checklist.md`

## Lab 12: Practice safe text editing

### Goal

Learn how to edit a lab file without panic.

### Steps

```bash
mkdir -p ~/week04-edit-lab
cd ~/week04-edit-lab
cp /etc/hosts hosts.copy
nano hosts.copy
```

Add a comment line at the bottom:

```text
# Week 4 editing practice
```

Save, exit, and run:

```bash
tail hosts.copy
```

### Hints

- Edit the copy, not `/etc/hosts`.
- Practice saving and exiting `nano`.

### Expected portfolio output

`12-safe-text-editing-notes.md`

## Lab 13: Run a remote-hands simulation

### Goal

Practice following instructions exactly.

### Scenario

A remote engineer sends:

```text
Please log into week04-linux-lab, confirm hostname, check disk usage, check nginx status, collect the last 20 nginx journal lines, and make no changes.
```

### Steps

1. Write an acknowledgement.
2. Run only the requested commands.
3. Record exact command output summaries.
4. Write a completion update.
5. Include "no changes made."

### Hints

- If nginx is not installed, report that clearly.
- Do not restart the service because it was not requested.

### Expected portfolio output

`13-remote-hands-simulation.md`

## Lab 14: Write mock Linux troubleshooting ticket updates

### Goal

Practice professional Linux communication.

### Scenarios

Write updates for:

1. Disk usage alert on `/`.
2. `nginx` service failed in lab.
3. Remote engineer asks for CPU and memory evidence.
4. Permission denied while trying to read a log.
5. Requested command appears destructive or unclear.

### For each scenario, include

- Acknowledgement.
- Commands run.
- Key evidence.
- Changes made or "no changes made."
- Blocker/risk.
- Next step or escalation request.

### Hints

- Keep updates factual.
- Do not diagnose beyond the evidence.

### Expected portfolio output

`14-mock-linux-ticket-updates.md`

## Lab 15: Build a Week 4 mock interview script

### Goal

Prepare confident spoken answers.

### Steps

Write 45-90 second answers for:

1. How do you check whether a Linux service is running?
2. How do you check disk space?
3. How do you check memory usage?
4. What is `sudo`?
5. What is SSH?
6. How do you inspect logs?
7. What would you do before running a command from a remote engineer?
8. How do you collect evidence without changing the system?
9. What would you do if a command failed with permission denied?
10. What have you practiced in your Linux lab?

### Hints

- Mention exact commands.
- Mention safe boundaries and documentation.
- Use portfolio evidence from the labs.

### Expected portfolio output

`15-week-04-interview-script.md`

## Lab 16: Final Week 4 self-assessment

### Goal

Check whether she can use Linux safely enough for beginner remote troubleshooting.

### Self-assessment table

| Skill | Can do without notes | Can do with notes | Need more practice |
|---|---|---|---|
| Log into Ubuntu Server VM | | | |
| Navigate the filesystem | | | |
| Explain common directories | | | |
| View files with `cat`, `less`, `head`, `tail` | | | |
| Search with `grep` and `find` | | | |
| Explain users, groups, sudo, and permissions | | | |
| Check CPU, memory, uptime, and processes | | | |
| Check disk usage with `df`, `du`, and `lsblk` | | | |
| Check network state with `ip` commands | | | |
| Check service status with `systemctl` | | | |
| Inspect logs with `journalctl` | | | |
| Explain SSH, SCP, and SFTP | | | |
| Follow remote instructions exactly | | | |
| Write Linux troubleshooting ticket updates | | | |
| Know when to stop and escalate | | | |

### Expected portfolio output

`16-week-04-self-assessment.md`

---

# Part 4: Templates to copy into the portfolio

## Linux health check runbook template

````markdown
# Linux Health Check Runbook

Host:
Date/time:
Technician:
Ticket:

## Identity

```bash
hostname
whoami
pwd
```

Expected:

## Resources

```bash
uptime
free -h
df -h
lsblk
```

Findings:

## Processes

```bash
ps aux --sort=-%cpu | head
ps aux --sort=-%mem | head
```

Findings:

## Network

```bash
ip addr
ip route
```

Findings:

## Services

```bash
systemctl --failed
systemctl status SERVICE_NAME
```

Findings:

## Logs

```bash
journalctl -u SERVICE_NAME --since "1 hour ago" --no-pager
```

Findings:
````

## Command evidence log template

```markdown
| Time | Host | Command | Key output | What it proves | Change made |
|---|---|---|---|---|---|
| | | | | | No |
```

## Service troubleshooting ticket template

```markdown
# Service Troubleshooting Ticket Update

Time:
Host:
Service:
Access method:
Commands run:
Service state:
Relevant log lines:
Changes made:
Validation:
Blocker/risk:
Next step:
```

## SSH access checklist

```markdown
# SSH Access Checklist

Ticket:
Target hostname:
Target IP:
Environment:
Username:
Approved access method:
Expected task:

## Before connecting

- [ ] Hostname/IP confirmed.
- [ ] Authorization confirmed.
- [ ] Production or lab status confirmed.
- [ ] Commands to run are understood.
- [ ] No credentials stored in ticket.

## After connecting

- [ ] `hostname` confirms expected host.
- [ ] `whoami` confirms expected user.
- [ ] Current directory checked with `pwd`.
- [ ] Commands run exactly as requested.
- [ ] Output captured.
- [ ] Session closed when complete.
```

## Linux handover template

```markdown
# Linux Handover Note

Ticket:
Host:
Prepared by:
Shift/date:

## Summary

## Timeline

## Commands run

## Findings

## Changes made

## Current state

## Open risks

## Next recommended action

## Do not do
```

## Safe command review checklist

```markdown
# Safe Command Review Checklist

Command:
Target host:
Requested by:
Ticket/change:

- [ ] I understand what the command does.
- [ ] I know whether it reads or changes state.
- [ ] The target host is confirmed.
- [ ] Approval is recorded if the command changes state.
- [ ] Expected output/result is understood.
- [ ] Rollback or escalation path is known if needed.
- [ ] I will capture output and update the ticket.

If any box cannot be checked, pause and ask for clarification.
```

---

# Part 5: Week 4 final exam

## Written exam

Answer these without looking at notes:

1. Explain why Linux is useful for data center technicians.
2. Explain the purpose of `/etc`, `/var/log`, `/home`, `/tmp`, and `/proc`.
3. Explain the difference between `cat`, `less`, `head`, and `tail`.
4. Explain users, groups, file ownership, and permissions.
5. Explain what `sudo` does and why it is risky.
6. Explain how to check disk usage.
7. Explain how to check memory usage.
8. Explain how to check running processes.
9. Explain how to check IP address and default gateway.
10. Explain how to check whether a service is running.
11. Explain how to inspect service logs.
12. Explain SSH, SCP, and SFTP.
13. List ten commands that are mostly read-only observation commands.
14. List ten commands or actions that require extra caution.
15. Write a ticket update after collecting Linux health-check evidence.

## Practical exam

Complete these tasks in the lab VM:

1. Log in and confirm hostname and user.
2. Navigate to `/var/log`, list files, and return home.
3. Create a lab directory and file under the home directory.
4. Explain permissions on one file using `ls -l`.
5. Run `uptime`, `free -h`, `df -h`, and `lsblk`.
6. Run `ip addr` and `ip route`.
7. Check `nginx` status or another installed service.
8. Inspect the last relevant logs for that service.
9. Write a short ticket update with command evidence.
10. Answer five Week 4 interview questions aloud.

## Passing standard

She passes Week 4 if she can:

- Use a Linux VM without fear.
- Navigate and inspect files safely.
- Explain users, groups, permissions, and `sudo`.
- Run health-check commands and explain the evidence.
- Check service status and logs.
- Explain SSH and file transfer basics.
- Follow remote instructions exactly.
- Write clear ticket updates and handover notes.
- Stop and escalate before running unclear or risky commands.

---

# Part 6: Interview positioning for Week 4

Week 4 gives her practical command-line credibility. She should not claim to be a Linux administrator. She should show that she can safely collect evidence and follow instructions.

## Strong interview themes

- I am comfortable using a Linux shell in a lab.
- I can run basic health-check commands and explain what they show.
- I understand which commands are read-only and which change state.
- I can check services and logs.
- I can use SSH conceptually and practice it safely.
- I document exact commands and output.
- I pause when a command is unclear, destructive, or not authorized.

## Example answer: checking service health

"I would first confirm I am on the correct host with `hostname` and that I have authorization. Then I would run `systemctl status service-name` to check whether the service is active, inactive, or failed. If it is failed, I would collect logs with `journalctl -u service-name --no-pager` or a time-bounded version. I would not restart the service unless the ticket or engineer specifically approved it."

## Example answer: checking disk space

"I would run `df -h` to see mounted filesystem usage, then use safe read-only checks such as `du -sh *` in the relevant directory to identify where space is being used. I would document the output and avoid deleting anything without approval, because logs or data may be needed for troubleshooting or audit."

## Example answer: safe command execution

"Before running a command from a remote engineer, I would confirm the target host, what the command does, whether it changes state, and whether approval is recorded. If I do not understand the command or it looks destructive, I would pause and ask for clarification. After running approved commands, I would capture the output and update the ticket."

---

# Part 7: Week 4 completion checklist

- [ ] I created a Week 4 portfolio folder.
- [ ] I installed or prepared an Ubuntu Server VM.
- [ ] I documented VM settings, hostname, user, and network mode.
- [ ] I practiced shell navigation.
- [ ] I can explain common Linux directories.
- [ ] I practiced file and directory commands in a safe lab folder.
- [ ] I can explain users, groups, sudo, ownership, and permissions.
- [ ] I installed nginx or another service in the lab.
- [ ] I can check service status with `systemctl`.
- [ ] I can inspect service logs with `journalctl`.
- [ ] I built a Linux resource health runbook.
- [ ] I practiced disk usage checks with `df`, `du`, and `lsblk`.
- [ ] I practiced Linux network checks with `ip addr`, `ip link`, and `ip route`.
- [ ] I created an SSH access checklist.
- [ ] I practiced safe text editing.
- [ ] I completed a remote-hands simulation.
- [ ] I wrote mock Linux troubleshooting ticket updates.
- [ ] I built a Week 4 mock interview script.
- [ ] I completed the Week 4 final exam.
- [ ] I can explain when to stop and escalate before running commands.
- [ ] My Week 4 portfolio folder is complete.
