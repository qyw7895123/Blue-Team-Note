* NIST four major phases in the incident response cycle
  * Preparation
  * Detection adn analysis
  * Containment, eradication, recovery
  * Post incident response
* Forensics on VM machines. To get all forensic data
  * Suspend the machine and copy the contents of the directory it resides in.
  * Suspending a virtual machine will result in the RAM and disk contents being stored
to the directory where it resides
* Where Chrome store forensic info?
  * SQLite
  * Chrome stores a broad range of useful forensic information in its SQLite database,
including cookies, favicons, history, logins, top sites, web form data, and other details.
* Someone attempting to image a device but got write issues and cannot write the image.
  * FAT32 biggest size 4GB. Should format the destination drive as NTFS.
* Windows built-in tool to create hash for a file.
  * certutil -hashfile [file location] md5 
  * Also support SHA1 and SHA256
* Incident response communication process
  *  Limiting communication to trusted parties
  *  Using a secure method of communication
  *  Preventing accidental release of incident-related information
* Best suited to detection beaconing using network security device?
  * IP reputation to monitor for connections
to known bad hosts
* Plug a system back in to the network, what phase of the incident response process is performing?
  * Containment, eradication, and recovery
* Monitoring unexpectedly connects to an off-site IP and transfer large data.
  * Flow logs with heuristic analysis
  * Flow logs would show outbound traffic flows based on remote IP and volume of traffic, and behavioral analysis.
* NIST recoverability effort categories
  * Regular - Time to recovery is predictable with existing resources.
  * Supplemented - Time to recovery is predictable with additional resources.
  * Extended - Time to recovery is unpredictable; additional resources and outside help are needed.
  * Not recoverable - Not possible for recovery.(sensitive data exfiltrated and posted publicly); launch investigation.
* Someone download file using incognito mode then deleted the file how to determine what files he downloads
  * Drive analysis.
  * network flows do not provide file information.
* Email "your system are weak; we will own your network by the end of the week."
  * A precursor
* What phase does lessons-learned belongs to?
  * Post-incident recovery
* Playbook for zero-day threats.
  * Segmentation, using threat intelligence, whitelisting, implementing only necessary firewall rules, using behavior and baseline-based intrusion prevention rules and SIEM alerts and a plan.
  * Patching is not one for zero-day threats.
* A user accessing a file that they are not authorized to view?
  * adverse events: events with negative consequences.
* Media sanitization NIST identifies
  * Clear(logical sanitize)
  * Purge(physical or logical data recovery infeasible sanitize) overwriting, block erase, cryptographic erase and degaussing.
  * Destroy(physically destroying)
* first step of spam email investigation
  * Check the full headers of one of the spam messages
* First step when arriving an investigation site.
  * Collect live forensic information, take photos of each system, and power them down.
* When forensic evidence or information is produced for a civil case, it is called e-discovery.
* PII(personal identifiable information), PHI(personal health information), PCI-DSS(payment card industry data security standards)
* Procedures and playbooks
  * Procedures: provide the detailed, tactical information that CSIRT members need when responding to an incident.
  * Playbooks: describe the specific procedures that they will follow in the event of a specific type of cybersecurity incident.
* Chain of custody 
  * Documenting the way that we secure, transport and verify that items acquired for investigation were held in an appropriate manner.
* Primary role of management in the incident response process?
  * Providing authority and resources
* **Process monitor** provides detailed tracking of filesystem and registry changes as well as other details that can be useful when determining what changes and application makes to a system.
* **Maintain back up** is **not** a recommended best practice based on NIST's guidelines.
* Methods to Identify evil twin 
  * check for BSSID(wireless MAC address)
  * check the attributes
  * check for tagged parameters like the organizational unique identifier
* What type of file is commonly used to store configuration settings for macOS?
  * Plists
* One or two year retention period is commonly used without other requirements in place
* Police seized equipments for investigation
  * Company should not plan on a time frame for return.
* Most common format for forensic tool
  * RAW
* Check USB drive connect history
  * security audit logs, setupapi log and registry.
* For network share or mounted drive, deleted files, unallocated space and other information that requires direct drive access will not be captured.
* NIST AP 800-61 identifies six outside parties IR team will communicate with
  * (customers, constituents, media), other IR teams, Internet service providers, incident reporters, law enforcement agencies, and software and support vendors.
* Volatility order for forensic data
  * CPU cache, network traffic, disk drives, optical media
* NIST notes that identifying an attacker can be "time-consuming and futile"
* Super Timeline is the ability to create a timeline of events that covers logs, file changes, and many other artifacts.
* ISACs Information shareing and analysis centers
  * Sharing and community support organizations.
* Most trustful information from a spam email header will be the originating host which in most cases is simply a compromised host spammers can leverage to send spam emails.
* If company want to ensure a chain of custody documentation will stand up to examination in court.
  * There should be a second examiner acting as a witness and countersigning all actions
* The system should isolated before restoring from backups.
* MBR-, UEFI-, and BIOS-resident malware packages can all survive a drive wipe
* Minimum retention period for incident data for U.S. federal government agencies is 3 years.
* NIST recommendations of a evidence log should includes host name, IP, MAC address
* APTs send traffic in an encrypted form, network forensics for traffic analysis will only provide information about potentially infected hosts. **Endpoint forensics** is the technique to detect the APT infections.
* Copying new files over old files can leave remnant data, to prove the old file were on the system by examining slack space.
* In a incident, proprietary information was changed, how should we classify this incident?
  * AS an integrity loss
* Windows does not include a built-in secure erase tool in the GUI or at command line.
* Data contain **merger and acquisition information as well as accounting data** is considered as **Corporate confidential data.**
* **Profiling networks and systems** will provide a baseline behavior set for **anomaly analysis**. A SIEM or similar system can monitor for differences or anomalies that are recorded as events. Behavioral analysis does not need a baseline.
* What will a Windows system restore return to a previous state?
  * Windows system files
* The **File system audit  subcategory** includes the ability to monitor for both access to objects ID 4663 and permission changes ID 4670.
* 