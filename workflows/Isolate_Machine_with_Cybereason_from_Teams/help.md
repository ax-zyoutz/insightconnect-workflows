# Description

This workflow allows a user to isolate a machine using Cybereason via a configurable Microsoft Teams command.

Sample Teams Trigger Commands:

`isolate <example_machine>`

# Key Features

* Isolate a machine with Cybereason from Microsoft Teams

# Requirements

* [Microsoft Teams](https://docs.rapid7.com/insightconnect/microsoft-teams)
* Cybereason account

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

Once the workflow has been imported, you must configure the Workflow Parameters for the Microsoft Teams team and the channel the chatops bot should monitor. 

After the workflow parameters have been configured, activate the workflow in order to trigger it.

# Usage

To run the workflow, send a message to the specified Microsoft Teams channel.

Commands should be in the following format:

`isolate <example_machine>`

The workflow will post the results in a thread.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Cybereason|2.0.1|1|
|Microsoft Teams|3.1.4|5|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 1.0.0 - Initial workflow

# Links

## References

* [Cybereason](https://www.cybereason.com/)
* [Microsoft Teams](https://teams.microsoft.com/)
