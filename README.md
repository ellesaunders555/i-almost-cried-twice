# i-almost-cried-twice
This repository is about my late night, bleary-eyed adventures deploying a dedicated server for an open-source ticketing system
## i-almost-cried-twice (E Saunders Lab HelpDesk)## 📌 What the Project Does
This project features a dedicated IT Help Desk ticketing server deployed within an Ubuntu Linux Virtual Machine (VM). It simulates a real-world enterprise support environment by installing and exposing Request Tracker (RT) / osTicket software over a local subnet.
The project stands as a practical demonstration of troubleshooting under pressure. When the web infrastructure encountered critical service failures during deployment, the system was manually diagnosed and repaired rather than wiped and rebuilt.
## Core Tech Stack

* OS: Ubuntu Linux
* Web Server: Apache2
* Service Manager: Systemd
* Text Editor: GNU Nano

------------------------------
## 💡 Why the Project Is Useful
This repository serves as a blueprint for foundational Linux systems administration, network configuration, and live service triage. It proves that deployment failures can be systematically resolved through deep log analysis and configuration audits rather than starting over.
## Key Technical Competencies Demonstrated

* Systems Administration: Navigating Linux file structures and editing configurations inside headless environments.
* Log Analysis: Utilizing standard system monitors to track structural issues back to explicit root causes.
* Network Testing: Verifying local network endpoints by routing clean host requests across a local private subnet (192.168.1.211).
* Technical Resilience: Diagnosing multi-layered dependencies and stepping systematically through structured recovery actions.

------------------------------
## 🚀 How Users Can Get Started
To replicate this environment or review the repair process, follow the breakdown of the deployment phases below.
## Phase 1: Core Web Server Deployment & Advanced Troubleshooting

   1. Diagnostic Logging & Triage
   * Investigate service initialization crashes using systemd logging mechanisms:
      
      systemctl status apache2
      journalctl -u apache2
      
      * Trace system faults down to specific syntax failures within the core server files.
   2. Configuration File Surgery
   * Use the nano terminal editor to isolate and audit deep configuration layers.
      * Fix the system-blocking mismatch found on line 225 of /etc/apache2/apache2.conf.
      * Audit configuration syntax line-by-line to ensure standard variable compliance.
   3. Link Clean Up & Directory Auditing
   * Isolate any corrupted symbolic links inside the active virtual host path: /etc/apache2/sites-enabled/
      * Clear out failing components using terminal file management tools:
      
      rm /etc/apache2/sites-enabled/corrupted-link
      
      * Re-establish standard symbolic links pointing back to production definitions:
      
      ln -s /etc/apache2/sites-available/rt.conf /etc/apache2/sites-enabled/rt.conf
      
      4. Verification & Validation
   * Execute structural validation using the Apache control management tool:
      
      apache2ctl configtest
      
      * Confirm the Syntax OK response.
      * Initialize the web engine and verify it reads Active: active (running).
   
------------------------------
## 🤝 Where Users Can Get Help
If you run into issues while replicating this setup:

* Check the Apache error logs located at /var/log/apache2/error.log.
* Open an Issue in this repository describing your configuration error.

------------------------------
## 👤 Who Maintains and Contributes

* E. Saunders - Lab Creator & Systems Administrator

-----------------------------
