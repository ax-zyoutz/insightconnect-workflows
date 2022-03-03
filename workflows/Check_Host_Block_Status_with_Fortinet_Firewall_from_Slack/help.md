# Description

This workflow accepts a Slack command containing an IP address. This IP address will be checked against a pre-defined address group in Fortinet to determine if the IP address is present or not. It is assumed that this address group will be used to store IP addresses for a block policy. A message with the results will be returned.

Sample Slack Trigger Commands:

`@Rapid7 InsightConnect block-status 198.51.100.100`

`@Rapid7 InsightConnect block-status example.com`

# Key Features

* The ability to see if an IP is currently blocked by the firewall

# Requirements

* Slack connection
* Admin API key to a Fortinet FortiGate firewall

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

This workflow leverages InsightConnect's Parameters feature. This feature allows variables used multiple times throughout a workflow to be entered once and then referenced throughout the workflow.

There are three parameters you will need to configure in order to complete setup of your workflow:

* Channel: The Slack channel name in your environment where the workflow should be triggered
* Group Name: The group name for blocked IPv4 addresses and domains
* IPv6 Group Name: The group name for blocked IPv6 addresses

To begin, select "Parameters" either from the Workflow Control Panel or from the Builder to begin configuration.

After configuring the parameters, activate the workflow in order to trigger it.

### Usage

*This workflow will only trigger in the channel specified in the workflow parameters.*

To run the workflow, send a message to the specified Slack channel starting with the command `@Rapid7 InsightConnect block-status`.

Your chatbot will reply when the workflow completes.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Fortinet FortiGate|6.0.0|1|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 3.0.0 - Leverage workflow parameters feature | Update documentation | Update Fortinet FortiGate plugin to version 6.0.0
* 2.0.0 - Update workflow to fix issue where addresses were not being correctly parsed | Update to version 5.0.0 of FortiGate
* 1.1.3 - Update Fortinet FortiGate to latest version
* 1.1.2 - Update Fortinet FortiGate to latest version | Added a new message if Fortinet FortiGate action fails
* 1.1.1 - Pass channel name from trigger to all subsequent steps so user only has to configure channel once
* 1.1.0 - Update Fortinet FortiGate to latest version
* 1.0.0 - Initial workflow

# Links

## References

* [Fortinet](https://www.fortinet.com/)
* [Slack](https://slack.com)
