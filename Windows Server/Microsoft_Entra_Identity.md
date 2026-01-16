
# Microsoft Entra Identity

## Identity landscape

* Zero Trust
* Verify Expliciblity
* Use Least Privileges
* Assume Breach
* Identity
* Business to Business (B2B)
* Business to Consumer (B2C)
* Verifiable Credentials
* Decentralize Providers
* Actions
* Authenticate - Prove - AuthN
* Authorize - Get - AuthZ
* Administer - Configure
* Audit - Report
* Usage
* Access applications and data
* Secure - Cryptography
* Dollars - Licenses
* Maintain
* Protect - Detect - Respond
* Always think and design with zero trust. Don't give access to data and applications becuase the user had access previously. (always confirm)
* Systems provide verified accounts for users and applications. Identify services from Microsoft Entra ID, business to business federation, business to customer, and decentralized identity providers
* Specific actions identify providers. Users and application can authenticate and authorize to gain access. Administrators need to maintain the identity of systems
* Many actions can be performed once credentials are verified
* Always keep systems up to date

Class Identity: Restrict everything to a secure network
Zero trust Identity: protect assets anywhere with a central policy

## Zero Trust Principles

* Verify Explicibility -> Indicate all available data points including:
* user identity & location
* device health
* service or workload context
* data classification
* anomalies
* Least privileged access -> Secure both data and productivity limit user access:
* Just in time (JIT)
* Just Enough Access (JEA)
* Risk based adaptive policies
* data protection against out-of band vectors
* Assume Breach -> Minimize blast radius and prevent lateral movement:
* segmenting access by network, user, devices, and app awareness
* Encrypting all sessions end to end
* analysis for threat detection, posture, visibility, and improving defenses

## Zero Turst Solutions

* Identity, Endpoints, Data, Apps, Infrastrucutre, networks

## Zero Trust Architecture

![zero trust Architecture](../../images/zero-trust-architecture.png)

## Control Plane

Part of a network that routes network traffic around the network architecture. Tool or service that directs access to resources based on specific criteria. (Identity)

## Identity Provides AAAA

* Athentication:
* User sign on experience
* Trusted source(s)
* Federative protocols
* Level of assurance
* Authrization
* User sign on experience
* Can a user access the resource
* what can they do when they have access?
* Administration
* Single view management
* Application of business rules
* Automated requests, approvals, and access assignment
* Entitlement management
* Auditing
* Track who does what, when, where, and how
* Focused auditing
* In-depth collated reporting
* Governance & Compliance

## Identity Provider (IdP)

System that creates, manages, and stores digital identities (Microsoft Entra ID)

* Common Components
* Repistoriory of user identities
* Authentication system
* Security protocol that defined against intrusion
* Someone we trust

## Common Identity Protcols

* OpenID provider (Open ID Connect (OIDC)): Authentication protcol based on OAuth2 protocol (used for authorization). OIDC uses standard message flows with OAuth2 to provide identity with system entity (OpenID-Provider) issues JSON format identity tokens to OIDC relying parties via rest HTTP API
* SAML Identity Provider (Security Assertion Markup Language (SAML)): Open standard for exchanging authentication and authorization data between identity and service provider. An XML based markup language for security assertions, statements that service providers use to make access control decisions

## Identity Administration

How identity objects managed over the lifetime of the identity's existence. This administration can be manual or automated.

## Identity Administration Provides

* System that is highly configurable around business processes
* Agility to scale resources according to demand
* Cost savings through the distribution and automation of management
* Flexibility around synchronization, profileration, and change control

## Identity administration tasks

* Identity proliferation: Deals with storage of identity objects within the environment. Active Directory, other directory services, and application specific identity stores
* Provision and deprovision: Two separate capabilities, Provisioning speaks towards how identiy objects are created within a system (Deletion, disablement of seucrity principle or removal of access)
* Identity Updates: Surrounds how identity information is updated throughout the environment. Move away from manual effort to more automated and streamlined approach
* Synchronization: Ensuring the identity systems within an environment are up to date with the latest identity information. Key things that influenece this capability are how synchronization is performed manual, time-based or event driven
* Password Management: Focuses on where and how passwords are set throughout the identity infrastructure.
* Group Management: Focuses on how organization manages groups (Active Directory and/or LDAP) within their environment. Groups of the most common form for determining access permissions to resources and are expensive to manage and operate
* Application Entitlement Management: Defines how identities are granted access to applications. Focuses on providing coarse-gained application enetitlements that are enforced as a capability contained with the authorization pillar.
* User Interface: How the end user is able to request, or make, updates to their identity information. Users continue to contact the service Desk for any updates to their identity information
* Change Control: Capability focuses on how changes flow through the environment whether manually completed by a Service Desk professional. There can be automation with or without workflow, which drives the change process.

## Identity Management Automation

* Powershell
* Cross platform powershell Runs on Windows, macOS, Linux
* Requires Windows PowerShell or PowerShell
* CLI (Command Line Interface)
* Cross Platform command-line interface, installable on Windows, macOS, Linux
* Runs in Windows PowerShell, Command Prompt, or Bash and other Unix Shells

## Create User

* Azure CLI Create User

```
ax ad user create --display-name "New User" --password "Password" --user-principal-name [email protected]

```

* Microsoft Graph Create user

```
New-MgUser -DisplayName "New User" -PasswordProfile Password -UserPrincipalName "[email protected]" -AccountEnabled $true -MailNickName "Newuser"

```

## Microsoft Graph

Exposes Rest APIs and client libraries to access data on the following Microsoft Cloud Services like Microsoft Entra ID, Microsoft 365, devices

* Single endpoint [wesite location](https://graph.microsoft.com) to provide access to rich, people-centric data and insights in Microsot Cloud, Microsoft 365, Windows 10, Enterprise Mobility + Security.
* Microsoft Graph Connectors Work in the incoming direction, delivering data external to the Microsoft Cloud into Microsoft Graph Services and applications, to enhance Microsoft 365 experiences such as Microsoft Search. Used data sources such as Box, Google Drive, Jira, and Salesforce
* Microsoft graph data connnect provides a set of tools to streamline secure and scalable delivery of Microsoft Graph data to popular Azure Data stores. The cached data serves as data sources for Azure development tools that you can use to build intelligent applications.

## Centralized Identity Management or Central Identity System

Single identity tool where credentials are stored and managed, to provide authentication and authorization capabilities. System can be on-premises or cloud-based. Centrally managed by an indentity authority or administrator

Microsoft Entra ID

* Credentials are verified when stored
* Management is by single authority
* Admin or Admin group
* Used for identity and access management
* Secure adaptive access: Protect access to resources and data using strong authentication and risk-based adaptive access policies without compromising user experience
* Seamless user experience: Provide an easy, fast sign-in experience to keep your users productive, reduce time managing passwords, and increase end-user productivity
* Unified Identity management: Manage all your identities and access to all your apps in a central location, whether they're in the cloud or on-premises, to improve visibility and control
* Simplified Identity governance: Control access to apps and data for all users and admins efficiently with automated identity governance to ensure only authorized users have access

## Deentralized Identity

Helps people, organizations, and tings interact with each other transparently and secrely, in an identity trust fabric. People control their own digital identity and credentials.

* Decentralized Identifiers (DIDs): User-generated, self-owned, globally unique identifiers rooted in decentralized systems. Possess unique characteristics, like greature assurance of immutability, censorhip reistance, and tamper evasiveness

Download a DID User Agent App. Trusted user agent helps you navigate the web, a DID User Agent helps you manage all aspects of DIDs -- creation of identifiers, authentication, data encryption, and management of keys and permissions.

DID implementations should use decentralized systems strictly to anchor identifiers and non-PLL DPKI metadata to enable routing and authentication for the DID owner without risk of censorship

## Decentralized Identity Components

* W3C Centralized Identifiers (DIDs): IDs users create, own, and control independently of any organization or government. DIDs are globally unique identifiers linked to Decentralized Public Key Infrastructure (DPKI) metadata composed of JSON documents that contain public key material, authentication descriptors, and service endpoints
* Decentralized Systems (Blockchains and ledgers): DIDs are rooted in decentralized systems that provide the meahnism and features required for PDKI.
* DID User Agents: Applications that enable real people to use decentralized identities. Aid in creating DIDs, manging data and permissions, and signing/validating DID-linked claims.
* DIF Universal Resolver: Srrver that utilizes a collection of DID drivers to provide a standard means of lookup and resolution for DIDs across impemtnations and decntralized systems and that returns the DID Document Object (DDO) that encapsulated DPKI metadata associated with a DID
* DIF Idnentity Hubs: Replicated mesh of encrypted personal datastores, composed of cloud and edge instances, that facilitate identity data storage and identity interactions
* DID Attestations: DID signed attestations are based on standard formats and protcols. They enable identity owners to generate, present, and verify claims. The beginning of trust between users of the system
* Decentralized apps and services. DIDs paired with identity Hub personal datasotres enable the creation of a new class of apps and services. They store data with the user's identity Hub and oeprate with the confines of the permissions they're granted

## Identity and Access Management (IAM)

An Identity solution controls access to an organization's apps and data. Users, devices, and applications have identities. IAM components support the authentication and authorization of these and other identies. Process of autehntication controls who or what uses an account. Authorization controls what that user can do in applications (Microsoft Entra ID)

![Basic Identity Architecture](../../images/identity-basic-architecture.png)

## Microsoft Entra ID Terminology

* Identity: An object that can be autehtnicated. An identity can be a user with a username nad password. Identities also include applications or otehr servers that might require authentication through secret keys or credentials
* Account: An identity that has data associated with it. You can't have an account without an identity
* Microsoft Entra Account: An identity created through Microsoft Entra ID or another Microsoft Cloud Service, such as Microsoft 365. Identies are stored in Microsoft Entra ID and accessible to your organization's cloud service subscriptions. This account is also sometimes called a work or school account
* User: A single personal verifiable identity in Microsoft Entra ID
* Group: A container of users or identities that can be asigned security privileges or restrictions. Often used to control access to speific shared resource to a set of accounts instead of assigning individually
* Azure Subscription: Used to pay for Azure Cloud services. You can have many subscriptions and they're linked to a credit card
* Microsoft Entra tenant/directory: Dedicated and trusted instance of Microsoft Entra ID, a tenant is automatically created when your organizations signs up a Microsoft Cloud Service Subscription.
* More instances of Microsoft Entra ID can be created. Entra ID is the underlying product providing the identity service. The term Tenant means asingle instance of Microsoft Entra ID representing a single organization. The terms Tenant and Diretory can be used interchangeably
* Administrative Unit: A portioned off piece of a Microsoft Entra tenant used to create and administrative boundary

## Microsoft Entra External Identities

Refers to all the ways you can secureley interact with users outside of your organization if you want to collaborate with partners, distribbutors, suppliers, or vendors, you can share your resources and define how your internal users can access external organizations.

## Type of Business to Business (B2B)

* B2B collaboration: Collaborate with external users by letting them use their preferred identity to sign in to your Microsoft applications or other enterprise applications (SaaS app, custom-developed apps, etc.) B2B collaboration users are represented in your directory, typically as guest users
* B2B Direct Connect: Establish a mutual, two-way trust with another Microsoft Entra organization for seamless collaboration. B2B direct connect currently supports Teams shared channels, enabling external users to access your resources from within their home instances of teams. B2B direct connect users aren't represented in your directory, but they're visible from within the Teams shared channel and can be monitored in Teams admin center reports.

## Microsoft Entra Business to Consumer (B2C) (Customer Identity Access Management (CIAM))

Solution capable of supporting millions of users and billions of authentications per day. Takes care of the scaling and safety of the authentication platform, monitoring, and automatically handling threats like denial-of-service, password spray, or brute force attacks. Separate service from Microsoft Entra ID, allows businesses to build customer facing appliacations, and then allow anyone to sign up into those applications with no restrictions on user account

## Microsoft Identity Providers (IdP)

System that creates, manages, and stores digital identies.

* Three most common components
* A Repository of user identies
* An authentication system
* Security protocols that defend against intrusion

## Identity providers in Microsoft Azure

* Microsoft Entra Domain Services: Provides managed domain services with a subset of fully compatible traditional AD DS features such as domain join, group policy, LDAP, and kerberos/NTLM Authentication
* AD DS: Enterprise ready LDAP server that provides key features such as identity and authentication, computer object management, group policy, and trusts
* AD DS: Central component in many organizations with an on-premises IT environment, and provides core user account authentication and computer management features
* Microsoft Entra ID: Cloud-based identity and mobile device management that provides user account and authentication services for resources such as Microsoft 365, the Azure Portal, or SaaS applications
* Microsoft Entra ID: Can be synchronized with an on-premises AD DS environment to provide a single identity to users that work natively in the cloud.
* Active Directory Domain Services: Enterprise-ready lightweight directory access protocol (LDAP) server that provides key features such as identity and authentication, computer object management, group policy, and trusts
* Entra Domain Services: Provides managed domain services with a subset fully compatiable traditional AD DS features such as domain join, group policy, LDAP, and kerberos/NTLM authentication
* Entra DS: integrates with Entra ID, which itself can synchronize with an on-premises AD DS environment. This ability extends central identity use cases to traditional web applications that run in Azure as part of a lift-and-shift strategy

## Identity Licensing

* Microsoft Entra ID P1 or P2 License: License allows you to purhcase access to the more features in Microsoft Entra ID. You need a Microsoft Entra ID P2 license if you want to use privileged Identity Management (PMI) capability in Microsoft Entra ID. Any user that assigns or manages assignments in PIM needs to have a license. A User within privileged user doesn't need a license
* Microsoft 365, Office 365, Windows License: License assigned to Microsoft Entra user or group to grant themm access to use Office or Windows products. You need one license for each user who needs access to Windows and/or Office
* Monthly Active User (MAU) License: License used with Microsoft Entra External Identities. A monthly report pulled for billing purposes, looking for external users logging in during the month

## Licenses

| License | Monthly Active User (MAU) Billing |
| --- | --- |
| purchased agreement to allow users or guests to use a Microsoft technology | Pricing model for external users in Microsoft Entra ID |
| Common SKUs/Licenses | MAU billing available when you have a subscrption |
| Microsoft Entra ID P1 or P2 License | Report of active users runs each month for billing |
| Microsoft 365 / Office 365 License | First 50,000 MAUs free monthly (P1 and P2) |
| Windows License | Helps establish predictable pricing |

* Subscription: An agreement with Microsoft to use one or more Microsoft cloud platforms or services for which charages accure based on either a per user or a cloud-based resource consumption. Microsoft's Software as a Service (SaaS)-based cloud offerings (Microsoft 365 and Dynamics 365) charge per-user license fees. Microsoft's Platform as a Service (PaaS) and Infrastructure as a Service (IaaS) cloud offerings (Azure) charge based on cloud resource consumption. You can also use a trial subscription, but the subscription expires after a specific amount of time or consumption charges. You can convert a trial subscription to a paid subscription. Organizations can have multiple subscriptions for Microsoft's cloud offerings.
* License: For Microsoft's SaaS cloud offerings, a license allows a specific user account to use the services of the cloud offering. You're charged a fixed monthly fee as part of your subscription. Administrators assign licenses to individual user accounts in the subscription.

## Authorization

Covers what an identity can access and what are they allowed to do once they gain access identity authorization provides:

* Methods of assigning entitlement allowing for increased security and less administration
* Ability to manage policy control
* Simplify enforcement by standardizing on a common approach

## Authorization concept

* Entitlement Type: Entitlements focus on whether or not an identity has been granted (“entitled”) access to a particular resource. As such, entitlements are handled using many different types. The assignment of entitlements happens at the application level, centrally via groups, defined through role based access control or attributes (ABAC) or applied centrally using a policy based (PBAC) approach.
* Access Policies: Focus on set of applications, data, and which users and groups can perform activities. Set of rules around getting your job done. Least access needed
* Enforcement: The enforcement capability focuses on how an organization handles the enforcement of authorization activities. In most cases, organizations handle enforcement at the application layer. Meaning enforcement is completed by an API within the application itself. Some forms of enforcement consist of the use a reverse proxy (such as UAG) to externalize authorization enforcement. A current trend is to use an external policy source (such as XACML) to determine how the identity interacts with the resource.
* Authorization (AuthZ): Set permissions that are used to elevate access to resources or functionality
* Authentication (AuthN): proving that an entity like a user or service is indeed who they claim to be

## Authorization approaches

* Access Control Lists (ACL): Explicit list of specific entities who do or don't have access to a resource or functionality. Offers fine control over resources, but difficult to maintain large groups of users and resources
* Role based Access control (RBAC): Roles are defined to describe the kinds of activities an entity can perform. Grant access to roles rather than to individual entities. An administrator can then assign roles to different entities to control which ones have access to what resources and functionality.
* Attribute-based Access Control (ABAC): Rules are applied to attributes of the entity, the resources being accessed, and the current environment to determine whether access to some resources or functionality is permitted. An example might be only allowing users who are managers to access files identified with a metadata tag of “managers during working hours only” during the hours of 9AM - 5PM on working days. In this case, access is determined by examining the user’s attribute (status as manager), the resource’s attribute (metadata tag on a file), and also an environment attribute (the current time).
* Policy-based Access Control (PBAC): A strategy for managing user access to one or more systems, where the business-role of the user is combined with policies to determine what access the user has.
* Authentication Context: These applications can be your own custom applications, custom line of business (LOB) applications, applications like SharePoint, or applications protected by Microsoft Defender for Cloud Apps. For example, an organization can keep files in SharePoint sites like the lunch menu or their secret BBQ sauce recipe. Everyone has access to the lunch menu site. However, users who have access to the secret BBQ sauce recipe site are required to connect from a managed device.

## Auditing in Identity

Auditing provides a way for an administrator to detect an attack that has already occurred or is in progress. Also, auditing is a tool for compliance and tracking what identity did what. In addition, auditing can help a developer to debug security-related problems. For example, if an error in the configuration of the authorization or checking policy accidentally denies access to an authorized user, a developer can quickly discover and isolate the cause of this error by examining the event log.

## Goverance

governance is the act or process of overseeing the control and direction of a system. That system could be a government, a budget, or an identity solution on Azure. Governance has processes and controls in place to both operate the systems and to evaluate the accountable running of the system. It's never enough to build a solution and then forget it. You have to monitor its running, update the processes regularly, remove or replace outdated features, and so on. If you don't, the system is slowly going to degrade and fail.

## Identity lifecycle management

Identity Lifecycle Management aims to automate and manage the entire digital identity lifecycle process.

1. Are there already systems of record: data sources, which the organization treats as authoritative. For example, the organization might have an HR system. That system is authoritative for providing the current list of employees, and some of their properties such as the employee's name or department.
2. Compare the system of record with one or more directories and databases used by applications, and resolve any inconsistencies between the directories and the systems of record.
3. Determine what processes can be used to supply authoritative information for visitors. It is necessary to find an alternate way to determine when a digital identity for a visitor is no longer needed.

## Management strategy

* Join: when an individual comes into scope of needing access, an identity is needed by those applications, so a new digital identity might need to be created if one isn't already available.
* Move: when an individual moves between boundaries, extra access authorization is required to be added or removed to their digital identity.
* Leave: when an individual leaves the scope of needing access, access might need to be removed, and the identity is no longer be required by applications other than for audit or forensics purposes.

## Monitoring tools

* Azure Monitor
* Application Insights
* Azure Service Health
* Azure Resource Health
* Azure Resource Manager
* Azure Policy