# Wazuh + Suricata + DVWA SOC Home Lab

## Project Overview

Built a local Security Operations Center (SOC) home lab on Kali Linux to detect and investigate SQL injection attempts using Wazuh SIEM, Suricata IDS, DVWA, Docker, and the Wazuh Agent.

## Architecture

```text
SQL Injection Test
        |
        v
       DVWA
        |
        v
  Docker Network
        |
        v
 Suricata IDS
        |
        v
      eve.json
        |
        v
   Wazuh Agent
        |
        v
  Wazuh Manager
        |
        v
  Wazuh Indexer
        |
        v
 Wazuh Dashboard
        |
        v
   Threat Hunting
```

## Technologies Used

* Kali Linux
* Wazuh SIEM
* Suricata IDS
* Docker and Docker Compose
* DVWA
* Linux
* HTTP and JSON logs
* Custom Suricata detection rules

## Implementation

1. Deployed Wazuh Manager, Indexer, and Dashboard using Docker.
2. Deployed DVWA as a controlled vulnerable web application.
3. Configured Suricata to monitor the relevant Docker network traffic.
4. Created a custom Suricata rule for the SQL injection request pattern tested in the lab.
5. Verified detection in `/var/log/suricata/eve.json`.
6. Configured the Wazuh Agent to collect Suricata JSON events.
7. Verified the resulting alert in Wazuh Threat Hunting.

## Detection Rule

The custom rule detects the specific request pattern used during testing. It is a lab-specific demonstration and does not detect every possible SQL injection technique.

## Evidence

Screenshots documenting the Wazuh dashboard, DVWA application, Suricata alert, Wazuh Threat Hunting event, and Docker containers are included in this repository.

## Skills Demonstrated

* SIEM deployment and log ingestion
* IDS configuration and rule testing
* Linux administration and troubleshooting
* Docker networking
* JSON security-event analysis
* Security alert investigation
* Threat Hunting

## Lab Safety

Testing was performed against a local DVWA instance in a controlled environment. DVWA is intentionally vulnerable and should not be exposed to the public internet.
