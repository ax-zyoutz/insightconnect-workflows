# Description

Scan and report on an asset's vulnerabilities and risk posture without leaving your Chat window. Built for patching administrators who may not have access to InsightVM, this workflow fetches the last vulnerability statistics for a given host, triggers a new scan for that host, and returns the updated vulnerability statistics. 

By displaying the last known vulnerability and risk data, the user is able to easily identify any change in vulnerability count or overall risk with the newly collected scan data.

Sample Trigger Commands:

`!scan-asset workstation123`

# Key Features

* Launch a scan of a single asset with a Microsoft Teams message
* Extend single-asset scanning capabilities to users without access to InsightVM
* Receive vulnerability and risk score statistics in Microsoft Teams
* Quickly compare previous vulnerability data with newly collected vulnerability data
* Confirm the effectiveness of patches and remediation actions without leaving Chat

# Requirements

* InsightConnect License
* InsightVM Site ID
* [Microsoft Teams](https://insightconnect.help.rapid7.com/docs/microsoft-teams)

# Documentation

## Readme

This workflow utilizes existing InsightVM (or Nexpose) sites and scan engines to run ad hoc single-asset scans. These ad hoc scans will not skip the scan engine queue. As such, if a scan engine is running a scheduled scan, then the scan triggered by this workflow will be added to the back of the scan engine queue.

This workflow may only scan assets that are in the site's asset scope. As such, administrators should configure the site so that the asset scope is broad enough to be useful for consumers of this workflow. On the other hand, explicitly exclude critical systems from the site scope to prevent unauthorized scanning activity.

## Setup

### InsightVM Setup

This workflow requires a pre-configured InsightVM (or Nexpose) site in order to scan a target. The scan will inherit all configuration settings for this site, and the asset specified must be in the Asset scope for the selected site.

The following guidelines are recommended for use when configuring the site within InsightVM (or Nexpose) for this workflow:

1. **Create New Site** Create a new site in InsightVM. This site will be used solely for this InsightConnect workflow.
2. **Add Assets** Add all possible scan targets. Using Class A, B, or C subnets (eg, 10.1.2.0/24, 10.1.0.0/16, or 10.0.0.0/8) or an asset group (eg, Windows Workstations) is recommended.
3. **Add Authentication** Add scan credentials in order to perform authenticated scans. Authenticated scans yield significantly more accurate results than non-authenticated scans. Administrative credentials are highly recommended for best results.
4. **Select Scan Template** Choose a scan template for the site. The default `Full Audit without Web Spider` is appropriate in most cases.
5. **Select Scan Engine** Select the `Engine most recently used for that asset` option. Also, select the scan engine with the broadest network access from the scan engine list below.
6. **No Scheduled Scans** Given this site likely has an extremely broad scope, it is not recommended that this site be used for regular vulnerability scanning. As such, it is recommended that there be no scheduled scans for the site.

Save the site configuration and navigate to the Site Summary page. View the URL in your web browser to find the `Site ID`. For example, if my console URL is `https://10.1.2.3:3780/site.jsp?siteid=123`, then my `Site ID` is `123`.

Once you have found the site ID, move on to configure the InsightConnect workflow.

### InsightConnect Setup

Import the workflow from the Rapid7 Extension Library and proceed through the Import Workflow wizard in InsightConnect. Import plugins, create or select connections, and rename the workflow as a part of the Import Workflow wizard as necessary.


This workflow leverages InsightConnect's Parameters feature. This feature allows variables used multiple times throughout a workflow to be entered once and then referenced throughout the workflow.
Select "Parameters" either from the Workflow Control Panel or from the Builder to begin configuration.
There are three parameters you will need to configure in order to complete setup of your workflow:

1. `Channel Name` Parameter needs to be provided with your Teams Channel Name.
2. `Team Name` Parameter needs to be provided with your Teams Name.
3. `Site ID` Parameter needs to be provided with your Site ID.

After configuring the parameters, activate the workflow in order to trigger it.
To trigger workflow use command in your Teams environment.

## Technical Details

Plugins utilized by workflow:

|Plugin|Version|Count|
|----|----|--------|
|Microsoft Teams|3.1.3|11|
|HTML|1.2.2|1|
|Rapid7 InsightVM Console|4.9.1|5|
|Type Converter|1.8.0|1|
|Timers|2.0.5|3|

## Troubleshooting

_There is no troubleshooting information at this time_

# Version History

* 1.2.1 - Update keywords
* 1.2.0 - Add workflow parameters | Update Microsoft Teams to version 3.1.3 | Update HTML to version 1.2.2 | Update Rapid7 InsightVM Console to version 4.9.1 | Update Type Converter to version 1.8.0 | Update Timers to version 2.0.5 | Update documentation
* 1.1.0 - Replace the Settings step with automatic team and channel name extraction in all Microsoft Teams steps except the first one | Update Microsoft Teams to version 3.1.0 | Update documentation
* 1.0.0 - Initial workflow

# Links

## References

* [Microsoft Teams](https://teams.microsoft.com)
* [Microsoft Teams Setup](https://insightconnect.help.rapid7.com/docs/microsoft-teams)
