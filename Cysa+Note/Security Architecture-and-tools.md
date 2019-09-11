* Cross training best practice to improve the organization.
  * It ensures that skills exist in more than one place, helping prevent a single employee's departure from leaving the organization whiteout the ability accomplish tasks that only that individual knew how to perform.
  * It can provide a valuable opportunity to review processes, potentially identifying issues or habits that a single responsible employee may develop.
* **Single sign-on** allow users to authenticate once and then to use multiple systems or services without having to use different usernames or passwords.
  * LDAP
  * CAS the Central authentication service
* **Shared authentication schemes** are similar to single sign-on, however it require users to enter credentials when authenticating to each site.
  * Open ID
  * OAuth relies on access tokens
  * Facebook connect
  * Open ID Connect is a authentication layer built using the OAth protocol
* **Policy contains** broad statements about cybersecurity objectives in the company. It's a framework to meet the business goals and to define roles, responsibilities, and terms used in other security documents. Approved by C suite.
  * Information security
  * Acceptable use
  * Data ownership
  * Data retention
  * Account management
  * Password
* **Standards** used to implement a policy. Includes mandatory actions, steps, or rules to achieve cybersecurity. Approved by management.
* **Procedures** detailed step-by-step instructions created for people to perform an action. For example, follow procedure to create a new user account.
* **Guidelines** are not required actions, just recommended. Flexible in nature to allow for exceptions and allowances during a unique situation. For example, show guidelines to end users how to store data files in a loud service.
* **Exceptions** specific approval to deviate from a policy, standard, procedure. Approval authority is specified in policy.
* **NIST cybersecurity framework**
  * Framework Core is a set of five security functions that apply to all industries.
  * Framework Implementation Tiers measure how the organization is positioned to meet cybersecurity objectives.
  * Framework Profiles describe how the organization might approach the functions covered by Framework Core.
* **ISO 27001** is the most commonly used information security standard. To become ISO 27001 certified, an external accessor validates organizational compliance.
* **ITIL** Information technology infrastructure library. Not totally for cybersecurity.
* **COBIT** Control objective for information & related technologies. Best practices for IT governance developed by ISACA.
  * Plan and Organize
  * Acquire and Implement
  * Deliver and Support
  * Monitor and Evaluate
* **TOGAF** the open group architecture framework.
* **Policy-based controls** is the desired end state, not the method or activities to accomplish them.
  * Physical controls
    * Fences, gates, locks, lighting, alarm systems, fire suppressions systems, etc.
  * **Logical controls** Technical controls to enforce CIA.
    * ACLs in firewalls and routers, encryption schemes. All the technics related to cybersecurity.
  * **Administrative controls** procedural controls to implement good cybersecurity practices
    * Separation of duties, background checks, reviewing of log files
* Audits and assessments
  * Quality control
    * Evaluation of your cybersecurity program is essential to it being effectively run
    * Evaluation occurs as audits or assessments
  * Audits
    * Formal review of organizational cybersecurity program (internally)
    * Or sometimes externally like PCI DSS
    * Formal testing of controls resulting in formal declaration by the auditor of compliance
  * Assessments
    * Less formal review of security controls
    * Usually request by the organization itself for process improvement purposes
  * **Laws and regulations**
    * HIPPA Health portability and accountability act. Health related.
    * GLBA Gramm-Leach-Bliley act. Financial institutions related. Must designate a "responsible" individual.
    * SOX Sarbanes-Oxley act. Requires publicly traded companies to maintain good security.
    * FERPA Family educational rights and privacy act. Requires educational institutions to implement security and privacy controls for educational records.
    * PCI DSS Payment card industry data security standard. Payment with card related.
    * Data breach notifications. Requires companies to notify victims of data breaches in a timely manner.
  * **Defense in Depth**. 
    * Foundation of good security architecture. Does not rely on a single defensive measure or control for protection.
    * From inside out the layers are Data, Application, Endpoint security, Network and Perimeter.
    * **Four design models**
      * **Uniform protection**
        * Gives same level of protection to all data, systems, or networks
        * Can be expensive for larger networks
      * **Protected enclaves**
        * Enclaves that house more sensitive data are given additional protections
        * Additional firewall for datacenter network.
      * **Risk or Threat analysis-based**
        * Addresses specific risks or threats in the design of the networks and systems
        * For phishing, you could employ additional controls to securely scan and filter your incoming emails
      * **Information or classification-based**
        * Map data protection to different classes of information
        * Higher classification levels get additional attention and security controls
      * **Combining design models**
        * Often these four models are combined.
  * **Types of controls** 
    * **Technical controls**
      * Designed to provide security through technical measures
        * Firewalls
        * IDS/IPS
        * Authentication systems
        * Network segmentation
    * **Administrative controls or procedural controls** 
      * Designed to provide security through processes and procedures
      * Legal controls are type of these controls that are put in place by the law
        * Incident Response plans
        * User awareness training
        * Account creation policy
        * Acceptable use polocy
    * **Physical controls**
      * Designed to provide security by preventing physical access or harm to the organization's systems or facilities
      * Fences
      * Mantraps
      * Security Guards
    * **Preventative controls**
      * Designed to stop an incident before it has occurred
      * Proactive measures
        * Fire walls
        * Antivirus
        * Training
    * **Detective controls**
      * Designed to detect when an incident occurs, capture details about it, and send an alarm/notification so someone can act
      * IDS
      * Security cameras
      * Logs
    * **Corrective controls**
      * Designed to fix an issue after an incident hs occurred
      * Part of incident response process
      * Reactive measures
      * Security patching
      * System rebuilding
      * Restore from backups
    * **Compensating controls**
      * Designed to satisfy a security requirement not being met by other controls
      * Minimizes threat down to an acceptable level of risk
      * Blocking certain ports instead of upgrading all of the OS
      * Segmenting vulnerable software to a separate part of the network
* **Layered network design**
  * **Network segmentation**
    * Compartmentalization of the network
    * Benefits
      * Reduces the network's attack surface
      * Limits scope of regulatory compliance
      * Increases availability of critical services
      * Increases network efficiency
    * Segmentation is implemented through firewalls, routers, switches, and VLANs
  * **Single fire wall or router** is the simplest network design utilized used to create a DMZ for a lower trusted segment of the netWork
```
internet <==> router <==> switch <==> firewall <==> intranet                        
                     //   ||     \\
                   Web   Mail    DNS 
```
* **Multiple interface firewalls** using different ACL and rule sets applied to each interface, creating multiple network segments
  * Often called service-leg DMZ
```
internet <==> router <==> firewall <==> intranet
                            ||
                           switch
                        //   ||    \\
                      Web   Mail    DNS

```
* **Multi-firewall** dual-firewalls or more puts a firewall at each control point
  * allows for more stringent controls as you move deeper into the network
```
internet <==> router <==> firewall <==> switch <==> firewall <==> intranet
                                      //   ||   \\
                                    Web   Mail  DNS  
```
* **Outsourcing segments** remote services
  * SaaS and PaaS rely on providers for security and network designs
  * Directly connected remote network
* **Layered host security**
  * **Cryptography: Encryption and hashing**
    * Encrypting files or the full disk
    * Proper storage of the encryption keys
    * Hashing files ensure file integrity
  * **Logging, monitoring and validation**
    * Logs must be securely stored and centrally monitored
    * Specialized log server or SIEM
    * Tripwire, AlienVault, Splunk
    * Configuration management (Microsoft SCCM) allow validation of system settings and software across the connected hosts
* **Data analytics**
  * Integrating logs provides the most value and information
  * Automated systems can help prioritize items for review based on heuristics and previous signatures created
  * **Data aggregation and correlation**
    * Combine data from multiple sources to identify events impacting different systems
      * System logs, authentication logs, application logs, event logs, and other into central analysis node
      * Effective as a detective control
      * Splunk is an example
    * **Trend analysis** looking forward 
      * Analyzes system, events, and devices to detect trends and patterns
      * Identifies issues that are outside of expected grouth or usage patterns
    * **Historical analysis** looking rear view
      * Analyzes system, events, and devices over time to detect trends and patterns
      * Helpful during incident responses as it looks back over a longer period of time
* **Personnel security**
  * **Separation of duties**
    * Requires more than one person to perform a task by breaking the task into additional parts
    * Provides a system of checks and balances to prevent fraud and abuse
  * **Dual control**
    * Process requiring two individuals to perform the action together
      * Unlocking a sage or server room
  * **Succession planning**
    * Focuses on ensuring important duties will always have someone who can perform them
    * Prevents issues from task not being performed during personnel turnover
      * A primary and backup administrator
  * **Cross training of employee**
    * Focuses on teaching emplyees skills to cover tasks other coworkers perform
    * On-the-Job training is used to ensure you have additional resources for a big project in the future or if someone quits
  * **Background checks**
    * Conducted prior to hiring an employee
      * Bank runs credit check on new hires
  * **Mandatory vacation time**
    * Staff members must take vacation
    * Allows us to identify any issues being hidden since the person will not maintain continuous access to the systems
  * **Termination**
    * Policies and procedures focus on that to do when an employee is terminated
    * Retrieving company property, disabling accounts, changing security codes
* **Outsourcing concerns**
  * **Proper vetting and employment practices**
    * Make sure do a thoroughly check about the outsourcing company
  * **Access control**
    * How is their access control handled to the system?
    * How is your data physically or logically segmented from other organizations?
  * **Data ownership and control** 
    * Who owns the data?
    * Does the service provider have access to just the data? Or do they also have the encryption keys?
  * **Incident response and notification processes**
    * How will you be notified if there is a breach?
    * Or, will you even be notified if there is a breach?
* **Analyzing secure architectures**
  * **Review architectures**
    * **Operational view**
      * Focus on how a function is performed or is supposed to accomplish
    * **Technical View**
      * Focuses on technologies, configurations, and settings used in an architecture (system or service)
    * **Logical View**
      * Focuses on the interconnections of systems with less technical details than the technical view
  * **Common Issues**
    * Single points of failure
    * Data validation and trust
      * SQL injections
      * Systems should always be designed with validation and integrity checking
    * Users
      * The largest cause of a security failure
      * To prevent 
        * Automated monitoring
        * Limit interfaces to only allow activities
        * User awareness training!!!
    * Authentication & Authorization
      * Credentials, passwords, and permissions 
      * To prevent
        * Multifactor authentication
        * Centralized account management
        * Centralized privilege management
        * Monitor privileged account access
        * User training!!!
  * **Architecture reviews**
  * **Maintaining secure architectures**
    * Threats change over time and system become outdated
    * Scheduled reviews
    * Continual improvement
    * Retirement of processes
* **AAA: Authentication, Authorization, and Accounting**
  * Used to control access to computers, networks, and services
  * AAA system use usernames, passwords, or other attributes of an identity to authorize access.
  * Authentication
    * Individual proves who they are
  * Authorization
    * Individual is provided access to a given resource
  * Accounting
    * Logs and monitors a user when an authentication or authorization attempt is made or completed
* **IAM Centralized identity and access management**
  * Systems built to create, store, and manage identity information, including group memberships, roles, permissions, and more
* Identity systems
  * Directory services
    * Used in networks to provide information about systems and users
    * LDAP lightweight directory access protocol is commonly used
      * Microsoft's active directory, Oracle's Internet directory, IBM's security directory, OpenLDAP, 389 Directory server, ApacheDS, and OpenDJ
      * Can be used to make organizational information available to email and other programs
  * LDAP directory structure 
    * dc = domain name
    * ou = organizational unit
    * cn = common name
  * Securing LDAP
    * Enable and require TLS
    * Set password storage to use salted hash
    * Disable unauthenticated and anonymous LDAP modes
    * Replicate LDAP to a redundant server to prevent outages or DOS
    * Strong ACLs on LDAP to limit access to objects using least privilege model
  * LDAP injection
    * Type of attack because of improperly filtered input via web applications shend arbitrary LDAP queries to the server
    * To prevent
      * Automated frameworks
      * Input validation
    * Authentication protocols
      * Protocols used to supply verification of user's identity to a relying system
      * TACACS+
        * Cisco extension to the terminal access control access control system
        * Using TCP to provide AAA services
        * Lacks integrity checking of data it sends
          * Subject to replay attacks
        * Encryption flaws
          * Encryption key can be discovered by attacker
        * Don't use TACACS+ unless on an isolated network
      * RADIUS
        * Remote Authentication Dial-in service
        * Most common AAA for networks, wireless networks, and other services
        * Operates over TCP or UDP in a client0server model
        * Password obscured using shared secret and MD5 hash (not strong)
        * RADIUS traffic should be encrypted using IPSec between endpoints
      * Kerberos
        * Operates on untrusted networks using encryption of its data
        * Principles (users) comprised of three elements:
          * Primary (usually a username)
          * Instance (unique ID uncase usernames are similar)
          * Realm (group of primaries)
        * Replaced NTLM for AAA in Windows domains
  * SSO **single-sign-on**
    * Allows users to authenticate once and then be able to use multiple systems
      * LDAP
      * CAS Central authentication service
    * Benefits
      * Reduce password reuse
      * Fewer password resets and support calls
  * **Shared authentication**
    * OpenID
      * Open-source standard for decentralized authentication
    * OAuth
      * Open authentication standard used to share elements of identify with third-party
    * OpenID connect
      * Authentication layer built using OAuth protocol
    * Facebook connect
* **Threats to identity systems**
  * **Personnel-based threats**
    * Phishing or social engineering techniques
    * Insider threat
  * **Endpoint threats**
    * Local exploits
    * Keyloggers
    * Local administrative credentials
    * Password stores and tokens
  * **Other identity threats**
    * Server-based treats
    * Application/Service threats
    * Roles, rights, and permission threats
* **Attacking AAA Protocols and Systems**
  * **Attacking LDAP**
    * Target unencrypted LDAP traffic to capture traffic for replay attacks
      * use secure binding to prevent 
    * Target improper access controls to harvest directory information or to modify directory
      * setup good access control
    * Perform LDAP injection against vulnerable web applications that interface with directory
      * Validate web-based input and use least privilege
    * Conduct DOS against LDAP to cause services to fail which rely on it
      * redundancy
  * **Active directory**
    * Core identity store and AAA service for Windows
      * many exploits built for clients, servers, and AD
      * Many Windows domains contain older systems still
      * Very common target for attackers
* **Targeting account lifecycle**
  * Create account and password ==> Provision to services and set rights/roles ==> Modify/Maintain account ==> Disable account ==> Retire/delete account
  * **Utilize least privilege**
  * **Prevent privilege creep** 
    * Accounts tend to gain privileges overtime based on rotating job functions a suer undertakes
    * Remove old rights when they are no longer needed
  * **Identity lifecycle Management**
    * Centrify, Okata, and Ping Identity 
* **Identity exploits**
  * Impersonation attacks
    * Usually involves credential theft or open redirects (OAuth)
  * Session hijacking
    * Attacker takes over an existing session by getting or guessing the session key
    * Encrypting sessions to prevent
  * Man-in-the-middle MITM
    * Attacker accesses the information flow between systems or services
    * Prevented through using session or link encryption tunnels
  * Privilege escalation
    * Attacker elevates permissions form one level to a higher level
  * Rootkits
    * Attacker uses malware to provide continued access to a server/client while hiding 
* **Credential theft**  
  * Phishing
  * Compromise other websites (password reuse)
    * Reusing stolen credential from a less secure server 
  * Brute-force attack
* **Securing authentication and authorization**
  * Securing authentication
    * Uses strong passwords 
    * Password management 
      * SSO
      * Token-based for multifactor
      * Password safes (LastPass)
    * Encrypt communications between clients and authenticators using TLS
  * **Securing authorization (Users)**
    * Access control users are matched with rights/privileges
    * Polices to control what rights are given
    * Implement management systems for approving rights
    * Monitor/report on accounts
  * **Securing authorization (Admin)**
    * Privileged User Management
    * Use additional monitoring and logging
    * Separation of duties
    * Training
    * Prevent admin accounts from being used as daily accounts
  * **Multifactor authentication**
    * More factor
    * Knowledge factors things you know
    * Possession factors things you have
    * Biometric factors things you are
    * Location factors where you are
  * **Context-based authentication**
    * Authentication decision based on information about the user or system
    * Time of a day
    * IP address and reputation
    * Frequency of access
    * Location
    * Type of device
* **Identity as a service (IDaaS)**
  * Provide authentication services, usually through cloud-based resources
* **Detecting identity attacks**
  * Identity and Access Management systems should be fed into the SIEM
* **Federated identity systems**
  * Moves the trust boundary outside your organization to Google, Facebook, ot other identity providers
  * Identity Provider(IDP)
    * Provides identities & release data to relying parties
  * Relying Party (RP) or Service Provider (SP)
    * Members of the federation that provides services to the user when identified by identity provider
  * Consumer or User
    * Asked to make decision on who to share their identity with by IDP in order to get services from RP/SP
  * **SAML Security assertion markup language**
    * XML-based language to send authentication and authorization data between IDP and RP
    * Used to enable SSO for web apps & services
  * **OAuth and OAuth 2.0**
    * Developed by the Internet Engineering Task Force (IETF) to provide an authorization framework to allow service provider applications to access HTTP0based services
  * **Flickr federated example (OAuth Authentication process)**
    * 