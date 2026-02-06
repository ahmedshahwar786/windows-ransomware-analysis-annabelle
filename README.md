# Comprehensive Malware Analysis – Annabelle Ransomware (.NET)

## Overview
This repository contains a full malware analysis case study of **Annabelle.exe**, a Windows-based malicious .NET executable exhibiting ransomware-like behavior. The project demonstrates the complete malware analysis lifecycle using both static and dynamic techniques inside isolated lab environments.

The goal is to simulate real-world malware research and DFIR workflows and produce actionable detection and remediation guidance.

---

## Malware Summary

- Sample Name: Annabelle.exe  
- Malware Type: Ransomware-like / Encryptor  
- Platform: Windows (.NET)  
- Behavior:
  - Registry persistence
  - Disables Windows security protections
  - Cryptographic functionality
  - System modification for defense evasion

---

## Objectives

- Perform static and dynamic malware analysis  
- Identify persistence mechanisms  
- Extract Indicators of Compromise (IOCs)  
- Analyze cryptographic and malicious functionality  
- Document findings in a professional technical report  

---

## Lab Environment

### Windows (FLARE VM)
- Ghidra  
- x64dbg  
- PE-bear  
- CFF Explorer  
- Strings  
- Procmon  
- Regshot  

### Linux (Kali)
- Wireshark  
- tcpdump  
- strings  

### Virtualization
- VirtualBox

---

## Analysis Workflow

### 1. Static Analysis
- PE header and section inspection  
- Strings extraction  
- .NET dependency analysis  
- Ghidra decompilation  
- Identification of cryptographic classes:
  - RijndaelManaged  
  - CryptoStream  
  - SHA512Managed  

### 2. Dynamic Analysis
- Execution inside isolated FLARE VM  
- Procmon monitoring of file and registry activity  
- Regshot comparison (before vs after)  
- Wireshark capture of network traffic  

### 3. Key Findings
- Registry persistence via Run key  
- Windows Defender real-time monitoring disabled  
- System restore and recovery features disabled  
- Cryptographic routines present  
- Ransom note displayed during execution  

---


---

## Defense Evasion Observed

- DisableAntiSpyware = 1  
- DisableRealtimeMonitoring = 1  
- DisableTaskMgr = 1  
- DisableRegistryTools = 1  
- DisableCMD = 2  

---

## Indicators of Compromise (IOCs)

- MD5: 0F743287C9911B4B1C726C7C7EDCAF7D  
- SHA256: 716335BA5CD1E7186C40295B199190E2B6655E48F1C1CBE12139BA67FAA5E1AC  
- File Path: C:\Analysis\annabelle.exe  
- Registry Persistence Key:
  HKCU\Software\Microsoft\Windows\CurrentVersion\Run\UpdateBackup  

(Full IOC table available in report)

---

## Report

📄 Full technical report with screenshots and step-by-step analysis:

[View Report](Report.pdf)

---

## What This Project Demonstrates

- Malware triage and classification  
- Static analysis using reverse engineering tools  
- Dynamic behavioral analysis  
- Registry and persistence detection  
- Cryptographic malware identification  
- Professional technical reporting  

---

## Disclaimer

All analysis was performed on educational malware samples inside isolated virtual machines.  
NO live malware binaries are included in this repository.

