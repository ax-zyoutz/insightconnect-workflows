# Description

Reset a domain user's password with a command in Slack. Quickly respond, whether it be to an emerging threat or to another user that locked themselves out of their account.

Sample Slack command:

`reset-password-ad jdoe`

# Key Features

* **Break the Kill Chain** - Credentials provide attackers with easy access to numerous targets. Disabling a compromised account or forcing a password reset can quickly and effectively interrupt an attacker’s kill chain.
* **Buy Time to Investigate and Remediate** - In a pinch, disabling a user account can limit your threat exposure and buy your team valuable time to investigate and contain a threat. Disabling the user may not remediate the root cause, but it can mitigate the immediate risk while you work on fixing underlying issues.
* **Minimize Disruption to the User** - Forcing a user to reset their password is a small inconvenience compared to re-imaging their entire system. Acting fast can save valuable time and teach a valuable lesson without a noticeable impact to your business.

# Requirements

* [Slack](https://insightconnect.help.rapid7.com/docs/configure-slack-for-chatops)
* [Microsoft Active Directory](https://extensions.rapid7.com/extension/active_directory_ldap)

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

This workflow leverages InsightConnect's Parameters feature. This feature allows variables used multiple times throughout a workflow to be entered once and then referenced throughout the workflow.

There are two parameters you will need to configure in order to complete setup of your workflow:

* Channel: The Slack channel name in your environment where the workflow should be triggered
* Search Base: The base of the Active Directory user search request, eg. DC=example,DC=com

To begin, select "Parameters" either from the Workflow Control Panel or from the Builder to begin configuration.

After configuring the parameters, activate the workflow in order to trigger it.

### Usage

*This workflow will trigger in any direct messages to your Chatbot **or** any message in a channel directed @ your Chatbot. Note the Chatbot must be in the channel in order to trigger the workflow this way.*

To run the workflow, send a direct message to your InsightConnect Slack Chatbot or @ your Chatbot in a public channel starting with the command `reset-password-ad`. Use the target user's username, not the full email address.

For example, in a direct message to your Chatbot:
* `reset-password-ad jdoe`

For example, in a channel with your Chatbot:
* `@Rapid7 InsightConnect reset-password-ad jdoe`

The workflow will post the results in a thread.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Active Directory LDAP|5.2.2|2|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 2.0.0 - Leverage Parameters Feature | Update Active Directory LDAP plugin to version 5.2.2
* 1.1.0 - Use the automatic extraction functionality instead of 'Pattern Match' to extract a username | Update Active Directory LDAP to version 4.0.3 | Improve workflow messaging | Add link to AD LDAP connection configuration in Requirements | Update screenshots
* 1.0.4 - Update Active Directory LDAP to version 4.0.1
* 1.0.3 - Updated trigger syntax and documentation
* 1.0.2 - Updated trigger syntax and documentation
* 1.0.1 - Updated documentation
* 1.0.0 - Initial workflow

# Links

## References

[Slack](https://slack.com)
[Active Directory LDAP](https://extensions.rapid7.com/extension/active_directory_ldap)
