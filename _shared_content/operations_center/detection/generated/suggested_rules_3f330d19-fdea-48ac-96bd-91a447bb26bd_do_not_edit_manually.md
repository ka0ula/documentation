## Related Built-in Rules

Benefit from SEKOIA.IO built-in rules and upgrade **Sophos EDR** with the following detection capabilities out-of-the-box.

[SEKOIA.IO x Sophos EDR on ATT&CK Navigator](https://mitre-attack.github.io/attack-navigator/#layerURL=https%3A%2F%2Fraw.githubusercontent.com%2FSEKOIA-IO%2Fdocumentation%2Fmain%2F_shared_content%2Foperations_center%2Fdetection%2Fgenerated%2Fattack_3f330d19-fdea-48ac-96bd-91a447bb26bd_do_not_edit_manually.json){ .md-button }
??? abstract "CVE-2020-0688 Microsoft Exchange Server Exploit"
    
    Detects the exploitation of CVE-2020-0688. The POC exploit a .NET serialization vulnerability in the Exchange Control Panel (ECP) web page. The vulnerability is due to Microsoft Exchange Server not randomizing the keys on a per-installation basis resulting in them using the same validationKey and decryptionKey values. With knowledge of these, values an attacker can craft a special viewstate to use an OS command to be executed by NT_AUTHORITY\SYSTEM using .NET deserialization. To exploit this vulnerability, an attacker needs to leverage the credentials of an account it had already compromised to authenticate to OWA. 
    
    - **Effort:** elementary

??? abstract "CVE-2020-17530 Apache Struts RCE"
    
    Detects the exploitation of the Apache Struts vulnerability (CVE-2020-17530).
    
    - **Effort:** intermediate

??? abstract "CVE-2021-20021 SonicWall Unauthenticated Administrator Access"
    
    Detects the exploitation of SonicWall Unauthenticated Admin Access.
    
    - **Effort:** advanced

??? abstract "CVE-2021-20023 SonicWall Arbitrary File Read"
    
    Detects Arbitrary File Read, which can be used with other vulnerabilities as a mean to obtain outputs generated by attackers, or sensitive data.
    
    - **Effort:** advanced

??? abstract "Cron Files Alteration"
    
    Cron Files and Cron Directory alteration used by attacker for persistency or privilege escalation.
    
    - **Effort:** advanced

??? abstract "Package Manager Alteration"
    
    Package manager (eg: apt, yum) can be altered to install malicious software
    
    - **Effort:** advanced

??? abstract "Possible Malicious File Double Extension"
    
    Detects request to potential malicious file with double extension
    
    - **Effort:** elementary

??? abstract "RYUK Ransomeware - martinstevens Username"
    
    Detects user name "martinstevens". Wizard Spider is used to add the user name "martinstevens" to the AD of its victims. It was observed in several campaigns; in 2019 and 2020.
    
    - **Effort:** elementary

??? abstract "Raccoon Stealer 2.0 Legitimate Third-Party DLL Download URL"
    
    Detects Raccoon Stealer 2.0 malware downloading legitimate third-party DLLs from its C2 server. These legitimate DLLs are used by the information stealer to collect data on the compromised hosts.
    
    - **Effort:** elementary

??? abstract "SEKOIA.IO Intelligence Feed"
    
    Detect threats based on indicators of compromise (IOCs) collected by SEKOIA's Threat and Detection Research team.
    
    - **Effort:** elementary

??? abstract "SSH Authorized Key Alteration"
    
    The file authorized_keys is used by SSH server to identify SSH keys that are authorized to connect to the host, alteration of one of those files might indicate a user compromision
    
    - **Effort:** advanced

??? abstract "Sophos EDR Application Blocked"
    
    Sophos EDR detected a potentially malicious application and blocked it.
    
    - **Effort:** master

??? abstract "Sophos EDR Application Detected"
    
    Sophos EDR detected a potentially malicious application.
    
    - **Effort:** master

??? abstract "Sophos EDR CorePUA Clean"
    
    Sophos EDR detected a potentially unwanted application and cleaned it.
    
    - **Effort:** master

??? abstract "Sophos EDR CorePUA Detection"
    
    Sophos EDR detected a potentially unwanted application.
    
    - **Effort:** master

??? abstract "Suspicious URI Used In A Lazarus Campaign"
    
    Detects suspicious requests to a specific URI, usually on an .asp page. The website is often compromised.
    
    - **Effort:** intermediate
