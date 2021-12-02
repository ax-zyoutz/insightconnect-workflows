# Description

This workflow automated the process of looking up an associated file hash in VirusTotal from an InsightIDR alert. InsightConnect then posts a user response prompt to the security channel in a synopsis of the incident. Based upon the details, the incident responder will either dismiss as a false positive or block the file with VMware Carbon Black EDR. 

# Key Features

* Data enrichment with VirusTotal
* File blacklist on endpoint with VMware Carbon Black EDR

# Requirements

* InsightConnect License
* [Slack](https://insightconnect.help.rapid7.com/docs/configure-slack-for-chatops)
* VMware Carbon Black EDR URL and Account Credentials
* VirusTotal API Key

# Documentation

## Setup

Once the workflow has been imported and the Slack chatbot selected for your workstation, edit the workflow and configure your CB Response connection in the Block Hash step. Also, configure your VirusTotal connection and confirm where applicable. 

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Cb Response|3.1.8|1|
|VirusTotal|7.0.0|2|
|Math|1.2.1|1|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 1.1.0 - Updated VirusTotal plugin | Added Math plugin to support the same artifact outputs
* 1.0.2 - Updated VMware Carbon Black EDR branding
* 1.0.1 - Updated documentation
* 1.0.0 - Initial workflow

# Links

## References

* [CB Response](https://extensions.rapid7.com/extension/carbon_black_response)
* [VirusTotal](https://extensions.rapid7.com/extension/virustotal)
