# Description
This workflow provides fast, convenient access to information about a given host from Automox by fetching device details 
from Automox and posting them in a Slack thread. Host information includes hostname, IP addresses, operating system, 
host status, and patch status details. Lookup can be performed by either hostname or IP address.

# Key Features

* Fetch host information from Automox quickly in Slack
* Determine when the system last checked in with the Automox platform
* Quickly identify the number of upcoming patch count along with patch time 
* Positively identify a system by looking up its IP or hostname

# Requirements

* Automox API key
* InsightConnect license
* [Slack](https://docs.rapid7.com/insightconnect/configure-slack-for-chatops/)

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. 
Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

There are two workflow parameters you will need to configure in order to complete setup of your workflow:
* `Automox Organization ID`: The Automox organization used for performing host lookups
* `Slack Channel`: The Slack channel name in your environment where the workflow should be triggered

## Usage

*This workflow will only trigger in the channel specified in the Slack workflow steps.*

To run the workflow, @ your Slackbot in the specific Slack channel along with the command "lookup-host" followed by the IP address or hostname.

For example:

* `@Rapid7 InsightConnect lookup-host hostname1`
* `@Rapid7 InsightConnect lookup-host 127.0.0.1`

The workflow will post responses in a thread of the original message.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Automox|1.1.0|2|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 1.0.0 - Initial workflow

# Links

## References

* [Automox](https://www.automox.com/)
* [Slack](https://www.slack.com)
