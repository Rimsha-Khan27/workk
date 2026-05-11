# ILS Alerts – SOP / Failure Handling Document

## Overview

This document provides the monitoring and handling procedure for ILS infrastructure alerts related to CPU usage, memory usage, and disk space threshold breaches across identified servers.

---

## Purpose of this Document

The purpose of this document is to provide the operational steps to be followed whenever ILS alert notifications are received for CPU, memory, or disk utilization issues on the listed servers.

---

## Scope of Services

This SOP covers:

* Memory usage alerts
* CPU usage alerts
* Disk threshold breach alerts
* Housekeeping verification
* Escalation to Wintel team
* Storage expansion request process

---

## Frequency and Timeline

| Alert Type          | Monitoring Frequency            | Action Required                               |
| ------------------- | ------------------------------- | --------------------------------------------- |
| CPU Usage Alerts    | As and when alerts are received | Verify processes and monitor usage            |
| Memory Usage Alerts | As and when alerts are received | Notify support mailbox                        |
| Disk Space Alerts   | As and when alerts are received | Perform housekeeping and escalate if required |

---

# Operating Procedure

## 1. Memory Usage Alerts

### Server Details

* awgidssql000001

### Procedure

When a memory usage alert is received for the above server:

1. Send an email notification to:

   [public_cloud_services_mailbox@aig.com](mailto:public_cloud_services_mailbox@aig.com)

2. Refer to the sample alert email below for reference:

   “RE_Average (2 samples) memory usage is now 80%, which is above the warning threshold (80%).”

---

## 2. CPU Usage Alerts

### Applicable Servers

* dwgsascs2505001
* pwgsascs2505005
* awgsascs2505004
* twgsascs2505004
* dwgsascs2505004

### Procedure

Upon receiving a CPU usage alert for any of the above servers:

1. Login to the affected server using the provided login instructions document.

2. Open Task Manager and verify:

   * Active users
   * Running processes
   * CPU and memory consumption

3. Monitor the CPU utilization.

4. In some cases, high CPU or memory usage may occur due to disconnected user sessions.

5. Coordinate with users and request them to disconnect inactive sessions.

6. Verify whether the CPU usage returns below the threshold limit after session disconnection.

---

## 3. Disk Space Threshold Alerts

### Applicable Servers

* pwgsascs2505010
* pwgsascs2505011

### Procedure

1. Perform housekeeping activities on the impacted servers.

2. Verify whether the disk utilization returns below the configured threshold.

3. If the disk space still remains above the threshold after housekeeping:

   * Wintel team will coordinate with the server managed owners.

4. Raise an incident ticket to the Wintel team if additional support is required.

5. If the Wintel team recommends storage expansion:

   * Raise a storage expansion request.

6. Sample Request Reference:

   * REQ5746514

---

## 4. Additional Memory / Disk Alerts

### Applicable Servers

* mwawdbcm25051
* mwawdbcm25052

### Procedure

1. When memory usage alerts are received for the above servers:

   * Send an email to:

     [public_cloud_services_mailbox@aig.com](mailto:public_cloud_services_mailbox@aig.com)

2. If required:

   * Raise a request for disk space extension.

---

## 5. Multiple Disk Threshold Breach Alerts

### Applicable Servers

* pwawadbcm25051
* pwawadbcm25052
* pwawadbcm25053

### Procedure

1. When disk threshold breach alerts are received for the above servers:

   * Send an email notification to:

     [public_cloud_services_mailbox@aig.com](mailto:public_cloud_services_mailbox@aig.com)

2. Refer to the sample alert email:

   “RE Multiple INC Disk threshold breached on F Housekeeping require”

---

# Escalation Process

| Scenario                                     | Action                                               |
| -------------------------------------------- | ---------------------------------------------------- |
| Memory usage threshold breached              | Notify public cloud services mailbox                 |
| CPU usage high                               | Verify Task Manager and disconnect inactive sessions |
| Disk threshold still high after housekeeping | Raise incident to Wintel team                        |
| Storage expansion required                   | Raise storage request                                |

---

# Notes

* Ensure all housekeeping activities are completed before escalation.
* Always monitor the server after corrective actions are performed.
* Attach screenshots or alert emails while raising incidents or requests wherever applicable.
