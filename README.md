# logCollection
Script to upload client device logs to Jamf Pro

Simple script that can be used via Self Service and/or via Policy to grab logs from a Mac and attach them to the computer record in Jamf Pro. No user interaction is required for this script so it can be run silently behind the scenes if you choose.

![alt text](https://kc9wwh-media.s3.us-east-2.amazonaws.com/logCollection/media/SSDescription.png "Self Service Description")

By default, the following log files are grabbed:
- /var/log/jamf.log
- /var/log/install.log (and all rollovers)
- /var/log/system.log (and all rollovers)

...the logs are then compressed and uploaded to Jamf Pro on the device record under Attachments. 

![alt text](https://kc9wwh-media.s3.us-east-2.amazonaws.com/logCollection/media/LogsOnDeviceRecord.png "Example of Logs Attached to Inventory Record")

I'd recommend using the Jamf Pro Script Variables ($4-$7) to make this more flexible along with [Encrypted Strings](https://github.com/jamf/Encrypted-Script-Parameters), but otherwise its a pretty straight forward setup. 

![alt text](https://kc9wwh-media.s3.us-east-2.amazonaws.com/logCollection/media/ScriptLabels.png "Script Labels")

![alt text](https://kc9wwh-media.s3.us-east-2.amazonaws.com/logCollection/media/ScriptParameters.png "Script Parameters")

**Please Note:** Once you've downloaded the compressed logs from Jamf Pro, you should **delete** them from the inventory record. These attachments live in the database and as always, we want to keep the database as lean and clean as possible. :)

If you have suggestions or questions, please open an issue.

~Josh
