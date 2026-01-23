# Wazuh-SIEM-Lab
## Overview
Built and configured Wazuh SIEM environment in a virtualized home lab to demonstrate security monitoring, file integrity monitoring, and incident detection.
![Wazuh Dashboard](screenshots/Agent_Connected.png)

## Project Goals
- Deploy functional SIEM solution for security monitoring.
- Implement file integrity monitoring across Windows endpoints.
- Demonstrate real-time detection alerting capabilities.
- Gain practical experience with SIEM.
## Architecture
Environment
  - Wazuh Manager: Ubuntu 22.04 Desktop (VirtualBox)
  - Wazuh Agent: Windows 11 Host
  - Version: Wazuh 4.14

Network Configuration
  - Adapter 1 (NAT): Internet connection.
  - Adapter 2 (Host-Only): Host-VM communication for agent-manager.
  - Bridged adapter had compatibility issues with my hardware, so I had to implement a dual-adapter approach.
  - [Architecture Diagram](docs/Architecure.png)
## Technologies Used
 - SIEM Platform: Wazuh 4.14 (Manager, indexer, dashboard)
 - OS: Ubuntu 22.04 (VM), Windows 10/11 (Host)
 - Virtualization: Oracle VirtualBox
 - Monitoring: File Integrity Monitoring (Syscheck)
## Implementation Stages
### 1. Wazuh Manager Installation
  - Deployed Ubuntu Desktop in VirtualBox. (8GB RAM, 6 Cores)
  - Configured dual network adapters (NAT + Host-Only) for connectivity.
  - Installed Wazuh all-in-one deployment including manager,indexer,dashboard.
  - Verified services and accessed web dashboard at https://localhost.
### 2. Windows Agent Deployment
  - Downloaded/Installed Wazuh agent MSI package on Windows host.
  - Generated agent authentication key using manage_agents utility.
  - Registered agent with manager using the VirtualBox Host-Only adapter.
  - Verified agent connectivity in Wazuh Dashboard.
### 3. File Integrity Monitoring Configuration
  - Configured real-time FIM on Windows agent via ossec.conf.
  - Monitored test directory C:\Users\[USERNAME]\WazuhTest.
  - Enabled real-time monitoring with realtime="yes" parameter.
  - Restarted agent service to apply changes.
### 4. Testing & Validation
  - Created, modified, and deleted test files in monitored directory.
  - Observed real-time FIM alerts in Wazuh Dashboard.
  - Analyzed alert details including timestamps, file hashes, and event types.
  - Verified detection of file creation, modification, and deletion events.
## Screenshots
  - [View Screenshots](./screenshots)
    - [Wazuh all-in-one installation script](screenshots/Installation_&_Setup.png)
    - [Wazuh dashboard before agent connected](screenshots/Wazuh_Dashboard.png)
    - [Adding Windows agent](screenshots/Adding_Windows_Agent.png)
    - [Wazuh dashboard with Windows agent connected](screenshots/Agent_Connected.png)
    - [All FIM Alerts](screenshots/FIM_Events.png)
    - [FIM alerts for real-time testing](screenshots/FIM_Alert_For_Test_Directory.png)
## Skills Demonstrated
  - SIEM deployment and configuration.
  - Linux system administration. (Ubuntu)
  - Windows endpoint security monitoring.
  - Network troubleshooting and configuration.
  - Security event analysis and correlation.
  - File integrity monitoring implementation.
  - Agent-based security architecture.
  - Technical documentation and troubleshooting
## Future Enhancements
  - Deploy additional Linux agents for multi-OS monitoring.
  - Implement custom detection rules for specific attack patterns.
  - Configure email alerting for critical events.
  - Integrate with threat intelligence feeds.
  - Create automated incident response playbooks.
  - Add vulnerability detection scanning.

## Connect With Me!

[<img align="left" alt="JamieDeMasi | LinkedIn" width="22px" src="https://cdn.simpleicons.org/linkedin/0A66C2" />][linkedin]

[linkedin]: https://www.linkedin.com/in/jamie-demasi-4bb616248/



