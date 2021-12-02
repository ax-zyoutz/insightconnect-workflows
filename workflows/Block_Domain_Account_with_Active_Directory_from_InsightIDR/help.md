# Description

Disabling a compromised account can limit the scope of an attack and buy valuable time to investigate and contain the threat. This workflow disables a domain user account from an InsightIDR Brute Force - Domain Account UBA alert.

# Key Features

* **Break the Kill Chain** - Credentials provide attackers with easy access to numerous targets. Disabling a compromised account or forcing a password reset can quickly and effectively interrupt an attacker’s kill chain.
* **Buy Time to Investigate and Remediate** - In a pinch, disabling a user account can limit your threat exposure and buy your team valuable time to investigate and contain a threat. 

# Requirements

* InsightIDR
* Active Directory connection

# Documentation

## Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.

Once the workflow has been imported, **It is recommended that you add you add the appropriate emails to the `Block Domain Account Decision` step so that the appropriate people are alerted that action needs to be taken**

After activation, this workflow is triggered when an InsightIDR Brute Force - Domain Account UBA alert occurs.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Active Directory LDAP|5.2.2|2|
|Rapid7 InsightIDR|3.1.3|2|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 1.0.1 - Update Active Directory LDAP plugin to version 5.2.2 | Update Rapid7 InsightIDR plugin to version 3.1.3
* 1.0.0 - Initial workflow

# Links

## References

* [Active Directory LDAP](https://extensions.rapid7.com/extension/active_directory_ldap)
* [InsightIDR](https://www.rapid7.com/products/insightidr/)
