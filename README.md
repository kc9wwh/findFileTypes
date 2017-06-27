# findFileTypes
###### Searches the desired system at the searchBase specified for any file of the fileType specified and make them read-only.
___
This script is designed to parse through the **searchBase** specified and look for the specified **fileType**. When a file is found, the permissions are changed to read-only.


Written By: Joshua Roskos | Professional Services Engineer | Jamf

Created On: June 20th, 2017 | Updated On: June 22nd, 2017
___

### Objective

This script was originally created to search through all the /Users/ directories and look for any .olm (Outlook for Mac Archives) and then convert them to read-only.

### Implementation

**Step 1 - Configure the Scripts**

When you open the script you will find some user variables that will need to be defined as specified below:
* Specify *searchBase* on line 53
* Specify *fileType* on line 54

**Step 2 - Upload the Script**

If you are using a management platform such as Jamf Pro you can upload the script and distribute via Policy. Otherwise you can also deploy using Apple's Remote Desktop.

**Step 3 - Create your Policy**

* Policy: findFileTypes - Outlook for Mac Archives
  * Payload - General
    * Display Name: *findFileTypes - Outlook for Mac Archives*
    * Enabled: *Checked*
    * Category: {Your Choice}
    * Trigger(s): *Recurring Check-In*
    * Execution Frequency: *Once per computer (recommended)*
  * Payload - Scripts
    * Scripts: *findFileTypes.py*
  * Scope
    * *Configure to your requirements*

