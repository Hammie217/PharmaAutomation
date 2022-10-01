# Pharma Automation

## Pharmaceutical requirements
Audit Trail
Electronic Signatures
Batch Reports
Access management

## Common implementation tools
PM-Quality 
OPC UA
ASI interfact
IO-Link
Pack-ML
### Active Directory
Windows Active Directory (AD) is a great tool for access management that allows machine builders to use a companies domain. In many industries, especially the pharmaceutical it is common to have two ADs, one for corporate systems such as your laptop used for emails and another for automation equpment on the shop floor known as Operational Technology (OT). An AD allows for centralised credential management and access management along with many other things less important to machine building. The active directory is built in a folder like structure breaking objects down using Organisational Units (OUs) similar to folders on a computer. 
- Credential management: One of the many types of objects stored in an AD is a User, a user object can, and almost certainly will, contain many attributes but the two most important are the Common Name (CN) and userPassword containing a users username and password respectively for authentication. It is worth noting that the userPassword is required to be hashed and is impossible to read the contents externally, this can only be pushed to the AD and should be managed through existing corporate systems. A CN with its OU path is called a Distinguised Name (DN) which is useful for large ADs as a user can be found by following the DN path rather than searching throughout the whole AD.
- Access Management: Another type of object stored in an AD is a group, for a group the most important attribute is the members. Members contains an array of the DNs of all users with access to the group. This allows a machine builders access levels to correlate to AD groups simplifying access provisioning removing the need for any local definition of users access levels.
A system implementing AD credential and access management has many advantages for both the machine builder and client such as: Not reinventing the wheel, standardisation across machines, reduction of validation due to being an already accepted RERS system as well as allowing companies to manage their AD settings connecting to existing password, group and training management systems centrally.
As this is a windows system it tends to interface easily with the windows OS but is also fairly pain-free using other commonplace systems or generic LDAP drivers but in some cases an extra abstraction layer is required to convert AD groups to a readable format such as Simatic Logon for Siemens systems.

## Documentation