# Description

This workflow blocks or unblocks a host with Fortinet Firewall via Microsoft Teams command and reports information back to Microsoft Teams.

Sample Microsoft Teams Trigger Commands:

`!block-host 198.51.100.100/32`

`!block-host 198.51.100.0/24`

`!block-host example.com`

`!unblock-host 198.51.100.100/32`

`!unblock-host 198.51.100.0/24`

`!unblock-host example.com`

# Key Features

* Block and unblock hosts 

# Requirements

* [Microsoft Teams](https://insightconnect.help.rapid7.com/docs/microsoft-teams)
* A Fortigate firewall

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

This workflow leverages InsightConnect's Parameters feature. This feature allows variables used multiple times throughout a workflow to be entered once and then referenced throughout the workflow.

There are four parameters you will need to configure in order to complete setup of your workflow:

* Team Name: The Microsoft Teams team name in your environment where the workflow should be triggered and respond
* Channel Name: The Microsoft Teams channel name in your environment where the workflow should be triggered and respond (the channel should exist in the aforementioned team)
* Group Name: The group name for blocked IPv4 addresses and domains
* IPv6 Group Name: The group name for blocked IPv6 addresses

To begin, select "Parameters" either from the Workflow Control Panel or from the Builder to begin configuration.
 
An optional whitelist can be added in the `Create Address Object` step. To use this list add IP addresses or domains in the following format `["198.51.100.100", "example.com", "198.51.100.1"]` and they will not be blocked.

By default, this workflow will automatically skip blocking private IP addresses. To block these, set the `Skip RFC 1918` option to false in the `Create Address Object` step.

After configuring the parameters, activate the workflow in order to trigger it.

### Usage

*This workflow will only trigger in the channel specified in the workflow parameters.*

To run the workflow, send a message to the specified Microsoft Teams channel starting with the command `!block-host` or `!unblock-host`.

The workflow will post status updates in the designated Microsoft Teams channel as it runs.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|HTML|1.2.2|1|
|Fortinet FortiGate|6.0.0|4|
|Microsoft Teams|3.1.5|9|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 2.0.0 - Leverage workflow parameters feature | Update documentation | Update Fortinet FortiGate plugin to version 6.0.0 | Update Microsoft Teams plugin to version 3.1.5
* 1.1.2 - Update Microsoft Teams to version 3.1.0 | Update documentation
* 1.1.1 - Update plugins to latest versions
* 1.1.0 - Update workflow to handle block requests for address that already exists | Update workflow to send Teams message when a job failure has occurred
* 1.0.2 - Help amendments
* 1.0.1 - Update to make Microsoft Teams plugin the latest version
* 1.0.0 - Initial workflow

# Links

## References

* [FortiGate](https://www.fortinet.com/products/next-generation-firewall.html)
* [Microsoft Teams](https://teams.microsoft.com)
