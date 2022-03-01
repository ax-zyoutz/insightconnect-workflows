# Description

This workflow blocks or unblocks a host with Fortinet Firewall via Slack command and reports information back to Slack.

Sample Slack Trigger Commands:

`@Rapid7 InsightConnect block-host 198.51.100.100/32`

`@Rapid7 InsightConnect block-host 198.51.100.0/24`

`@Rapid7 InsightConnect block-host example.com`

`@Rapid7 InsightConnect unblock-host 198.51.100.100/32`

`@Rapid7 InsightConnect unblock-host 198.51.100.0/24`

`@Rapid7 InsightConnect unblock-host example.com`

# Key Features

* Block and unblock hosts 

# Requirements

* [Slack](https://insightconnect.help.rapid7.com/docs/configure-slack-for-chatops)
* A Fortigate firewall

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

This workflow leverages InsightConnect's Parameters feature. This feature allows variables used multiple times throughout a workflow to be entered once and then referenced throughout the workflow.

There are three parameters you will need to configure in order to complete setup of your workflow:

* Channel: The Slack channel name in your environment where the workflow should be triggered
* Group Name: The group name for blocked IPv4 addresses and domains
* IPv6 Group Name: The group name for blocked IPv6 addresses

To begin, select "Parameters" either from the Workflow Control Panel or from the Builder to begin configuration.
 
An optional whitelist can be added in the `Create Address Object` step. To add this list add IP's or domains in the following format `["198.51.100.100", "example.com", "198.51.100.1"]` and they will not be blocked.

By default, this workflow will automatically skip blocking private IP addresses, if you’d like to block these as well, set `Skip RFC 1918` option to false in the `Create Address Object` step.

After configuring the parameters, activate the workflow in order to trigger it.

### Usage

*This workflow will only trigger in the channel specified in the workflow parameters.*

To run the workflow, send a message to the specified Slack channel starting with the command `@Rapid7 InsightConnect block-host` or `@Rapid7 InsightConnect unblock-host`.

Your chatbot will reply when the workflow completes.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Fortinet FortiGate|6.0.0|4|


## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 2.0.0 - Leverage workflow parameters feature | Update documentation | Update Fortinet FortiGate plugin to version 6.0.0
* 1.1.1 - Update plugins to latest version
* 1.1.0 - Update workflow to handle block requests for address that already exists | Update workflow to send Slack message when a job failure has occurred
* 1.0.2 - Pass channel name from trigger to all subsequent steps so user only has to configure channel once
* 1.0.1 - Help amendments
* 1.0.0 - Initial workflow

# Links

## References

* [Fortigate](https://www.fortinet.com/products/next-generation-firewall.html)
* [Rapid7 Slack Chatbot](https://insightconnect.help.rapid7.com/docs/configure-slack-for-chatops)
