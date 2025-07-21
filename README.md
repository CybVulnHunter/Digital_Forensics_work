# 🕵️ Digital Forensics Work

**CybVulnHunter’s Windows Forensics Toolkit & Scripts**

---

## 📖 Overview

This repository contains PowerShell scripts, investigation guides, and notes focused on Windows forensics. These resources are crafted for digital investigators, incident responders, and cybersecurity enthusiasts seeking to analyze Windows systems and extract forensic evidence.

## 🔧 Contents

- **Window_Forensics_PS/**  
  PowerShell scripts to collect forensic artefacts:
  - Event logs extraction
  - Registry snapshots
  - ART (Access, Recent, Typed URL) item grabs  
  - And more specific artefact collectors

- **Incident_Response_team/**  
  Guidelines and playbooks tailored for incident response teams operating in Windows-centric environments.

- **Digital_Forensics_Windows/**  
  General reference notes, tool comparisons, and best practices for Windows forensic investigations.

- **README.md**  
  You are reading it 😊

---

## 🚀 Getting Started

1. **Clone the repository**  
   ```bash
   git clone https://github.com/CybVulnHunter/Digital_Forensics_work.git
   cd Digital_Forensics_work
   ```

2. **Review the PowerShell tools** under `Window_Forensics_PS/`.

3. **Run scripts** in an elevated PowerShell session on a Windows investigation machine or controlled environment.

4. **Follow playbooks** located in the `Incident_Response_team/` folder for structured analysis guidance.

---

## 🧭 Use Cases

- Collect volatile and non-volatile Windows forensic artefacts.
- Create event timeline and registry analysis.
- Automate routine forensic tasks using PowerShell.
- Establish incident response protocols aligned with forensic best practices.

---

## ℹ️ Requirements

- Windows 10 / 11 or Server 2016+
- Windows PowerShell 5.1 or PowerShell 7+
- Administrative privileges (for artefact collection)
- (Optional) Forensic workstation with read‑only mounting tools

---

## 🔐 Usage & Caution

- **Read the script headers first** for usage instructions and parameters.
- Test scripts on **non-production systems** to ensure safety.
- Always **run with administrator privileges** to access system artefacts.
- **Handle all outputs responsibly**—these often contain sensitive data.

---

## 📝 Contributing

Contributions, enhancements, bug fixes, or new artefact collectors are welcome. Feel free to submit pull requests or open issues detailing proposed changes.
