Authority - 
    Operators must meet strict demands on non-manipulation of data in their systems.
    As an operator must have detailed list of who has access to sensitive data, as well as records on when and where such data has been accessed.

Authenticity -
    Authrticity means that the log information on data transmissions must serve as a correct basis for invoicing, among other things.
    Today there is Euroption legislstion that also sets time limits for how long the log information must be kept, as well as when and how it should be destoryed.

Confidentiality - 
    Confidentiality is linked with privacy which is heavily protected by law.
    An operator must guatantee that private telecom dara is accessed lawfully, possibly in accordance of a court order.
    Both EU and the US e.g. have strict legislation on privacy.
    Infregements of these laws are serious crimes that can even lead to losing the right to carry on business in the country.

Availabilty -
    Available covers legal interception and emergency calls.
    Legal interceptions means the government's right to listen to communications in an operator's network.
    An operator must also by law be able to offer functional emergency call connections.
    An outage in critical national infrastrature, such as a telecom network, must be reported to authrities.

-----------------------------------------------------------------------------------------------
Attack examples:

Denial of Service - 
    An attempt to prevent or delay authorized access to a system for example by flooding the target system with crafted requests.

Man-in-the-Middle -
    A format of actice wiretapping where a third party arracker intercepts and modifier communicated data in order to masquerade as one or more of the entites involed in a communication association.

Session Hijacking - 
    An active attack in which a communication session is taken over.
    This is accompilshed by eavesdropping (e.g. sniffing in Ethernet), for example to steal a session token, followed by impersonation of one of the entites.

Password Cracking - 
    In threats to the system security, guessing of the password i.e.  password cracking is a way to get access to information and services that would normally be denied.

Trojan - 
    A computer program that appears to have a useful function, but also has a hidden and potentially mailcious function that evades security mechanisms, sometimes by exploiting legitimate authorizations of a system entity that invokes the program.
    E.g., a Trojan horse in an e-mail attachment that supposedly launches a video clip but instead executes a program that installs a backdoor on the system.

-----------------------------------------------------------------------------------------------
Type of Security Measures:
    Thread => Defer -> Protect -> Detect -> Response -> Recover & Replace => Asset

Thread - 
    Thread is defined as the means by which a security incident could take place.
    Threads may be external but also internal!

Deter -
    Implement deterrent controls discouraging potential attackers from even trying to attack the system.
    Creat and communicate security policies and directives.
    Emphasize the legal consequences.
    Visible controls at the perimeter can also deter potential attackers.

    E.g.,
        Code of Business Ethics
        Press Clippings of Incidents

Protect -
    Implement preventive controls protecting the system against actual insider and outsider threats.
    Risk Assessment is needed to focus on the biggest risks.
    Countermeasures include perimeter defense mechanisms, traffic separation, and node level controls.

    E.g.,
        Firewall
        Pin-code locks

Detect - 
    It is possible or cost efficient to completely eliminate all risks.
    The expected frequency of security incident can be reduced but the incident may still be possible.
    It is important that the system can detect incidents.
    Detective controls should be derived from the Risk Assessment.

    E.g.,
        Audit
        Intrusion Detection System

Respond -
    Under attack, the system must be able to send an alarm triggering actions by the operator's personnel.
    Automatic alarm is vital for handling precedures, aiming at dynamically limiting consequences of the incident (new firewall rules could be dynamically configured, users could be locked out, etc.).
    A trained security incident response team (SIRT) is a key success factor in containing, mitigating and recording the incident.

    E.g.,
        Security Staff, Guards
        Personnel & Qualified Job Description

Recover & Replace -
    A recovery plan is important.
    The system should be brought back to operational state to minimize downtime, and proper investigations must be started.
    It is necessary to investigate the complete attack flow and record the incident, criminal investigations may also be needed.

    E.g.,
        Backup
        Insurance

Asset -
    Everything that has value to the organization.
    Assets may be tangible or intangible.
    Humans are assets too!

---------------------------------------------------------------------------------------------
Vulnerabilities: What & Why?

Software Architecture and Design -
    Risk assessment helps on selecting the needed baseline security requirements to be implemented, to reduce security risk to an adequate level.
    Following the Security Desigen Rules help in defining a secure software design, and to implement security controls appropriately.

Programming Error -
    All software may have programming errors.
    Error can exist in a security function implementation, for example if password checker checks only 6 first charactors in the password.
    Error can also correlate directly to the use of coding language, for example when memory buffers are overflown due to missing check of the dara size copied to the memory buffer.
    These problems may allow among others unathorized system access, denial of service or arbitrary code executions.
    Security testing and enforcement of Secure Coding rules will diminish the number of coding errors that cause security vulnerabilities.

Operations and Management -
    Products amd services in operation require constant caretaking to run them securely without interruption.
    Security risks may arise e.g. due to unpatched vulnerabilities, lack of hardening, poor access management practices or misconfigured logging and backup systems.

---------------------------------------------------------------------------------------------
Security Incident Response Team (SIRT) for:
    - Vulnerability Watch
    - Vulnerabiliry Coordination (example follows)
    - Security Incident Forensics and Investigation
    - Security Customer Support Request (CSR)
    - Vulnerability Analysis Tool snd Support
    - Up-to-date view into Security in Telecom

----------------------------
CASE: Security Issues

Business critical problems reported:
    Hardening and File system intergrity: 60 issues, top 3:
    1. Uneeded services running (14)
    2. SSH is not used to replace telnet (16)
    3. Default accounts are active on the system (12)

    Access control: 16 issues, top 2:
    1. Password aging (6)
    2. Root privileges are shared (6)

    Patching: 4 issues, top 1
    1. Security patches are not installed in a timely manner.

    Logging; 1 issue
    1. No audit logging enabled

---------------------------- 
CASE: Lessons Learned
    - Response time for releasing security patches varies among the development organizations.
    - Getting the security patches installed in the customer network may takes a substanutial amount of time and efforts.
    - Some decvelopment organizations are not very proactive in adding security patches to their products.
      If there are no customer complaints, the security patching is left to next major release.
    - ~80% of the issue would not have existed if the Security Reliabilty Model would have been followed.
    - Development organization cooperation is needed in order to produce high quality answers to the customer.
    - The fixed for the issue were included in new product releases.

---------------------------------------------------------------------------------------------

Security Policies & Principles:
    - Denfense in Depth
    - Least Priviledge
    - Fail Safe Stance
    - Chock Point 
    - Diversity in Defense
    ...

Threats & Attacks:
    - Disclosure
    - Modification
    - Destruction/Loss
    - Interruption
    - Unauthorized access

---------------------------
Security Plane:

End User Security Plane - 
    The End-User Security Plane addresses security of access and use of the Service Provider's network by customers.
    This plane also represents actual end-user data flows.
    End-users may use a network that only provides connectivity, they may use it for value-added services such as VPNs, or they may use it to access netqork-based applications.

Signaling and Control Security Plane -
    The Signaling and Control Security Plane protects efficient delivery of information, services and application across the network.
    It typically involves machine-to-machine communications of information that allows network element (e.g. switches and routers) determine how to best route or switch traffic across the underlaying transport network.
    This Type of information is referred to as control or signaling infomation.
    In IP networks the control information is tranmitted together with the end-user information (in-band), whereas traditional telecom network's control information is carried over a separat (out-of-bong) signaling network.
O&M Security Plane - 
    O&M Security Plane protects operation and maintenance functions of the network elements, transmission  facilityes, back-office systems (Operations Suppport Systems, Business Support Systems, CUstomer Care Systems, etc), and Data Centers.
    THe Management Plane supports the Fault, Configuration, Accounting, Performance, and Security management functions (FCAPS).
    It should be noted that O&M Security Plane traffic may be in-boumd or out-of-bound (see Sinaling and Control Security Plane).

--------------------------
Security aspects:

Accountability - 
    Accountability procedures are used to keep track of who did want and when.
    Accountability functions track the usage of security services and network resources.
    Recovery and fault discovery are supported by accountability logs.

Authentication -
    Authentication serves





































































    










