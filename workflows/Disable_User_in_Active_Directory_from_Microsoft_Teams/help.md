# Description

Disabling a compromised account can limit the scope of an attack and buy valuable time to investigate and contain the threat. This workflow disables a domain user account with a command in Microsoft Teams.

Sample Microsoft Teams Trigger Commands:

`!disable-user-ad <exampleuser>`

`!enable-user-ad <exampleuser>`


# Key Features

* **Break the Kill Chain** - Credentials provide attackers with easy access to numerous targets. Disabling a compromised account or forcing a password reset can quickly and effectively interrupt an attacker’s kill chain.
* **Buy Time to Investigate and Remediate** - In a pinch, disabling a user account can limit your threat exposure and buy your team valuable time to investigate and contain a threat. 
* **Reduce Portal Fatigue** - You have enough to do without logging into a different solution every 5 minutes. Control your response actions from chat instead.

# Requirements

* [Microsoft Teams](https://insightconnect.help.rapid7.com/docs/microsoft-teams)
* Active Directory connection

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

This workflow leverages InsightConnect's Parameters feature. This feature allows variables used multiple times throughout a workflow to be entered once and then referenced throughout the workflow.

There are three parameters you will need to configure in order to complete setup of your workflow:

* Team Name: The Microsoft Teams team name in your environment where the workflow should be triggered and respond
* Channel Name: The Microsoft Teams channel name in your environment where the workflow should be triggered and respond (the channel should exist in the aforementioned team)
* Search Base: The base of the Active Directory user search request, e.g. DC=example,DC=com

To begin, select "Parameters" either from the Workflow Control Panel or from the Builder to begin configuration.

After configuring the parameters, activate the workflow in order to trigger it.

# Usage

*This workflow will only trigger in the channel specified in the Microsoft Teams workflow steps.*

To run the workflow, send a message to the specified Microsoft Teams channel starting with the command `!disable-user-ad` or `!disable-user-ad`.

Commands should be in the following format:

`!disable-user-ad jdoe`

`!disable-user-ad jdoe`

The workflow will post the results in a thread.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Active Directory LDAP|5.2.2|3|
|Microsoft Teams|3.1.2|6|
|HTML|1.2.2|1|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 2.0.0 - Leverage Parameters Feature | Update Active Directory LDAP plugin to version 5.2.2 | Update Microsoft Teams to version 3.1.2
* 1.1.0 - New functionality - Enable AD User
* 1.0.3 - Update Active Directory LDAP to version 4.0.1
* 1.0.2 - Update to Microsoft Teams to make plugin the latest version
* 1.0.1 - Update trigger syntax, documentation, workflow name, and input parameters
* 1.0.0 - Initial workflow

# Links

## References

* [Active Directory LDAP](https://extensions.rapid7.com/extension/active_directory_ldap)
* [Microsoft Teams](https://teams.microsoft.com)
