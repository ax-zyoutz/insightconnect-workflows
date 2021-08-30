# Description

After locking down a user account, it may be convenient to allow administrators to unlock users accounts. The normal unlock account process would require logging into the AD server and manually unlocking it. This workflow allows a user to unlock an account via Microsoft Teams command.

Sample Microsoft Teams Trigger Commands:

`!unlock-user-ad <exampleuser>`

# Key Features

* Unlock a user in Active Directory from Microsoft Teams

# Requirements

* [Microsoft Teams](https://insightconnect.help.rapid7.com/docs/microsoft-teams)
* Active Directory connection

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

Once the workflow has been imported, you must edit the workflow parameters to match your Teams channel and team name, as well as the search base for your Active Directory/LDAP instance (see troubleshooting for tips on setting search base). 

Setting the search base for your instance isn't very intuitive to someone unfamiliar with AD. The search base identifies your organization and folder where the users are kept so that an entire query can be performed. For example, if you had a folder called "Users" in your AD instance, and your AD address was examplecompany.com, your search base would be:
OU=Users,DC=examplecompany,DC=com
If you have multiple "." in the address, split each into its own "DC" section. 


# Usage

*This workflow will only trigger in the channel specified in the Microsoft Teams workflow steps.*

To run the workflow, send a message to the specified Microsoft Teams channel starting with the command `!unlock-user-ad`

Commands should be in the following format:

`!unlock-user-ad jdoe`

The workflow will post the results in a thread.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Active Directory LDAP|5.3.0|2|
|Microsoft Teams|3.1.3|5|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 1.0.0 - Initial workflow

# Links

## References

* [Active Directory LDAP](https://extensions.rapid7.com/extension/active_directory_ldap)
* [Microsoft Teams](https://teams.microsoft.com)
