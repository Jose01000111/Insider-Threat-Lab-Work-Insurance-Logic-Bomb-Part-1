# 💣Insider Threat Lab: Work Insurance Logic Bomb💥

In this lab, I simulated an insider threat scenario where a privileged sysadmin, steveg, sets up a harmless “logic bomb” disguised as a Work Insurance automation script. I then prepared the system for a forensic investigation by my IR consultant account, john.

---

> ## 🧨 Story Interlude — The Warning Signs  
> Steve, a long‑time system administrator, had recently been placed on a PIP. His behavior shifted — quiet, distant, protective of his workstation.  
>
> Logs later revealed unauthorized edits to hidden shell scripts buried deep within the system.  
>

# Phase 0 — Initial Setup 🛠️
I set up the environment and made sure all the key players were ready. I created an IR consultant user and confirmed the privileged status of steveg.  




>- 👨‍💻 **steveg** — privileged sysadmin on a PIP  
>- 🕵️ **john** — IR consultant with sudo privileges  
>- 🆔 **UID/GID check** — confirming steveg’s identity and privileges

---

# Phase I — Attack Setup: Work Insurance Logic Bomb 💣
I created a safe simulation script in steveg’s home directory, pretending it was HR Work Insurance automation. Then I moved the script to a persistent directory and configured a systemd path trigger so it would execute when steveg’s account was deleted.  




>- 📂 **Script creation** — /home/steveg/work_insurance.sh  
>- 🗄️ **Persistence** — copied script to /usr/local/lib/work-insurance  
>- ⚙️ **Systemd trigger** — work-insurance.path & work-insurance.service  
>- 🔒 **RHEL9 fix** — used PathModified instead of PathChanged

---

> ## 🔓 Story Interlude — The Trigger Event  
> When HR deactivated Steve’s account, a hidden script executed.  
>
> It created suspicious files, tampered with logs, and triggered automated tasks tied to his user.  
>
> A simulated **logic bomb** had gone off.

# Phase II — Triggering the Logic Bomb 💥
I stopped all active processes for steveg to allow account deletion, then deleted the account. This successfully triggered the Work Insurance logic bomb and generated forensic artifacts.  




>- ❌ **Terminate user processes** — pkill -u steveg  
>- 🧹 **User deletion** — sudo userdel -r steveg  
>- 📝 **Artifact creation** — /tmp/work_insurance_records with event logs  
>- 📜 **System changes** — /etc/motd modified to log event

---

# Phase III — Verification 👀
I verified that the simulated malicious activity had occurred. I checked the artifact directory and inspected the system modifications to confirm the logic bomb executed correctly.  




>- 📂 **Artifact inspection** — ls /tmp/work_insurance_records  
>- 🖊️ **Event logs** — cat /tmp/work_insurance_records/event.log  
>- 🖥️ **System message** — cat /etc/motd
