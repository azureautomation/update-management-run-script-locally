Update Management - Run Script Locally
======================================

            

This script is intended to be run as a part of Update Management Pre/Post scripts. 
This script will run an Azure Automation runbook via a hybrid worker, allowing for local execution of a script. 
It requires a RunAs account and [a hybrid worker](https://docs.microsoft.com/en-us/azure/automation/automation-windows-hrw-install#automated-deployment ) configured on the machine.  Due to a known issue in pre/post deployment scripts where objects and arrays are not able to be passed as parameters, this script can only execute against a single hybrid worker group. You can modify
 the script if you have a well-known list of hybrid workers you wish to execute against per deployment. 

This script takes in the name of another Azure Automation runbook, which will run in the context of the hybrid worker. For example, if you wanted to stop a service, you could publish a new Azure Automation runbook named 'StartMyService'
 that just consists of:


 

 

 


 Start-Service -Name 'Fax'


And pass the name of that Azure Automation runbook into this script, e.g. 'StartMyService' . 


 


 

 

 


        
    
TechNet gallery is retiring! This script was migrated from TechNet script center to GitHub by Microsoft Azure Automation product group. All the Script Center fields like Rating, RatingCount and DownloadCount have been carried over to Github as-is for the migrated scripts only. Note : The Script Center fields will not be applicable for the new repositories created in Github & hence those fields will not show up for new Github repositories.
