# Format the fixes and workarounds as Knowledge Base (KB) Articles or Standard Operating Procedures (SOPs).
## Knowledge Base (KB)
* The purpose of a Knowledge Base (KB) is to document a specific breakdown, troubleshooting path and repair.
* The tone of a Knowledge Base (KB) is "Forensic"(Root Cause Analysis format), i.e., "the directory permissions were mistakenly set to...".
* The trigger of a Knowledge Base (KB) in an error, an outage, or a support ticket escalation.

## Standard Operating Procedures (SOPs)
* The purpose of a Standard Operating Procedures (SOPs) is to document a routine, repeatable, and standardized deployment process.
* The tone of a Standard Operating Procedures (SOPs) is "Directive"("must", "shall") , i.e.,  "the directory permission *must* allow...".
* The trigger of a Standard Operating Procedures (SOPs) is provisioning new infrastructure, on-boarding, or scheduled maintenance.

**Each adheres to standard IT Service Management (ITSM) and systems administration frameworks. If your KB article documented how to fix a permission error on a directory, your SOP is the document that teaches a technician how to properly create and secure that directory from scratch during server setup.**

---

When a lab breaks or a command fails, document it as if it is a tier-2 escalation ticket using these Markdown structures:

# Turning "Notes" into KB's - KB Format Example

---

# KB00124: Resolving Permission Denied on Grain Scale Upload Directory

## Issue
Operators were unable to write log payloads to `/var/log/scale_data/`, resulting in an application hang.

## Root Cause Analysis (RCA)
The directory ownership was mistakenly set to `root:root` with `755` permissions during provisioning, blocking the `scaleops` group.

## Resolution / Workaround
1. Corrected directory group ownership to the designated operational group.
2. Adjusted write permissions for group members.

```bash
sudo chown -R root:scaleops /var/log/scale_data/
sudo chmod -R 775 /var/log/scale_data/
```

## Verification
Verified resolution by switching to user `john` and successfully touching a test file:
```bash
sudo -u john touch /var/log/scale_data/test_write.log
```


---


# Turning "Notes" into SOP's - SOP Format Example

Standard Operating Procedure (SOP) is proactive. It is a step-by-step instruction manual written so that any technician can deploy a service or complete a task perfectly the first time.

---

# SOP-SYS-004: Provisioning Secure Role-Based Access Directories

## 1. Objective
This procedure defines the standard configuration for establishing secure, shared data directories on enterprise Linux instances. Adherence to this standard ensures proper role-based isolation and prevents permission-related application failures.

## 2. Prerequisites
* Root or full `sudo` administrative privileges on the target system.
* Pre-existing operational user groups (e.g., `scaleops`).

## 3. Step-by-Step Execution Procedure

### Step 3.1: Create the Target Directory
Initialize the directory path within the system logging environment:
```bash
sudo mkdir -p /var/log/scale_data/
```

### Step 3.2: Configure Directory Permissions
Apply explicit POSIX permissions. The directory must allow full read, write, and execute permissions for the owner and group, but restrict write access from public system users (775):
```bash
sudo chmod 775 /var/log/scale_data/
```

### Step 3.3: Assign Role-Based Ownership
Set the user ownership to `root` and delegate group control to the designated operational group:
```bash
sudo chown root:scaleops /var/log/scale_data/
```

## 4. Quality Assurance & Verification
Validate the access model by simulating a non-root group user creation task. Replace `john` with an active member of the designated operational group:

```bash
# Attempt to write a validation log payload as a standard group user
sudo -u john touch /var/log/scale_data/provision_test.log

# Verify the file was created successfully with accurate permissions
ls -l /var/log/scale_data/provision_test.log
```

## 5. References
* *UNIX and Linux System Administration Handbook* (5th Edition) — Chapter 5: The Filesystem.
* *The Practice of System and Network Administration* (3rd Edition) — Chapter 17: Service Planning and Engineering, Chapter 29: Debugging, Chapter 30: Fixing Things Once, Chapter 31: Documentation.
