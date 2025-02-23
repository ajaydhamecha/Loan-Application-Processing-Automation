### Overview ###
**Statement**
Developed an RPA bot to automate loan application processing. The bot extracted customer data from emails and validated applications based on predefined criteria such as annual income and loan amount. Valid applications were identified and forwarded for further processing, while exceptions were flagged for manual review. The automation reduced manual effort by 80%, improved accuracy, and expedited loan approvals.

Build on **RE Framework** template of UiPath
Uses *State Machine* layout for the phases of automation project
* Offers high level logging, exception handling and recovery
* Keeps external settings in *Config.xlsx* file and Orchestrator assets
* Pulls credentials from Orchestrator assets and *Windows Credential Manager*
* Gets transaction data Using datarow with excel file and updates back status
* Takes screenshots in case of system exceptions

**The framework is modified to use *DataRows* instead of default orchestrator Queues**

### ⚙️ Setup Instructions ### 
**Prerequisites**
* UiPath Studio installed  
* Excel Application Installed *(as input excel file is of .csv type)*
* Arrange a mail with current date in format dd_MM_yyy in subject and a csv file attachment

**Configure Settings**
* Update *Config.xlsx* with email credentials and loan validation criteria.
* Add Orchestrator *credentials* to the Assets section.

**Execution Details**
* Open the project in UiPath Studio.
* Run the Main.xaml file.

**Error Handling**
*Business Exceptions*: Invalid loan applications are logged and update the reason in csv file.
*System Exceptions*: The bot retries failed transactions before logging the error.

**Output**
A mail with an attached loan data file with an added column of status *(Loan ID, or reason of loan not processed)*
