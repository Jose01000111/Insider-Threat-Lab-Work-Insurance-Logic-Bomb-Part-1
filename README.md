# 💣Insider Threat Lab: Work Insurance Logic Bomb💥 Part 1

![CnBKPi0](https://github.com/user-attachments/assets/97414533-055f-4b58-b421-1fd7e3d12add)

In this lab, I simulated an insider threat scenario where a privileged sysadmin, steveg, sets up a harmless “logic bomb” disguised as a Work Insurance automation script. I then prepared the system for a forensic investigation by my IR consultant account, john.

---

> ## 🧨 Story Interlude — The Warning Signs  
> Steve, a long‑time system administrator, had recently been placed on a PIP. His behavior shifted — quiet, distant, protective of his workstation.  
>
> Logs later revealed unauthorized edits to hidden shell scripts buried deep within the system.  
>

# Phase 0 — Initial Setup 🛠️
I set up the environment and made sure all the key players were ready. I created an IR consultant user and confirmed the privileged status of steveg.  

<img width="625" height="292" alt="cgL0PGs" src="https://github.com/user-attachments/assets/39c7ddbd-8c8a-47f4-8087-46159b80b408" />

---

<img width="801" height="401" alt="msusejD" src="https://github.com/user-attachments/assets/b039ecd3-0f3a-47d6-a588-4387c8d8ad61" />

---

<img width="794" height="51" alt="QeAI3af" src="https://github.com/user-attachments/assets/b672bdf9-4580-48a9-98ad-d26ae16a82f2" />

>- 👨‍💻 **steveg** — privileged sysadmin on a PIP  
>- 🕵️ **john** — IR consultant with sudo privileges  
>- 🆔 **UID/GID check** — confirming steveg’s identity and privileges

---

# Phase I — Attack Setup: Work Insurance Logic Bomb 💣
I created a safe simulation script in steveg’s home directory, pretending it was HR Work Insurance automation. Then I moved the script to a persistent directory and configured a systemd path trigger so it would execute when steveg’s account was deleted.  

<img width="964" height="271" alt="CoiPyXl" src="https://github.com/user-attachments/assets/8fa8bdaa-57cf-4f0a-bd86-e28d410ec823" />

---

<img width="756" height="130" alt="ogX4ZDY" src="https://github.com/user-attachments/assets/b5d351fc-f8eb-451e-af48-8e1c3821712e" />

---

<img width="989" height="95" alt="a3fs3C5" src="https://github.com/user-attachments/assets/b5c9b59b-58a4-48ee-a280-fcf9f9a55e60" />

---

<img width="823" height="261" alt="O0G4Eud" src="https://github.com/user-attachments/assets/fae914ed-eb43-453f-912e-4b4b728debd2" />

---

<img width="819" height="209" alt="PMqXzlR" src="https://github.com/user-attachments/assets/4a08743c-2de5-43fe-aa5d-a73028efcedf" />

---

<img width="715" height="41" alt="jljVWp9" src="https://github.com/user-attachments/assets/8931a8a9-6830-4733-90b6-7fa25ef131d5" />


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

<img width="585" height="184" alt="yzhraqb" src="https://github.com/user-attachments/assets/a47ba40b-cafc-4b8b-bbdd-be1993280df3" />


>- ❌ **Terminate user processes** — pkill -u steveg  
>- 🧹 **User deletion** — sudo userdel -r steveg  
>- 📝 **Artifact creation** — /tmp/work_insurance_records with event logs  
>- 📜 **System changes** — /etc/motd modified to log event

---

# Phase III — Verification 👀
I verified that the simulated malicious activity had occurred. I checked the artifact directory and inspected the system modifications to confirm the logic bomb executed correctly.  

<img width="921" height="229" alt="pbRosw9" src="https://github.com/user-attachments/assets/8ed8d1ca-58eb-456c-adba-4114ed596e7c" />


>- 📂 **Artifact inspection** — ls /tmp/work_insurance_records  
>- 🖊️ **Event logs** — cat /tmp/work_insurance_records/event.log  
>- 🖥️ **System message** — cat /etc/motd

---

# 🔚 Conclusion & Next Steps

This concludes Part 1 of the Insider Threat Lab, where I set up a simulated **Work Insurance logic bomb**, triggered it safely, and verified the artifacts.  

In **Part 2**, I will switch to the IR consultant account (john) to:

- Perform a detailed **incident response investigation**  
- Run a **Qualys vulnerability scan** to identify system weaknesses  
- Collect and analyze forensic evidence  

Stay tuned for Part 2, where the focus shifts from **attack simulation** to **detection, analysis, and remediation**. 🚀

