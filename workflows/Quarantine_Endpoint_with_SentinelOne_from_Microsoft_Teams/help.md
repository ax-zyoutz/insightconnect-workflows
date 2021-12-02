# Description

This workflow will quarantine and unquarantine an endpoint in SentinelOne from a Microsoft Teams command. This workflow supports endpoints in the form of Agent IDs, hostnames, MAC addresses, or IP addresses.

Sample Microsoft Teams Trigger Commands:

`!quarantine-endpoint 198.51.100.100`

`!unquarantine-endpoint 198.51.100.100`

Under the "Endpoints" tab from the "Sentinels" page on the main menu in the SentinelOne console, the quarantined endpoint will show "Network status" as "Disabled" after being quarantined.

# Key Features

* Quarantine and unquarantine endpoints

# Requirements

* [Microsoft Teams setup](https://insightconnect.help.rapid7.com/docs/microsoft-teams)
* SentinelOne account with permission to manage endpoints

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

This workflow leverages InsightConnect's Parameters feature. This feature allows variables used multiple times throughout a workflow to be entered once and then referenced throughout the workflow.
Select "Parameters" either from the Workflow Control Panel or from the Builder to begin configuration.
There are two parameters you will need to configure in order to complete setup of your workflow:

1. `Channel Name` Parameter needs to be provided with your Teams Channel Name.
2. `Team Name` Parameter needs to be provided with your Teams Name.

After configuring the parameters, activate the workflow in order to trigger it.
To trigger workflow use command in your Teams environment.
 
## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Microsoft Teams|3.1.4|7|
|SentinelOne|6.2.0|2|
|HTML|1.2.2|1

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 1.2.0 - Update SentinelOne version to 6.2.0 | Update Microsoft Teams plugin version to 3.1.4| Add HTML plugin to strip HTML | Add workflow parameters | Update keywords
* 1.1.0 - Replace the preset text of "change_me" with automatic team and channel name extraction in all Microsoft Teams steps except the first one | Update Microsoft Teams to version 3.1.0 | Update documentation
* 1.0.0 - Initial workflow

# Links

## References

* [SentinelOne](https://www.sentinelone.com/)
* [SentinelOne plugin](https://extensions.rapid7.com/extension/sentinelone)
* [Microsoft Teams](https://teams.microsoft.com)
