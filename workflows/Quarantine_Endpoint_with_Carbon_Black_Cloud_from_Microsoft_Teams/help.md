# Description

This workflow quarantines or unquarantines endpoints with VMware Carbon Black Cloud via Microsoft Teams command and reports information back to Microsoft Teams.
This workflow supports endpoints in the form of Device IDs, hostnames, or IP addresses.

Sample Slack Trigger Commands:

`!quarantine-endpoint example-host`

`!quarantine-endpoint 198.51.100.100`

`!unquarantine-endpoint 198.51.100.100`

`!unquarantine-endpoint example-host`


# Key Features

* Quarantine endpoints

# Requirements

* [Microsoft Teams](https://insightconnect.help.rapid7.com/docs/microsoft-teams)
* VMware Carbon Black Cloud account with [Automation API Access Settings configured](https://developer.carbonblack.com/reference/carbon-black-cloud/authentication/#creating-an-api-key)

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

Once the workflow has been imported, **the first Microsoft Teams step will need the channel name, and team name updated to suit your Microsoft Teams environment!** Edit the input with the preset text of `change_me` in the first Microsoft Teams step in the workflow.

After configuring the Microsoft Teams steps, activate the workflow in order to trigger it.
 
## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Carbon Black Cloud|1.0.1|2|
|HTML|1.2.1|1|
|Microsoft Teams|3.1.0|5|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 1.1.1 - Update keywords
* 1.1.0 - Replace the preset text of "change_me" with automatic team and channel name extraction in all Microsoft Teams steps except the first one | Update Microsoft Teams to version 3.1.0 | Update documentation
* 1.0.1 - Updated VMware Carbon Black branding
* 1.0.0 - Initial workflow

# Links

## References

* [VMware Carbon Black Cloud](https://www.carbonblack.com/products/vmware-carbon-black-cloud)
* [VMware Carbon Black Cloud plugin](https://extensions.rapid7.com/extension/carbon_black_cloud)
* [Microsoft Teams](https://teams.microsoft.com)
