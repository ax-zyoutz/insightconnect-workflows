# Description

Disabling a compromised account can limit the scope of an attack and buy valuable time to investigate and contain the
threat. This workflow disables or enables a domain user account with a command in Slack.

Sample Slack Trigger Commands:

`@Rapid7 InsightConnect disable-user-ad <username>`

`@Rapid7 InsightConnect enable-user-ad <username>`

# Key Features

* Disable an Active Directory LDAP user directly from Slack
* Enable an Active Directory LDAP user directly from Slack

# Requirements

* [Slack chatops connection](https://insightconnect.help.rapid7.com/docs/configure-slack-for-chatops)
* Active Directory LDAP connection

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

To run the workflow, @ your Slackbot in the channel along with the command `disable-user-ad <username>` or `enable-user-ad <username>`. The workflow will acknowledge the request and reply when it has completed.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Active Directory LDAP|5.2.2|3|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 2.0.0 - Leverage Parameters Feature | Update Active Directory LDAP plugin to version 5.2.2
* 1.1.0 - New functionality - Enable AD User
* 1.0.1 - Update trigger syntax, update documentation, fix naming scheme, add clarity to setup for LDAP search base
* 1.0.0 - Initial workflow

# Links

## References

* [Active Directory LDAP](https://extensions.rapid7.com/extension/active_directory_ldap)
* [Slack](https://slack.com)
