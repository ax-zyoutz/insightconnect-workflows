# Description

This workflow delivers InsightIDR alerts to the appropriate Microsoft Teams channel based on whether the user involved in the alert belongs to the specified Active Directory group. If the user belongs to the specified Active Directory group, a message with information about the alert is sent to the specified Microsoft Teams channel for "critical" severity alerts. If the user does not belong to the group or none of the users is involved in the alert, the message is sent to the channel intended for "normal" severity alerts.

# Key Features

* Deliver InsightIDR alerts to the appropriate Microsoft Teams channel based on the user involved in the alert
* Sort between critical and non-critical events based on the users involved

# Requirements

* [Microsoft Teams](https://insightconnect.help.rapid7.com/docs/microsoft-teams)
* [Microsoft Active Directory](https://extensions.rapid7.com/extension/active_directory_ldap)
* [Universal Webhook Data Exporter](https://docs.rapid7.com/insightidr/webhook)

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

This workflow leverages InsightConnect's Parameters feature. This feature allows variables used multiple times throughout a workflow to be entered once and then referenced throughout the workflow.

There are five parameters you will need to configure in order to complete setup of your workflow:

* **Team Name**: The Microsoft Teams team name in your environment where the workflow should be triggered and respond
* **Channel Name - Normal Severity**: The Microsoft Teams channel name in your environment where the workflow should be triggered and respond (the channel should exist in the aforementioned team) for normal severity alerts
* **Channel Name - Critical Severity**: The Microsoft Teams channel name in your environment where the workflow should be triggered and respond (the channel should exist in the aforementioned team) for critical severity alerts
* **Search Base**: The search base for group membership query. For example, `DC=example,DC=com`
* **Group Name**: The Active Directory group name. For example, `Domain Admins`.

To begin, select "Parameters" either from the Workflow Control Panel or from the Builder to begin configuration.

The last step is to configure the Universal Webhook data exporter that will send the alert information from your collector that hosts the data exporter to the URL configured in the data exporter. To configure your data exporter you need to follow these steps:

1. From your InsightIDR dashboard, select Data Collection on the left hand menu. 
2. When the Data Collection page appears, click the Setup Event Source dropdown and choose Add Event Source.
3. From the "Security Data" section, click the Data Exporter icon. The "Add Event Source" panel appears.
4. Choose your collector. Select the `Universal Webhook` as event source type and name your event source.
5. Provide the `Trigger URL` from the workflow API trigger as `URL`. Add `Secret` if not already provided.
6. Make sure `Alerts` is selected under "Data Export Types" and click "Save". 

After configuring the parameters and data exporter, activate the workflow in order to trigger it.

### Usage

The workflow will be triggered upon receiving an alert information from the data exporter and a message will be sent to one of the specified Microsoft Teams channels depending on whether the user involved in the alert belongs to the specified Active Directory group or not.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Microsoft Teams|3.1.2|2|
|Active Directory LDAP|5.2.2|1|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 1.0.0 - Initial workflow

# Links

## References

* [Microsoft Teams](https://teams.microsoft.com)
* [Active Directory LDAP](https://extensions.rapid7.com/extension/active_directory_ldap)
* [Universal Webhook Data Exporter](https://docs.rapid7.com/insightidr/webhook)
