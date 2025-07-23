# Detection Engineering Repository

A comprehensive repository for detection rules, queries, and threat hunting content across multiple platforms and security tools.

## Repository Structure

This repository is organized by platform, SIEM tools, and threat categories to provide comprehensive detection coverage for modern security operations.

### Platforms
- **Windows**: Sysmon, Event Logs, PowerShell, WMI, Registry monitoring
- **Linux**: auditd, syslog, process monitoring, file integrity monitoring
- **macOS**: Unified Logs, osquery, Endpoint Security framework
- **Cloud**: AWS, Azure, GCP, and Kubernetes detection rules
- **Network**: Suricata, Zeek, Snort, NetFlow rules

### SIEM Platforms
- **Splunk**: SPL queries, alerts, and dashboards
- **Elastic**: Detection rules, Watcher alerts, Kibana dashboards
- **Microsoft Sentinel**: KQL analytics rules and hunting queries
- **Google Chronicle**: YARA-L rules and detection logic
- **IBM QRadar**: Custom rules and building blocks

### Threat Intelligence & Framework Mapping
- IOCs organized by type (IPs, domains, hashes, URLs)
- YARA rules for malware detection
- Sigma rules for cross-platform compatibility
- MITRE ATT&CK framework mapping

## Getting Started

1. Navigate to the relevant platform directory
2. Review the detection rules and their metadata
3. Adapt rules to your environment
4. Test thoroughly before deploying to production

## Contributing

Please ensure all detection rules include:
- Clear title and description
- MITRE ATT&CK mapping
- Data source requirements
- False positive considerations
- Testing instructions
