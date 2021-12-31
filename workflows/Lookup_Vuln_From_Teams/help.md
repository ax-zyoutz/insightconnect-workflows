# Description

This workflow accepts a Microsoft Teams command containing a CVE ID or vulnerability keyword(s), looks up the vulnerability in Rapid7's vulnerability database, and posts the vulnerability details back to the Microsoft Teams channel.

Sample Trigger Commands:

`!lookup-vuln CVE-2020-0674`

`!lookup-vuln printnightmare`

`!lookup-vuln MS08-067`


# Key Features

* Lookup vulnerability information from a designated Microsoft Teams channel
* Find all vulnerabilities that match a search term
* Get solution, severity, description, and publish date information in a Microsoft Teams message

# Requirements

* [Microsoft Teams](https://insightconnect.help.rapid7.com/docs/microsoft-teams)

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

Once the workflow has been imported, set the `Team Name` and `Channel Name` parameters to the Microsoft Teams channel where your workflow may be run from. **Remember to add your Microsoft Teams user to this channel!**

After configuring the Microsoft Teams parameters, activate the workflow in order to trigger it.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Microsoft Teams|3.1.2|5|
|HTML|1.2.2|1|
|Rapid7 Vulnerability & Exploit Database|2.0.3|2|
|Basename|1.1.0|1|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 2.0.1 - Update keywords
* 2.0.0 - Improved workflow logic, added parameters, updated plugins to run on cloud
* 1.1.0 - Replace the Settings step with automatic team and channel name extraction in all Microsoft Teams steps except the first one | Update Microsoft Teams to version 3.1.0 | Update sample trigger commands in description | Update documentation
* 1.0.2 - Fix to correct invalid version of Rapid7 Vulnerability & Exploit Database
* 1.0.1 - Update to make Microsoft Teams plugin the latest version
* 1.0.0 - Initial workflow

# Links

## References

* [Rapid7 Vulnerability Database](https://www.rapid7.com/db)
* [Microsoft Teams](https://teams.microsoft.com)
* [Microsoft Teams Setup](https://insightconnect.help.rapid7.com/docs/microsoft-teams)
