# Description

Use the simplicity of a chat command in Microsoft Teams to block indicators such as IPv4 and IPv6 address, MD5 and SHA256 hashes, and domains in CrowdStrike Falcon.

Multiple indicators can be specified within one command.

Sample Teams Trigger Commands:

`!block-indicators 198.51.100.100 bd3b8dbb50fbd58e1bc2cc82effb9d81a2ea0aa6be235ff58ec7eb997deea1ab`

`!block-indicators 198.51.100.100 example.com 2001:db8:8:4::2`

`!block-indicators 9de5069c5afe602b2ea0a04b66beb2c0`

# Key Features

* **Block an Indicator** - Use Microsoft Teams and InsightConnect to make indicator blocks easy. 

# Requirements

* [Microsoft Teams](https://docs.rapid7.com/insightconnect/microsoft-teams)
* CrowdStrike Falcon Client Secret and Client ID

# Documentation

## Setup

The workflow works by adding indicators in your CrowdStrike Falcon.

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

This workflow leverages InsightConnect's Parameters feature. This feature allows variables used multiple times throughout a workflow to be entered once and then referenced throughout the workflow. 

There are two parameters you will need to configure in order to complete setup of your workflow:

* Teams Channel - enter the Teams channel name matching your environment ex: `channelname`
* Teams Team - enter the Teams team name matching your environment ex: `teamname`

To begin, select "Parameters" either from the Workflow Control Panel or from the Builder to begin configuration.

After configuring the parameters, activate the workflow in order to trigger it.

### Usage

*This workflow will only trigger in the channel specified in the Microsoft Teams parameters.*

For example:
* `!block-indicators 198.51.100.100`

The workflow will reply when it completes.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|CrowdStrike Falcon|3.1.0|1|
|Microsoft Teams|3.1.4|6|
|Type Converter|1.8.1|1|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 1.0.0 - Initial workflow

# Links

## References

* [CrowdStrike](https://www.crowdstrike.com/)
* [CrowdStrike Falcon API](https://falcon.crowdstrike.com/support/documentation)
* [Microsoft Teams](https://teams.microsoft.com/)
