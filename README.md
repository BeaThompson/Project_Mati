# Project_Mati

**Project_Mati** is a collection of Sigma detection rules, supporting lab simulations, and detection engineering documentation. The goal is to build a practical detection engineering portfolio that maps directly to real-world adversary techniques, leveraging the MITRE ATT&CK framework.

---

## **Repository Overview**

| Folder/File | Description |
|-------------|-------------|
| `/rules/` | Sigma detection rules categorized by operating system (Windows, Linux, Cloud). |
| `/labs/` | Lab simulations and write-ups that demonstrate adversary behaviors and their detection. |
| `/docs/` | Guides and references on detection engineering, SIEM pipelines, and Sigma rule creation. |
| `/tools/config/` | Custom Sigma configurations and mappings for parsing rules into different formats like Wazuh/Elastic. |

---

##  **Current Sigma Rules**

| Rule File | Description | MITRE ATT&CK |
|-----------|-------------|--------------|
| `suspicious_powershell.yml` | Detects use of PowerShell EncodedCommand flag. | T1059.001 |
| `service_creation.yml` | Identifies suspicious Windows service creation patterns. | T1543.003 |
| `defender_bypass.yml` | Detects attempts to disable Microsoft Defender via command line. | T1562.001 |

More rules to be added continuously.

---

## **Lab Simulations**

- **Encoded PowerShell Command**: Demonstrates obfuscation via EncodedCommand flag with detection strategy using Sysmon.
- **HoneyUser Detection**: Implements a honeyuser in Active Directory to detect unauthorized account enumeration attempts.
  
All labs are documented in `/labs/` with step-by-step procedures, observations, and MITRE mapping.

---

## **Documentation**

- **Rule-Writing Guide**: Step-by-step guide to writing effective Sigma rules.
- **SIEM Pipeline**: Overview of how logs flow through collection, normalization, enrichment, and detection in a SOC SIEM.

---

## **Future Enhancements**

- Additional Sigma rules for Linux and Cloud environments.
- Example implementations in Wazuh, Elastic, and Splunk
