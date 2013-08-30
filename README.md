Demandware SimpleRelevance Business Manager Extension
=====================================================

SimpleRelevance Business Manager extension provides a functionality to export your store resources such as `Customers`, `Products`, `Orders` to your SimpleRelevance account via [SimpleRelevanc API][1].

###How to install###

Download SimpleRelevance extension zip archive and import it to your instance via Business Manager.

####Verify installation####

Navigate to `Administration`->`Organization`->`Roles & Permissions` and select `Administrator` user or any other user which has the rights to perform tasks related to the overall administration of the merchant organization and its users and roles. After selecting admin user, Select `Business Manager Modules` tab. From `Select Context:` dropdown select your site instance that you wish to enable SimpleRelevance extension for and click Apply. `SimpleRelevance` module name and *icon* should be there, if you can see it then it means you've installed the extension successfully.


###Usage###
You can use SimpleRelevance Business Manager extenstion by schedule jobs, where you can define and customize them via Demandware Business Manager.

#####Setup schedule jobs####
Navigate to `Admiistration`->`Operations`->`Job Schedules`. You can see a list of schedule jobs now. Press `New` button to define new schedule jobs. In schedule job add page, you're on `General` tab by default, To define the job fill the required fields as bellow:
* `Name`: You can input any name for this job. (ex. SimpleRelevace export)
* Check `Enable` in front of `Name` field.
* `Execution Scope`: Select your site instance you wish the job runs for
* `Pipelins`: **ExportResourceForSimpleRelevance**
* `Startnode`: **Start**

The rest of the form is for job schedule datetime settings. Fill them as you like. 
After filling the form press `Apply` button to create/save the schedule job.

#####SimpleRelevance API credentials#####
Extension requires your SimpleRelevance API credentials in orther to make API calls. You need to provide these creds to extension. On schedule job form page select `Parameters` tab and define these two parameters.
* `APIKEY`
* `BusinessName`
As their name, and set the proper values. You can get API key and Business name from you SimpleRelevance account setting page.

#####Schedule jobs notification#####
In order to get notifited about SimpleRelevance schedule job result by email you must setup notification feature via Business Manager. To do so, From schedule job form select `Notification` tab, check all the bellow boxes on this page:
* `Enabled`
* `SUCCESS`
* `EXCEPTION`
* `ERROR`
* `HANG`
* `RETRY`

And fill the form fields as bellow:
* `To`: tech@simplerelevance.com
* `CC`: your email address (Optional, if you like to get notofied too.)

That's all you need in order to get schedule job notification propely enabled and configured.


####Logging####
SimpleRelevance Business Manager extension comes with logging functionality. Logging help us to find out what our extension does under the hood. We can fix extension bugs and issues so quickly if you have enabled logging for you instance.

#####Enable logging######
Navigate to `Administration`->`Operations`->`Custom Log Settings`. You need to add `SimpleRelevanceLogger` log category to logging levels. In **Warn** section add `SimpleRelevanceLogger` to its log levels. Repeat the same for `Info`, `Debug` category. Remember to enable logging message to File, To do so Prees `Log Info To File`, `Log Debug To File`. Finally press `Apply` button to save the setings.


[1]: https://www.simplerelevance.com/api_doc/
