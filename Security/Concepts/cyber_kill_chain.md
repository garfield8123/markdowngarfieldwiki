# Cyber Kill Chain

## Reconnaissance

Reconnaissance: discovering and collecting information on the system and the victim.

OSINT (Open-Source Intelligence): also falls under reconnaissance. OSINT is the first step an attacker needs to complete to carry out the further phases of an attack. The attacker needs to study the victim by collecting every available piece of information on the company and its employees, such as the company's size, email addresses, phone numbers from publicly available resources to determine the best target for the attack.

Email harvesting: is the process of obtaining email addresses from public, paid, or free services. An attacker can use email-address harvesting for a phishing attack (a type of social-engineering attack used to steal sensitive data, including login credentials and credit card numbers). The attacker will have a big arsenal of tools available for reconnaissance purposes.

* [theHarvester](https://github.com/laramies/theHarvester) - other than gathering emails, this tool is also capable of gathering names, subdomains, IPs, and URLs using multiple public data sources
* [Hunter.io](https://hunter.io/) - this is an email hunting tool that will let you obtain contact information associated with the domain
* [OSINT Framework](https://osintframework.com/) - OSINT Framework provides the collection of OSINT tools based on various categories

## Weaponization

* Malware: is a program or software that is designed to damage, disrupt, or gain unauthorized access to a computer.
* exploit is: a program or a code that takes advantage of the vulnerability or flaw in the application or system.
* payload: is a malicious code that the attacker runs on the system.
* Create an infected Microsoft Office document containing a malicious macro or VBA (Visual Basic for Applications) scripts. If you want to learn about macro and VBA, please refer to the article ["Intro to Macros and VBA For Script Kiddies" by TrustedSec](https://www.trustedsec.com/blog/intro-to-macros-and-vba-for-script-kiddies/).
* An attacker can create a malicious payload or a very sophisticated worm, implant it on the USB drives, and then distribute them in public. An example of the virus.
* An attacker would choose Command and Control (C2) techniques for executing the commands on the victim's machine or deliver more payloads. You can read more about the C2 techniques on [MITRE ATT&CK](https://attack.mitre.org/tactics/TA0011/).
* An attacker would select a backdoor implant (the way to access the computer system, which includes bypassing the security mechanisms).

## Delivery

* Phishing email: after conducting the reconnaissance and determining the targets for the attack, the malicious actor would craft a malicious email that would target either a specific person (spearphishing attack) or multiple people in the company. The email would contain a payload or malware. For example, "Megatron" would learn that Nancy from the Sales department at company A would constantly like the posts on LinkedIn from Scott, a Service Delivery Manager at company B. He would give it a second guess that they both communicate with each other over work emails. "Megatron" would craft an email using Scott's First Name and Last Name, making the domain look similar to the company Scott is working at. An attacker would then send a fake "Invoice" email to Nancy, which contains the payload.
* Distributing infected USB drives in public places like coffee shops, parking lots, or on the street. An attacker might decide to conduct a sophisticated USB Drop Attack by printing the company's logo on the USB drives and mailing them to the company while pretending to be a customer sending the USB devices as a gift. You can read about one of these similar attacks at CSO Online "Cybercriminal group mails malicious USB dongles to targeted companies."
* Watering hole attack: A watering hole attack is a targeted attack designed to aim at a specific group of people by compromising the website they are usually visiting and then redirecting them to the malicious website of an attacker's choice. The attacker would look for a known vulnerability for the website and try to exploit it. The attacker would encourage the victims to visit the website by sending "harmless" emails pointing out the malicious URL to make the attack work more efficiently. After visiting the website, the victim would unintentionally download malware or a malicious application to their computer. This type of attack is called a drive-by download. An example can be a malicious pop-up asking to download a fake Browser extension.

## Exploitation

* lateral movement: refers to the techniques that a malicious actor uses after gaining initial access to the victim's machine to move deeper into a network to obtain sensitive data.
* zero day exploit: the zero-day exploit or a zero-day vulnerability is an unknown exploit in the wild that exposes a vulnerability in software or hardware and can create complicated problems well before anyone realizes something is wrong. A zero-day exploit leaves NO opportunity for detection at the beginning."
* The victim triggers the exploit by opening the email attachment or clicking on a malicious link.
* Using a zero-day exploit.
* Exploit software, hardware, or even human vulnerabilities.
* An attacker triggers the exploit for server-based vulnerabilities.

## Installation

* [persistent backdoor](https://www.offensive-security.com/metasploit-unleashed/persistent-backdoors/): will let the attacker access the system he compromised in the past
* Installing a web shell on the webserver. A web shell is a malicious script written in web development programming languages such as ASP, PHP, or JSP used by an attacker to maintain access to the compromised system. Because of the web shell simplicity and file formatting (.php, .asp, .aspx, .jsp, etc.) can be difficult to detect and might be classified as benign. You may check out this great article released by Microsoft on various web shell attacks.
* Installing a backdoor on the victim's machine. For example, the attacker can use Meterpreter to install a backdoor on the victim's machine. [Meterpreter](https://www.offensive-security.com/metasploit-unleashed/meterpreter-backdoor/) is a Metasploit Framework payload that gives an interactive shell from which an attacker can interact with the victim's machine remotely and execute the malicious code.
* Creating or modifying Windows services. This technique is known as [T1543.003](https://attack.mitre.org/techniques/T1543/003/) on MITRE ATT&CK (MITRE ATT&CK® is a knowledge base of adversary tactics and techniques based on real-world scenarios). An attacker can create or modify the Windows services to execute the malicious scripts or payloads regularly as a part of the persistence. An attacker can use the tools like sc.exe (sc.exe lets you Create, Start, Stop, Query, or Delete any Windows Service) and [Reg](https://attack.mitre.org/software/S0075/) to modify service configurations. The attacker can also [masquerade](https://attack.mitre.org/techniques/T1036/) the malicious payload by using a service name that is known to be related to the Operating System or legitimate software.
* Adding the entry to the "run keys" for the malicious payload in the Registry or the Startup Folder. By doing that, the payload will execute each time the user logs in on the computer. According to MITRE ATT&CK, there is a startup folder location for individual user accounts and a system-wide startup folder that will be checked no matter what user account logs in.

[Attack techniques](https://attack.mitre.org/techniques/T1547/001/)

* [Timestopping](https://attack.mitre.org/techniques/T1070/006/) technique: avoid detection by the forensic investigator and also to make the malware appear as a part of a legitimate program. The Timestomping technique lets an attacker modify the file's timestamps, including the modify, access, create and change times.

## Command & Control

* C&C or C2 Beaconing: type of malicious communication between a C&C server and malware on the infected host. The infected host will consistently communicate with the C2 server; that is also where the beaconing term came from.
* The protocols HTTP on port 80 and HTTPS on port 443 - this type of beaconing blends the malicious traffic with the legitimate traffic and can help the attacker evade firewalls.
* DNS (Domain Name Server). The infected machine makes constant DNS requests to the DNS server that belongs to an attacker, this type of C2 communication is also known as DNS Tunneling.

## Actions on Objectives (Exfiltration)

* Collect the credentials from users.
* Perform privilege escalation (gaining elevated access like domain administrator access from a workstation by exploiting the misconfiguration).
* Internal reconnaissance (for example, an attacker gets to interact with internal software to find its vulnerabilities).
* Lateral movement through the company's environment.
* Collect and exfiltrate sensitive data.
* Deleting the backups and shadow copies. Shadow Copy is a Microsoft technology that can create backup copies, snapshots of computer files, or volumes.
* Overwrite or corrupt data.

[insider threats](https://www.cisa.gov/defining-insider-threats)
