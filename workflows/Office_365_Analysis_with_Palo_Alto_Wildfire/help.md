# Description

This workflow is designed to automatically analyze incoming emails to determine if they are malicious. This workflow assumes a user is using their report phishing button to send an email to an administrative account with the suspicious email attached. The workflow will then analyze the attached email for any suspicious links or files. If any malicious indicators are found the email will be remediated across the organization.

# Key Features

* Identifies malicious emails
* Removes identified emails from the entire organization
* Blocks sender from the organization

# Requirements

API and account credentials for

* Microsoft Office365
* Palo Alto Wildfire

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

Once the workflow has been imported, on the workflow overview page, provide values for workflow parameters. Please notice that the **Malicious Email Notification Recipient** parameter accepts a list of email addresses in _JSON format_, for example:

```json
["user1@example.com", "user2@example.com", "user3@example.com"]
```

The remediation steps are disabled due to their destructive nature. To use them, they must be manually enabled after importing the workflow.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|ExtractIt|2.2.1|1|
|Microsoft Office 365 Email|4.0.0|1|
|Microsoft Office 365 Email|5.1.0|1|
|Microsoft Office365 Email Security|2.3.5|2|
|Palo Alto Wildfire|1.2.0|4|
|Sleep|1.0.2|2|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 1.1.0 - Workflow improvements | Support for nested EML attachments
* 1.0.1 - Update workflow title to enrichment
* 1.0.0 - Initial workflow

# Links

## References

* [Microsoft Office365](https://www.office.com)
* [Palo Alto Wildfire](https://www.paloaltonetworks.com/products/secure-the-network/wildfire)