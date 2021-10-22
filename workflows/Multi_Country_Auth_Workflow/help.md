# Description

This workflow accepts an InsightIDR User Behavior Analytics Alert (UBA) when a member of a certain user group is logged in from two or more countries. It uses a human decision step to send a templated email to a secure mailbox with the report.
Indicators supported in this workflow are IP addresses.

# Key Features

* The ability to determine if a member of a certain user group is logged in from two or more countries

# Requirements

* [InsightIDR User Behavior Analytics Alert](https://docs.rapid7.com/insightidr/alerts)
* Access to InsightIDR

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

This workflow leverages InsightConnect's Parameters feature. This feature allows variables used multiple times throughout a workflow to be entered once and then referenced throughout the workflow.

There are two parameters you will need to configure in order to complete setup of your workflow:

* Email Recipient: Recipient for email alert
* Required AD Group DN: Active Directory user group to monitor

To begin, select "Parameters" either from the Workflow Control Panel or from the Builder to begin configuration.

After configuring the parameters, activate the workflow in order to trigger it.

 
## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|IPStack|2.0.0|1|
|Type Converter|1.8.1|1|
|Active Directory LDAP|5.3.1|1|
|Microsoft Exchange|6.1.3|1|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 1.0.0 - Initial workflow

# Links

## References

* [Active Directory LDAP Plugin](https://extensions.rapid7.com/extension/active-directory-ldap)
* [IPStack Plugin](https://extensions.rapid7.com/extension/ipstack)
* [Microsoft Exchange Plugin](https://extensions.rapid7.com/extension/microsoft-exchange)
* [Type Converter Plugin](https://extensions.rapid7.com/extension/type-converter)