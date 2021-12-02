# Description

Reset a domain user's password with a command in Microsoft Teams. Quickly respond, whether it be to an emerging threat or to another user that locked themselves out of their account.

Sample Microsoft Teams command:

`!reset-password-ad <username>`

# Key Features

* **Break the Kill Chain** - Credentials provide attackers with easy access to numerous targets. Disabling a compromised account or forcing a password reset can quickly and effectively interrupt an attacker’s kill chain.
* **Buy Time to Investigate and Remediate** - In a pinch, disabling a user account can limit your threat exposure and buy your team valuable time to investigate and contain a threat. Disabling the user may not remediate the root cause, but it can mitigate the immediate risk while you work on fixing underlying issues.
* **Minimize Disruption to the User** - Forcing a user to reset their password is a small inconvenience compared to re-imaging their entire system. Acting fast can save valuable time and teach a valuable lesson without a noticeable impact to your business.

# Requirements

* [Microsoft Teams](https://insightconnect.help.rapid7.com/docs/microsoft-teams)
* [Microsoft Active Directory](https://extensions.rapid7.com/extension/active_directory_ldap)

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

This workflow leverages InsightConnect's Parameters feature. This feature allows variables used multiple times throughout a workflow to be entered once and then referenced throughout the workflow.

There are three parameters you will need to configure in order to complete setup of your workflow:

* Team Name: The Microsoft Teams team name in your environment where the workflow should be triggered and respond
* Channel Name: The Microsoft Teams channel name in your environment where the workflow should be triggered and respond (the channel should exist in the aforementioned team)
* Search Base: The base of the Active Directory user search request, eg. DC=example,DC=com

To begin, select "Parameters" either from the Workflow Control Panel or from the Builder to begin configuration.

After configuring the parameters, activate the workflow in order to trigger it.

### Usage

*This workflow will only trigger in the channel specified in the Microsoft Teams workflow steps.*

To run the workflow, send a message to the specified Microsoft Teams channel starting with the command `!reset-password`. 

Commands should be in the following format:
`!reset-password <username>`

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Microsoft Teams|3.1.2|5|
|Active Directory LDAP|5.2.2|2|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 2.0.0 - Leverage Parameters Feature | Update Active Directory LDAP plugin to version 5.2.2 | Update Microsoft Teams to version 3.1.2
* 1.1.1 - Update documentation
* 1.1.0 - Use the automatic extraction functionality instead of 'Pattern Match' to extract a username | Update Microsoft Teams to version 3.1.0 | Update Active Directory LDAP to version 4.0.3 | Improve workflow messaging | Add link to AD LDAP connection configuration in Requirements | Update screenshots
* 1.0.3 - Update Active Directory LDAP to version 4.0.1
* 1.0.2 - Update to make Microsoft Teams plugin the latest version
* 1.0.1 - Updated trigger syntax and documentation
* 1.0.0 - Initial workflow

# Links

## References

* [Microsoft Teams](https://teams.microsoft.com)
* [Active Directory LDAP](https://extensions.rapid7.com/extension/active_directory_ldap)
