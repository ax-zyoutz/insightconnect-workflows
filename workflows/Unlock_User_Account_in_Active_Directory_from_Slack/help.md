# Description

After locking down a user account, it may be convenient to allow administrators to unlock users account. The normal unlock account would require logging into the AD server and manually unlocking it. This workflow allows a user to unlock an account via Slack command.

Sample Slack Trigger Commands:

`@Rapid7 InsightConnect unlock-user-ad <exampleuser>`

# Key Features

* Unlock a user in Active Directory from Slack

# Requirements

* [Slack](https://insightconnect.help.rapid7.com/docs/configure-slack-for-chatops)
* Active Directory connection

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

Once the workflow has been imported, you must edit at least the search base workflow parameter.
You may also optionally choose a Slack channel name to exclusively activate this command from. Leave this blank to allow for any channel.


Setting the search base for your instance isn't very intuitive to someone unfamiliar with AD. The search base identifies your organization and folder where the users are kept so that an entire query can be performed. For example, if you had a folder called "Users" in your AD instance, and your AD address was examplecompany.com, your search base would be:
OU=Users,DC=examplecompany,DC=com

If you have multiple "." in the address, split each into its own "DC" section. 

After configuring the workflow parameters steps, activate the workflow in order to trigger it.

# Usage

To run the workflow, send a message to the specified Slack channel.

Commands should be in the following format:

`@Rapid7 InsightConnect unlock-user-ad <exampleuser>`

The workflow will post the results in a thread.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Active Directory LDAP|5.3.0|2|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 1.0.0 - Initial workflow

# Links

## References

* [Active Directory LDAP](https://extensions.rapid7.com/extension/active_directory_ldap)
* [Slack](https://slack.com/)