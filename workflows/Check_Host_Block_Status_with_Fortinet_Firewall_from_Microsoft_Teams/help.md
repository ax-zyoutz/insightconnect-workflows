# Description

This workflow accepts a Microsoft Teams command containing an IP address. This IP address will be checked against a pre-defined address group in Fortinet to determine whether or not the IP address is present. It is assumed that this address group will be used to store IP addresses for a block policy. A message with the results will be returned.

Sample Microsoft Teams Trigger Commands:

`!block-status 198.51.100.100`

`!block-status example.com`

# Key Features

* The ability to see if an IP address is currently blocked by the firewall

# Requirements

* Microsoft Teams connection
* Admin API key to a Fortinet FortiGate firewall

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

After configuring the parameters, activate the workflow in order to trigger it.

### Usage

*This workflow will only trigger in the channel specified in the workflow parameters.*

To run the workflow, send a message to the specified Microsoft Teams channel starting with the command `!block-status`.

The workflow will post status updates in the designated Microsoft Teams channel as it runs.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Fortinet FortiGate|6.0.0|1|
|HTML|1.2.2|1|
|Microsoft Teams|3.1.5|4|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 2.0.0 - Leverage workflow parameters feature | Update documentation | Update Fortinet FortiGate plugin to version 6.0.0 | Update Microsoft Teams plugin to version 3.1.5
* 1.2.0 - Replace the preset text of "change_me" with automatic team and channel name extraction in all Microsoft Teams steps except the first one | Update Microsoft Teams to version 3.1.0 | Update documentation
* 1.1.3 - Update Fortinet FortiGate, Microsoft Teams, and HTML plugins to latest versions
* 1.1.2 - Update Fortinet FortiGate and Microsoft Teams plugins to the latest versions | Added a new message if Fortinet FortiGate action fails
* 1.1.1 - Update to make Microsoft Teams plugin the latest version
* 1.1.0 - Update Fortinet FortiGate to latest version
* 1.0.0 - Initial workflow

# Links

## References

* [Fortinet](https://www.fortinet.com/)
* [Microsoft Teams](https://teams.microsoft.com)
