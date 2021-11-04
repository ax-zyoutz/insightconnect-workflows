# Description

This workflow allows for fast quarantine and unquarantine from Microsoft Teams of an asset that has the [Insight Agent](https://docs.rapid7.com/insight-agent/) installed. 

Sample Microsoft Teams Trigger Commands:

`!quarantine-endpoint 198.51.100.100`

`!unquarantine-endpoint 198.51.100.100`

For batches of assets, more than one IP can be specified

`!unquarantine-endpoint 198.51.100.100 198.51.100.101 198.51.100.102`

# Key Features

* Quickly respond to threats by quarantining endpoints from Microsoft Teams
* Reduce the time it takes to contain an endpoint

# Requirements

* [Insight Platform API Key](https://docs.rapid7.com/insight/managing-platform-api-keys/)
* [Microsoft Teams](https://docs.rapid7.com/insightconnect/microsoft-teams/)

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

This workflow leverages InsightConnect's Parameters feature. This feature allows variables used multiple times throughout a workflow to be entered once and then referenced throughout the workflow.

There are two parameters you will need to configure in order to complete setup of your workflow:

* Team Name: The Microsoft Teams team name in your environment where the workflow should be triggered and respond
* Channel Name: The Microsoft Teams channel name in your environment where the workflow should be triggered and respond (the channel should exist in the aforementioned team)

To begin, select "Parameters" either from the Workflow Control Panel or from the Builder to begin configuration.

After configuring the parameters, activate the workflow in order to trigger it.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Microsoft Teams|3.1.3|6|
|Rapid7 Insight Agent|1.0.3|3|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 2.0.0 - Leverage Parameters Feature | Fix issue with the unquarantine action not working | Update Microsoft Teams to version 3.1.3 | Update Rapid7 Insight Agent to version 1.0.3 | Update documentation | Update screenshots
* 1.0.1 - Update Microsoft Teams to version 3.1.0 | Update documentation
* 1.0.0 - Initial workflow

# Links

## References

* [Microsoft Teams](https://docs.rapid7.com/insightconnect/microsoft-teams/)
* [Insight Agent](https://docs.rapid7.com/insight-agent/)
* [Insight Platform API Key](https://docs.rapid7.com/insight/managing-platform-api-keys/)
