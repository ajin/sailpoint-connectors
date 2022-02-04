# Oracle Unified Directory LDAP SailPoint IdentityIQ integration reference
This page provides reference information specific to Oracle Unified Directory (OUD) LDAP SailPoint integration. 

## Features
Integrating with OUD service with SailPoint IdentityIQ will enable the following capabilities:

Account Management: 
- [x] Query (aggregate) user accounts from defined scope
- [x] Retrieve (refresh) user account information
- [x] Enable pass-through authentication to the directory
- [x] Create, update and delete user account
- [x] Enable and disable user account
- [x] Allow (self) change password from the console
- [x] Retrieve lock state of user account
- [ ] Unlock user account
- [x] Modify group/entitlement membership of user account

Group Management:
- [x] Query (aggregate) groups from defined scope
- [x] Retrieve (refresh) group information
- [x] Create, update and delete groups

## Tested version
- [x] Oracle Unified Directory 12.2.1.4.0

## Integration configuration
The Oracle Unified Directory integration connector uses the following settings:
| Setting | Value |
|--|--|
| Application Type | LDAP |
| featureString | AUTHENTICATE, MANAGER_LOOKUP, SEARCH, PROVISIONING, SYNC_PROVISIONING, ENABLE, PASSWORD, CURRENT_PASSWORD |
| Identity Attribute | entryuuid |
| DN Attribute | entrydn |
| Display Attribute | CN |
| User Object Class | inetorgpersonj |
| User Object Filter | (objectclass=inetorgperson) |
| Account Disabled Attribute | ds-pwp-account-disabled |
| Account Disabled Value | TRUE |
| Account Enabled Value | FALSE |
| Password Attribute | userpassword |
| Password Expiration Attribute | passwordexpirationtime |
| Group Object Class | groupofuniquenames |
| Group Object Filter | (objectclass=groupofuniquenames) |
| Native Object Type | groupOfUniqueNames |
| Identity Attribute | DN |
| Display Attribute | CN |
| Membership Attribute | uniquemember |

## Installation
To install the connector, simply:

### Web
Use the Import From File page to import the new directory connector into IdentityIQ. Open IdentityIQ from your Web browser and log in with the administrator account. Next, navigate to `Global Settings` -> `Import from File`. Select the file `oud-connector.xml` and click import. This will create a new Application Type. 

### CLI
Launch the IdentityIQ console by running the iiq console command from the `identityiq_home\WEB-INF\bin` directory. Next, use the console command to import `oud-connector.xml` file to import the directory connector.

```console
iiq console
> import oud-connector.xml
> quit
```





