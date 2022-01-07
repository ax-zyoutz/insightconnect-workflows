# Description

This workflow enriches an IDR alert by performing a lookup on all domains, hashes, URLs and IPs in the investigation with Rapid7 IntSights.

# Key Features

* Perform a domain, hash, URL and IP lookup automatically from any IDR alert

# Requirements

* InsightConnect License
* Rapid7 IntSights API Key and Account Credentials

# Documentation

## Setup

* Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.
* Configure the connection for the Rapid7 IntSights plugin
* Activate your workflow
* Navigate to IDR's alert triggers page at #/automation/alerts
* Click Create Alert Trigger
* Select Enrich Indicators with Rapid7 IntSights from IDR Alert
* While Selecting Alerts, check any alerts you would like to automatically enrich

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Rapid7 IntSights|2.0.0|4|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 2.0.0 - Update workflow to use IntSights plugin version 2.0.0
* 1.0.0 - Initial workflow

# Links

## References

* [Rapid7 IntSights](https://intsights.com/)

