# sysmon-telemetry-basics
Configuring and analyzing Windows endpoint telemetry using Microsoft Sysmon.
# Sysmon Telemetry Configuration & Analysis

###  Objective
Deploy advanced Windows system logging to capture process creation and network connections, mimicking an enterprise SOC environment. 

###  Tools Used
* **Microsoft Sysmon:** System Monitor for advanced endpoint telemetry.
* **SwiftOnSecurity Configuration:** Industry standard XML configuration filtering out benign system noise to highlight genuine threats.
* **Windows Event Viewer:** For parsing and analyzing the generated operational logs.

###  Execution & Analysis
1. Installed Sysmon64 using the SwiftOnSecurity ruleset via elevated PowerShell.
2. Generated test telemetry by executing standard networking commands (`ping`).
3. Navigated to `Microsoft-Windows-Sysmon/Operational` in Event Viewer.
4. Successfully isolated **Event ID 1 (Process Create)**, identifying the specific Process ID (PID), executable path, and command line arguments used during the test.

###  Action Demonstration
<img width="1777" height="1060" alt="sysmon-demo" src="https://github.com/user-attachments/assets/0f133c8d-dd18-40e7-9edd-bad33cc6ca4a" />


###  Key Learning
Standard Windows logging often misses granular command line execution details. Sysmon bridges this gap, providing the exact telemetry required for a SOC Analyst to trace the origin and behavior of a process.
