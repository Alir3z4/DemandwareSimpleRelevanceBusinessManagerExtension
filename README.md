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


[1]: https://www.simplerelevance.com/api_doc/
