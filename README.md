# SOP – Resolving Legit Security Findings in Candor

## Purpose

This document describes the process for identifying, investigating, remediating, and closing Legit Security findings that appear in the Candor Application Security Scorecard.

---

# 1. Identifying Legit Findings

1. Log in to Candor.

2. Navigate to:

   Application Security Scorecard

3. Review the application's security status.

4. Applications showing a Red status require immediate attention.

5. A Red status may impact Change Management approvals and can prevent deployments from being approved.

---

# 2. Review Legit Security Findings

1. Open the Legit Security section for the application.
2. Review all open findings.
3. Findings may include:

   * Secret Detected
   * Misconfiguration
   * Other security-related issues

Example findings:

* Client Secret exposed in source code
* Password exposed in repository
* Code review enforcement not enabled

---

# 3. Understand SLA Requirements

Legit findings must be resolved within the defined SLA:

| Severity | SLA      |
| -------- | -------- |
| Critical | 30 Days  |
| High     | 60 Days  |
| Medium   | 180 Days |
| Low      | 360 Days |

Monitor the finding age carefully to avoid SLA breaches.

Example:

* High Severity Finding
* Current Age = 46 Days
* Remaining Time = 14 Days

---

# 4. Download the Legit Report

1. Download the finding report from Legit Security.
2. Review the report contents.

The report contains:

* Finding ID
* Repository Name
* Issue Type
* Payload Reference
* GitHub Link
* Severity
* Additional remediation details

Important:
The Finding ID must be retained, as it will be required during the closure process.

---

# 5. Investigate the Finding

## Secret Detection Findings

If the finding indicates:

"Secret Detected"

The report usually provides:

* Repository name
* GitHub URL
* File location
* Line number

### Investigation Steps

1. Open the GitHub link provided in the report.
2. Log in to GitHub.
3. Navigate to the specified file.
4. Review the referenced line number.

Example:

* Line 6 contains a Client Secret.
* Legit identifies this as an exposed credential.

Common exposed secrets include:

* Client Secrets
* Passwords
* API Keys
* Access Tokens
* Credentials

---

# 6. Determine Where the Secret Exists

Before remediation:

1. Verify which branch contains the secret.
2. Check whether the branch still exists.

Possible scenarios:

### Scenario A – Secret Exists in Active Branch

The secret is present in:

* master
* development
* another active branch

Action:

* Remove or vault the secret.
* Commit the change.

### Scenario B – Secret Exists Only in Commit History

The referenced branch no longer exists.

Action:

* Investigate commit history.
* Perform repository history cleanup.

---

# 7. Secret Remediation

Depending on the application requirements:

### Option 1 – Remove the Secret

If the value is not required:

* Remove it from source code.

### Option 2 – Vault the Secret

If the value is required:

* Move the secret to the approved vaulting mechanism.
* Replace hardcoded credentials with secure references.

The exact vaulting process may vary by application and security requirements.

---

# 8. Commit History Cleanup Process

If the secret exists in repository history, additional cleanup is required.

## Prerequisites

Before starting:

1. Java 11 or above installed.
2. Git Bash installed.
3. Write access to repository.
4. Branch protection temporarily disabled if required.

---

## Local Setup

Create:

### Folder 1

backup

Used for repository clone activities.

### Folder 2

LegitActivity

Used for cleanup activities and BFG tool execution.

---

## Repository Preparation

1. Obtain repository URL.
2. Clone repository as a mirror.
3. Follow cleanup instructions provided by the DevOps/Legit process.

The cleanup process typically includes:

* Cloning repository
* Running Git cleanup commands
* Executing BFG Repo-Cleaner
* Replacing/removing secrets
* Cleaning repository history
* Rebuilding repository metadata

---

# 9. Push Updated Repository

After cleanup:

1. Push the cleaned repository changes back to GitHub.
2. This is typically the final step of the cleanup process.

Important:

Write access issues commonly occur during the push operation.

Therefore:

* Obtain repository write access before starting the Legit remediation activity.

---

# 10. Raise Required Requests

After successful remediation and repository update:

## Request 1 – DevOps Team

Raise a request to:

Delete/Clean Commit History

Purpose:

* Ensure historical secret exposure is removed completely.

## Request 2 – Legit Team

Raise a closure request.

Include:

* Legit Finding ID
* Repository details
* Evidence of remediation
* Confirmation that repository updates have been completed

Important:
Without the Finding ID, Legit team will not process the closure request.

---

# 11. Closure Validation

1. Legit Team reviews the submitted evidence.
2. DevOps validates cleanup activities if required.
3. Legit finding is closed.
4. Candor Application Security Scorecard is refreshed.
5. Application status returns to compliant state after successful validation.

---

# End-to-End Process Flow

Candor →
Application Security Scorecard →
Open Legit Findings →
Download Report →
Capture Finding ID →
Review Repository & GitHub Link →
Locate Exact File and Line Number →
Identify Secret/Misconfiguration →
Remove or Vault Secret →
Perform Commit History Cleanup (if required) →
Push Changes to Repository →
Raise DevOps Cleanup Request →
Raise Legit Closure Request →
Legit Review →
Finding Closed →
Candor Updated
