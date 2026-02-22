# Create, Configure, and manage identies

## Users

* Cloud identities: These users exist only in Microsoft Entra ID. Examples are administrator accounts and users that you manage yourself. Their source is Microsoft Entra ID or External Microsoft Entra directory if the user is defined in another Microsoft Entra instance but needs access to subscription resources controlled by this directory. When these accounts are removed from the primary directory, they're deleted.
* Directory-synchronized identities: These users exist in an on-premises Active Directory. A synchronization activity that occurs via Microsoft Entra Connect brings these users in to Azure. Their source is Windows Server AD.
* Guest users: These users exist outside Azure. Examples are accounts from other cloud providers and Microsoft accounts such as an Xbox LIVE account. Their source is Invited user. This type of account is useful when external vendors or contractors need access to your Azure resources. Once their help is no longer necessary, you can remove the account and all of their access.

## Create new user Entra ID

* Microsoft Entra Admin Center -> Users -> All users -> New User -> Create new user -> fill out User principal name (ChrisG), Name (Chris Green), First Name (Chris), Last Name (Green), Password (Make Unique password)

## Create security in ENtra ID

* Microsoft Entra Admin Center -> Identity -> Groups -> All Groups -> new group -> Fill out group type (Security), Group Name (Marketing), Membership Type (Assigned), Owners (Assign administrator account as the group owner), Members (Chris Green)

## Assign License to group

* All groups -> Marketing -> Manage -> Licenses -> open new tab -> Microsoft 365 admin center [Admin Center](https://admin.microsoft.com) -> Billing -> Licenses -> Select One -> Select Groups -> Assign License -> Assign button

## Restore or remove recently deleted user Microsoft Entra ID

After you delete a user, the account remains in a suspended state for 30 days. During that 30-day window, the user account can be restored, along with all its properties. After that 30-day window passes, the permanent deletion process is automatically started.

* Global administrator
* Partner Tier-1 Support
* Partner Tier-2 Support
* User administrator

## Remove user Microsoft Entra ID

* Micrsoft Entra Admin Center -> Identity -> Users -> Select check box of user -> Delete User

## Restore deleted user

* Users page -> Deleted users -> Select user deleted -> restore user -> ok -> All users

## Create, Configure, and manage groups

* Security groups: the most common type of groups and are used to manage member and computer access to shared resources for a group of users. For example, you can create a security group for a specific security policy. By doing it this way, you can give a set of permissions to all the members at once, instead of having to add permissions to each member individually. This option requires a Microsoft Entra administrator.
* Microsoft 365 groups: provide collaboration opportunities by giving members access to a shared mailbox, calendar, files, SharePoint site, and more. This option also lets you give people outside of your organization access to the group. This option is available to users as well as admins.

## Membership types

* Assigned: members are added and maintained manually.
* Dynamic: members are added based on rules, creating a Dynamic Group. These groups are still either a security group or Microsoft 365 group, just their members are controlled by rule.

## Create Microsoft 365 group in Entra ID

* Identity page in Microsoft Entra Admin Center -> Groups -> New Group -> Create group with information group type (Microsoft 365), Group Name (Northwest Sales), Membership type (Assigned), Owners (Administrator account as group owner), Members (member of group)

## Configure and manage device registration

* Bring Your Own Device (BYOD)
* Allow end users to be productive wherever and whenever and on any device
* Protect the organization's assets

## Microsoft Entra registered terms

* Definition: Registered to Microsoft Entra ID without requiring organizational account to sign in to the device
* Primary audience: Applicable to Bring your own device (BYOD), and Mobile devices
* Device ownership: User or Organization
* Operating systems: Windows 10, Windows 11, iOS, Android, and macOS
* Device sign in options: End-user local credentials, Password, Windows Hello, PIN Biometrics
* Device management: Mobile Device Management (example: Microsoft Intune)
* Key capabilities: SSO to cloud resources, Conditional Access

## Microsoft Entra joined terms

* Definition: Joined only to Microsoft Entra ID requiring organizational account to sign in to the device
* Primary audience: Suitable for both cloud-only and hybrid organizations
* Device ownership: Organization
* Operating systems: All Windows 10 & 11 devices except Windows 10/11 Home
* Device management: Mobile Device Management (example: Microsoft Intune)
* Key capabilities: SSO to both cloud and on-premises resources, Conditional Access, Self-service Password Reset and Windows Hello PIN reset

## Hybrid Microsoft Entra terms

* Definition: Joined to on-premises AD and Microsoft Entra ID requiring organizational account to sign in to the device
* Primary audience: Suitable for hybrid organizations with existing on-premises AD infrastructure
* Device ownership: Organization
* Operating systems: Windows 11, 10, 8.1 and 7, along with Windows Server 2008/R2, 2012/R2, 2016 and 2019
* Device sign in options: Password or Windows Hello for Business
* Device management: Group Policy, Configuration Manager standalone or co-management with Microsoft Intune
* Key capabilities: SSO to both cloud and on-premises resources, Conditional Access, Self-service Password Reset and Windows Hello PIN reset

  You have Win32 apps deployed to these devices that rely on Active Directory machine authentication.
  You want to continue to use Group Policy to manage device configuration.
  You want to continue to use existing imaging solutions to deploy and configure devices.
  You must support down-level Windows 7 and 8.1 devices in addition to Windows 10.

## Device writeback

Scenario: You have an application that you want to give access to users only if they are coming from registered devices.

Cloud: You can write Conditional Access policies for any Microsoft Entra integrated applications to authorize based on whether the device is joined to Microsoft Entra ID or not.

On-premises: This is not possible without device writeback. If the application is integrated with ADFS (2012 or higher) then you can write claim rules to check for the device status and then provide access only if the "is managed " claim is present. In order to issue this claim, ADFS will check for the device object in the "Registered Devices" container and then issue the claim accordingly.

Windows Hello For Business (WHFB) requires device writeback to function in Hybrid and Federated scenarios.

## Microsoft Entra Licenses

* group based licenses
* Paid or trial subscription for Microsoft Entra ID Premium P1 and above
* Paid or trial edition of Office 365 Enterprise E3 or Office 365 A3 or Office 365 GCC G3 or Office 365 E3 for GCCH or Office 365 E3 for DOD and above
* Features
* Licenses can be assigned to any security group in Microsoft Entra ID. Security groups can be synced from on-premises, by using Microsoft Entra Connect. You can also create security groups directly in Microsoft Entra ID (also called cloud-only groups), or automatically via the Microsoft Entra dynamic group feature.
* When a product license is assigned to a group, the administrator can disable one or more service plans in the product. Typically, this assignment is done when the organization is not yet ready to start using a service included in a product. For example, the administrator might assign Microsoft 365 to a department, but temporarily disable the Yammer service.
* All Microsoft cloud services that require user-level licensing are supported. This support includes all Microsoft 365 products, Enterprise Mobility + Security, and Dynamics 365.
* Group-based licensing is currently available only through the Azure portal. (coming soon to the Microsoft Entra admin center)
* Microsoft Entra ID automatically manages license modifications that result from group membership changes. Typically, license modifications are effective within minutes of a membership change.
* A user can be a member of multiple groups with license policies specified. A user can also have some licenses that were directly assigned, outside of any groups. The resulting user state is a combination of all assigned product and service licenses. If a user is assigned same license from multiple sources, the license will be consumed only once.
* In some cases, licenses cannot be assigned to a user. For example, there might not be enough available licenses in the tenant, or conflicting services might have been assigned at the same time. Administrators have access to information about users for whom Microsoft Entra ID could not fully process group licenses. They can then take corrective action based on that information.

## Change group license assignments

* Microsoft Entra Admin [center](https://entra.microsoft.com) -> Groups -> All Groups -> Manage -> Licenses
* Assignments -> Microsoft Admin [center](https://admin.microsoft.com) -> Billing -> Licenses -> select license -> Groups -> Assign License
* Set-MgUserLicense: there might be an insufficient number of licenses or a conflict between two service plans that can't be assigned at the same time

## Not enough licenses

Problem: There aren't enough available licenses for one of the products that's specified in the group. You need to either purchase more licenses for the product or free up unused licenses from other users or groups.

* See how many license: Microsoft Entra -> Identity -> Billing -> License -> All Products

Licensed users: you see a list of all users who have had licenses assigned directly or via one or more groups.
Licensed groups: you see all groups with product licenses assigned.

PowerShell cmdlets report this error as CountViolation.

## Service plans that conflict

Problem: One of the products that's specified in the group contains a service plan that conflicts with another service plan that's already assigned to the user via a different product. Some service plans are configured in a way that they can't be assigned to the same user as another, related service plan.

A user has a license for Office 365 Enterprise E1 assigned directly, with all the plans enabled. The user has been added to a group that has the Office 365 Enterprise E3 product assigned to it. The E3 product contains service plans that can't overlap with the plans that are included in E1, so the group license assignment fails with the Conflicting service plans error. In this example, the conflicting service plans are:

```
SharePoint Online (Plan 2) conflicts with SharePoint Online (Plan 1).
Exchange Online (Plan 2) conflicts with Exchange Online (Plan 1).

```

To solve this conflict, you need to disable two of the plans. You can disable the E1 license that's directly assigned to the user. Or, you need to modify the entire group license assignment and disable the plans in the E3 license. Alternatively, you might decide to remove the E1 license from the user if it's redundant in the context of the E3 license.

PowerShell cmdlets report this error as MutuallyExclusiveViolation

## Products depend on license

Problem: One of the products that's specified in the group contains a service plan that must be enabled for another service plan, in another product, to function. This error occurs when Microsoft Entra ID attempts to remove the underlying service plan. For example, this can happen when you remove the user from the group.

To solve this problem, you need to make sure that the required plan is still assigned to users through some other method or that the dependent services are disabled for those users. After doing that, you can properly remove the group license from those users.

PowerShell cmdlets report this error as DependencyViolation.

## Location isn't allowed

Problem: Some Microsoft services aren't available in all locations because of local laws and regulations. Before you can assign a license to a user, you must specify the Usage location property for the user. You can specify the location under the User, then Profile, then Edit the section in the Azure portal.

When Microsoft Entra ID attempts to assign a group license to a user whose usage location isn't supported, it fails and records an error on the user.

To solve this problem, remove users from unsupported locations from the licensed group. Alternatively, if the current usage location values don't represent the actual user location, you can modify them so that the licenses are correctly assigned next time (if the new location is supported).

PowerShell cmdlets report this error as ProhibitedInUsageLocationViolation.

## Microsoft Entra Mail and ProxyAddress attribute

Problem: While updating license assignment on a user or a group, you might see that the Microsoft Entra Mail and ProxyAddresses attribute of some users are changed.

Updating license assignment on a user causes the proxy address calculation to be triggered, which can change user attributes.

## LicenseAssignmentAttributeConcurrencyException in audit logs

Problem: User has LicenseAssignmentAttributeConcurrencyException for license assignment in audit logs. When group-based licensing tries to process concurrent license assignment of the same license to a user, this exception is recorded on the user. This typically happens when a user is a member of more than one group with same assigned license. Microsoft Entra ID will retry processing the user license and will resolve the issue. There is no action required from the customer to fix this issue.

## Multiple licenses

Microsoft Entra ID attempts to assign all licenses that are specified in the group to each user. If Microsoft Entra ID can't assign one of the products because of business logic problems, it won't assign the other licenses in the group either. An example is if there aren't enough licenses for all, or if there are conflicts with other services that are enabled on the user.

## Licensed group deletion

Must remove all licenses before deletion of group

## License with prerequise

Microsoft Workplace Analytics is an add-on product. It contains a single service plan with the same name. We can only assign this service plan to a user, or group, when one of the following prerequisites is also assigned:

```
Exchange Online (Plan 1)
Exchange Online (Plan 2)

```

If we try to assign this product on its own to a group, the portal returns a notification message. If we select the item details, it shows the following error message:

License operation failed. Make sure that the group has necessary services before adding or removing a dependent service. The service Microsoft Workplace Analytics requires Exchange Online (Plan 2) to be enabled as well.

To assign this add-on license to a group, we must ensure that the group also contains the prerequisite service plan. For example, we might update an existing group that already contains the full Office 365 E3 product, and then add the add-on product to it.

It is also possible to create a standalone group that contains only the minimum required products to make the add-on work. It can then be used to license only selected users for the add-on product. Based on the previous example, you would assign the following products to the same group:

```
Office 365 Enterprise E3 with only the Exchange Online (Plan 2) service plan enabled
Microsoft Workplace Analytics

```

From now on, any users added to this group consume one license of the E3 product and one license of the Workplace Analytics product. At the same time, those users can be members of another group that gives them the full E3 product, and they still consume only one license for that product.

## Force group license process to resolve errors

For example, if you free up some licenses by removing direct license assignments from users, you need to trigger the processing of groups that previously failed to fully license all user members. To reprocess a group, go to the group pane, open Licenses, and then select the Reprocess button on the toolbar.

## Force user license process to resolve users

For example, after you resolve duplicate proxy address problem for an affected user, you need to trigger the processing of the user. To reprocess a user, go to the user pane, open Licenses, and then select the Reprocess button on the toolbar.

## Migrate users with individual licenese to group license

### Recommend migration process

1. You have existing automation (for example, PowerShell) managing license assignment and removal for users. Leave it running as is.
2. Create a new licensing group (or decide which existing groups to use) and make sure that all required users are added as members.
3. Assign the required licenses to those groups; your goal should be to reflect the same licensing state your existing automation (for example, PowerShell) is applying to those users.
4. Verify that licenses have been applied to all users in those groups. This application can be done by checking the processing state on each group and by checking Audit Logs.
5. You can perform a random check of a few individual users by looking at their license details. You will see that they have the same licenses assigned “directly” and “inherited” from groups.
6. You can run a PowerShell script to verify how licenses are assigned to users.
7. When the same product license is assigned to the user both directly and through a group, only one license is consumed by the user. Hence no additional licenses are required to perform migration.
8. Verify that no license assignments failed by checking each group for users in error state.

Consider removing the original direct assignments. We recommend that you do it gradually, and monitor the outcome on a subset of users first. If you leave the original direct assignments on users, when the users leave their licensed groups they retain the directly assigned licenses, which might not be what you want.

## change licenese assignments for a user or group in Entra ID

* Users have the current license plan that's assigned to a group and inherited by the user and not assigned directly.
* You have enough available licenses for the license plan you're assigning. If you don't have enough licenses, some users might not be assigned the new license plan. You can check the number of available licenses.
* Always confirm users don't have assigned service licenses that can conflict with the desired license or prevent removal of the current license. For example, a license from a service such as Workplace Analytics or Project Online that has a dependency on other services.
* If you manage groups on-premises and sync them into Microsoft Entra ID via Microsoft Entra Connect, then you add or remove users by using your on-premises system. It can take some time for the changes to sync with Microsoft Entra ID to be picked up by group licensing.
* If you're using Microsoft Entra dynamic group memberships, you add or remove users by changing their attributes, but the update process for license assignments remains the same.

## Custom Security Attribute

Custom security attributes in Microsoft Entra ID are business-specific attributes (key-value pairs) that you can define and assign to Microsoft Entra objects. These attributes can be used to store information, categorize objects, or enforce fine-grained access control over specific Azure resources.

* Why use custom security attributes
* Extend user profiles, such as add Employee Hire Date and Hourly Salary to all my employees.
* Ensure only administrators can see the Hourly Salary attribute in my employees' profiles.
* Categorize hundreds or thousands of applications to easily create a filterable inventory for auditing
* Grant users access to the Azure Storage blobs belonging to a project.
* What to do with custom security attributes
* Define business-specific information (attributes) for your tenant.
* Add a set of custom security attributes on users, applications, Microsoft Entra resources, or Azure resources.
* Manage Microsoft Entra objects using custom security attributes with queries and filters.
* Provide attribute governance so attributes determine who can get access.
* Custom security features
* Available tenant-wide
* Include a description
* Support different data types: Boolean, integer, string
* Support single value or multiple values
* Support user-defined free-form values or predefined values
* Assign custom security attributes to directory synced users from an on-premises Active Directory

## System for Cross-Domain Identity Management (SCIM) Automatic user creation

* HCM system: Applications and technologies that enable Human Capital Management process and practices that support and automate HR processes throughout the employee lifecycle.
* Microsoft Entra Provisioning Service: Uses the SCIM 2.0 protocol for automatic provisioning. The service connects to the SCIM endpoint for the application, and uses the SCIM user object schema and REST APIs to automate provisioning and de-provisioning of users and groups.
* Microsoft Entra ID: User repository used to manage the lifecycle of identities and their entitlements.
* Target system: Application or system that has SCIM endpoint and works with the Microsoft Entra provisioning to enable automatic provisioning of users and groups.

System for Cross-Domain Identity Management (SCIM) is an open standard protocol for automating the exchange of user identity information between identity domains and IT systems. SCIM ensures that employees added to the Human Capital Management (HCM) system automatically have accounts created in Microsoft Entra ID or Windows Server Active Directory. User attributes and profiles are synchronized between the two systems, updating removing users based on the user status or role change.