Demandware SimpleRelevance Business Manager Extension
=====================================================

SimpleRelevance Business Manager extension provides a functionality to export your store resources such as `Customers`, `Products`, `Orders` to your SimpleRelevance account via [SimpleRelevanc API][1].

###How to install###

Download SimpleRelevance extension zip archive and import it to your instance via Demandware Studio.

Do the following to import the extension into Demandware Studio:
* In Demandware Studio click `File`->`Import`, `General`->`Existing Projects into Workspace` then click `next`.
* In the next window ensure `Select archive file` is checked and click on the `Browse` button on the right.
* Select the archive file containing the integration, then click `Open`->`Finish`.
* If you have an active Demandware server connection the Studio will ask you to link the cartridge to it. Click `Yes`.
* To manually assign and deploy the cartridge to a server connection, right-click on it and then `Properties`. Select `Project References` and check the project containing the integration. The cartridge should be automatically uploaded.

To activate the integration in SiteGenesis, the cartridge has to be assigned to the site and Business Manager:

1. Login to Business Manager and click on `Administration`.
2. Click on `Sites`->`Manage Sites`.
3. Click on the site name followed by the `Settings` tab at the top.
4. In the `Cartridges` text field, add the beginning of the pre-existing text `ext_simplerelevance:`.
5. Go back to `Manage Sites` and click on `Business Manager`.
6. Click the `Settings` tab at the top.
7. In the `Cartridges` text field, add in the beginning of the pre-existing text `ext_simplerelevance:`.
8. Repeat steps 3 and 4 for each `Instance Type` by selecting the appropriate type from the drop-down menu (`Production`, `Staging`, `Sandbox / Development`).


####Verify installation####

Navigate to `Administration`->`Organization`->`Roles & Permissions` 

![Administration Organization Roles Permissions](documentation/document_images/Administration_Organization_Roles_Permissions.png?raw=true "Administration Organization Roles Permissions")
and select `Administrator` user or any other user which has the rights to perform tasks related to the overall administration of the merchant organization and its users and roles. After selecting admin user, Select `Business Manager Modules` tab. From `Select Context:` dropdown select your site instance that you wish to enable SimpleRelevance extension for and click Apply. `SimpleRelevance` module name and *icon* should be there,

![SimpleRelevance In Business Manager Modules](raw/master/documentation/document_images/SimpleRelevance_In_Business_Manager_Modules.png?raw=true "SimpleRelevance In Business Manager Modules")

if you can see it then it means you've installed the extension successfully.


###Usage###
You can use SimpleRelevance Business Manager extension by schedule jobs, where you can define and customize them via Demandware Business Manager.

#####Setup schedule jobs####
Navigate to `Administration`->`Operations`->`Job Schedules`. You can see a list of schedule jobs now. Press `New` button to define new schedule jobs. In schedule job add page, you're on `General` tab by default, To define the job fill the required fields as bellow:
* `Name`: You can input any name for this job. (ex. SimpleRelevace export)
* Check `Enable` in front of `Name` field.
* `Execution Scope`: Select your site instance you wish the job runs for
* `Pipelins`: **ExportResourceForSimpleRelevance**
* `Startnode`: **Start**

![Administration Operations Job Schedules General Tab](raw/master/documentation/document_images/Administration_Operations_Job_Schedules_General_Tab.png?raw=true "Administration Operations Job Schedules General Tab")


The rest of the form is for job schedule date-time settings. Fill them as you like. 
After filling the form press `Apply` button to create/save the schedule job.

#####SimpleRelevance API credentials#####
Extension requires your SimpleRelevance API credentials in other to make API calls. You need to provide these credentials to extension. On schedule job form page select `Parameters` tab and define these two parameters.
* `APIKEY`
* `BusinessName`
As their name, and set the proper values. You can get API key and Business name from you SimpleRelevance account setting page.

![Administration Operations Job Schedules Parameters Tab](raw/master/documentation/document_images/Administration_Operations_Job_Schedules_Parameters_Tab.png?raw=true "Administration Operations Job Schedules Parameters Tab")


#####Schedule jobs notification#####
In order to get notified about SimpleRelevance schedule job result by email you must setup notification feature via Business Manager. To do so, From schedule job form select `Notification` tab, check all the bellow boxes on this page:
* `Enabled`
* `SUCCESS`
* `EXCEPTION`
* `ERROR`
* `HANG`
* `RETRY`

And fill the form fields as bellow:
* `To`: tech@simplerelevance.com
* `CC`: your email address (Optional, if you like to get notified too.)

![Administration Operations Job Schedules Notification Tab](raw/master/documentation/document_images/Administration_Operations_Job_Schedules_Notification_Tab.png?raw=true "Administration Operations Job Schedules Notification Tab")

That's all you need in order to get schedule job notification properly enabled and configured.


####Logging####
SimpleRelevance Business Manager extension comes with logging functionality. Logging help us to find out what our extension does under the hood. We can fix extension bugs and issues so quickly if you have enabled logging for you instance.

#####Enable logging######
Navigate to `Administration`->`Operations`->`Custom Log Settings`. You need to add `SimpleRelevanceLogger` log category to logging levels. In **Warn** section add `SimpleRelevanceLogger` to its log levels. Repeat the same for `Info`, `Debug` category. Remember to enable logging message to File, To do so Press `Log Info To File`, `Log Debug To File`. Finally press `Apply` button to save the settings.

![Administration Operations Custom Log Settings](raw/master/documentation/document_images/Administration_Operations_Custom_Log_Settings.png?raw=true "Administration Operations Custom Log Settings")

[1]: https://www.simplerelevance.com/api_doc/
