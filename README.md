# System Hacking Using Kali Linux & Metasploit (MS17-010 / EternalBlue)

> **Educational use only.** This lab was performed in an isolated VM network I own/control. Do **not** test on systems you don’t have permission to assess.

## Objective
- Demonstrate the MS17-010 (EternalBlue) vulnerability in a Windows 7 VM.
- Walk through attacker workflow: reconnaissance → exploitation → post-exploitation.
- Document defenses and mitigations.

## Lab Setup & Tools
- **Attacker:** Kali Linux (Metasploit Framework)
- **Target:** Windows 7 VM (intentionally unpatched for the lab)
- **Network:** Host-only / NAT (isolated)
- **Utilities:** Nmap for recon

## Steps Performed (High-Level)
1. **Identify target & IP** on the Windows VM (e.g., `ipconfig`).
2. **Reconnaissance** with Nmap to confirm SMB (445) and OS fingerprint.
3. **Launch Metasploit**, select the EternalBlue module (MS17-010), configure target/host.
4. **Exploit** the target; a Meterpreter session is opened on success.
5. **Post-exploitation (demonstration only):** list files, take a screenshot, verify access, then close the session.

> In the `screenshots/` section below I’ve added proof-of-work images for each step.

## Defense & Mitigations
- Apply Microsoft’s security update for **MS17-010** on all affected hosts.
- **Disable SMBv1** and limit SMB exposure (firewall rules / segmentation).
- Enforce **rapid patching** and vulnerability management.
- Monitor SMB traffic with **IDS/IPS/SIEM** and alert on anomalies.
- Principle of least privilege & regular backup/restore testing.

## Outcome
- Confirmed how an unpatched SMBv1 host can be exploited via EternalBlue in a **controlled lab**.
- Practiced safe exploitation workflow and documented remediation steps.

## ​ Screenshots

<p align="center">
  <b>Step 1: Nmap Scan (Reconnaissance)</b><br>
  <img src="https://raw.githubusercontent.com/Monisha-krish/system-hacking-metasploit/main/screenshots/NMap_Scan.jpeg" width="500"/>
</p>

<p align="center">
  <b>Step 2: Searching for EternalBlue in Metasploit</b><br>
  <img src="https://raw.githubusercontent.com/Monisha-krish/system-hacking-metasploit/main/screenshots/msf_search.jpeg" width="500"/>
</p>

<p align="center">
  <b>Step 3: Exploit Setup in Metasploit</b><br>
  <img src="https://raw.githubusercontent.com/Monisha-krish/system-hacking-metasploit/main/screenshots/exploit_setup.jpeg" width="500"/>
</p>

<p align="center">
  <b>Step 4: Meterpreter Session Established</b><br>
  <img src="https://raw.githubusercontent.com/Monisha-krish/system-hacking-metasploit/main/screenshots/meterpreter.jpeg" width="500"/>
</p>

<p align="center">
  <b>Step 5: Host System Screenshot via Meterpreter</b><br>
  <img src="https://raw.githubusercontent.com/Monisha-krish/system-hacking-metasploit/main/screenshots/screenshot_meterpreter.jpeg" width="500"/>
</p>

<p align="center">
  <b>Step 6: Captured Screenshot of Target Using Meterpreter</b><br>
  <img src="https://raw.githubusercontent.com/Monisha-krish/system-hacking-metasploit/main/screenshots/host_screenshot.jpeg" width="500"/>
</p>



---

### ℹ️ Notes
- All actions are logged and reproducible within the lab.
- This repository is intended to demonstrate **security awareness and defense**, not to enable misuse.
