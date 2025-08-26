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

## Screenshots
> Add your images here once uploaded to `screenshots/`.

- Step 1 – Recon (Nmap): `![Nmap Scan](screenshots/step1_nmap.jpeg)`
  https://raw.githubusercontent.com/Monisha-krish/system-hacking-metasploit/main/screenshots/NMap_Scan.jpeg

- Step 2 – Metasploit search: `![MSF Search](screenshots/step2_msf_search.jpeg)`
- Step 3 – Module/Options: `![Exploit Setup](screenshots/step3_exploit_setup.jpeg)`
- Step 4 – Session: `![Meterpreter](screenshots/step4_meterpreter.jpeg)`
- Step 5 – Post-exploitation demo: `![Post Exploit](screenshots/step5_post.jpeg)`

---

### ℹ️ Notes
- All actions are logged and reproducible within the lab.
- This repository is intended to demonstrate **security awareness and defense**, not to enable misuse.
