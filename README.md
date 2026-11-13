# CRM

## Here are the D365 CRM and Power Platform interview questions from your image, with wording corrected:
1. What types of components can we add to a sitemap?
2. How can we control the maximum attachment file size?
3. How can we block specific file extensions for attachments?
4. How can we make a subgrid editable?
5. What is the purpose of Quick Create and Quick View forms?
6. How many types of forms are available in Dynamics 365 CRM?
7. What is the seed value in an autonumber column?
8. What is the purpose of keys in CRM?
9. How can we enable auditing in CRM?
10. How can we enable Relevance Search?
11. How can we include an entity in Relevance Search / Dataverse Search?
12. How can we add a column to search?
13. How can we delete audit history records?
14. What types of components can we add to dashboards?
15. How can we filter child lookup records based on the selected parent lookup value?
16. What is a rollup column, and what is its purpose?
17. How frequently are rollup columns calculated?
18. Can we trigger business rules on rollup columns?
19. What are the limitations of rollup columns?
20. Can we edit the schema name of a table or column?
21. What actions can we perform using business rules?
22. What is the purpose of business rules?
23. What is the difference between Set Field Value and Set Default Value?
24. What are the different scopes of business rules?
25. Which events are available for JavaScript in model-driven apps?
26. How can we implement JavaScript in CRM?
27. How can we make a column read-only using JavaScript?
28. How can we make a column business-required using JavaScript?
29. How can we identify the form type using JavaScript?
30. If a business rule and JavaScript handle the same event, which executes first?
31. How can we display messages to users using JavaScript?
32. Can we use Xrm.Page in JavaScript?
33. Which privileges are available in security roles?
34. What privilege access levels are available in CRM?
35. What is the difference between Append and Append To privileges?
36. What security model does Dynamics 365 CRM use?
37. Which options are available for record-level security?
38. How can we configure access team templates?
39. What is the purpose of field-level security?
40. Which permissions are available in field security profiles?
41. What is hierarchy security, and how can we configure it?
42. What is the purpose of the Principal Object Access (POA) table?
43. How can we enable plug-in trace logs, and which logging options are available?
44. What are the stages of the plug-in execution pipeline?
45. What is the purpose of entity images in plug-ins?
46. Can we register a pre-image for a Create operation?
47. Can we register a post-image for a Delete operation?
48. How can we display a validation error using a plug-in?
49. What syntax is used to save a record using JavaScript?
50. How can we pass formContext to a ribbon button action?
51. How do display rules and enable rules differ?
52. How can we control page visibility in a portal?
53. Where are portal user records stored?
54. How can we enable sign-in on a portal?
55. How can we display plug-in or workflow errors on a portal?
56. Where are portal user records stored? (Repeated in the source.)
57. How can we manage data access for portal users?
58. How can we reset a portal user’s password?
59. What types of Power Automate flows are available?
60. Are Power Automate flows synchronous or asynchronous?
61. How can we manage exceptions in Power Automate flows?
62. How can we process more than 5,000 records in Power Automate?
63. What types of CRM systems are there?
64. What is the difference between Dynamics 365 online and on-premises?
65. What is the file extension for custom report files?
66. How can we retrieve the current record’s details in a report?
Terminology note: Your list uses some older terms: entity is now commonly called table, field is column, and Power Apps portals is now Power Pages.



## Below are answers to your 66 interview questions, with examples and syntax. Start by practising questions 5, 8, 15–16, 20–29, 33–41 and 59–62.

## Use these as explanations you understand and demonstrate—not as claims about projects you haven’t worked on.

1. What components can we add to a sitemap?

A sitemap defines an app’s navigation using areas, groups and subareas. Subareas can link to tables, dashboards, URLs or other supported pages.

Example: Sales area → Customers group → Accounts and Contacts.

2. How do we control attachment size?

Configure Maximum file size for attachments in the environment’s email settings. The classic interface exposes this under System Settings → Email.

Example: Set the limit to 10240 KB for approximately 10 MB. Dataverse file columns have separate size settings. Microsoft Learn

3. How do we block attachment extensions?

Configure the environment’s blocked attachment extensions, traditionally under System Settings → General.

Example:
exe;bat;cmd

This restricts uploads of those file types. Microsoft Learn

4. How do we make a subgrid editable?

Configure the subgrid to use the Power Apps grid control, enable editing, then save and publish.

Example: Allow users to update enquiry priorities directly in the customer’s enquiry subgrid.

The older Editable Grid control is deprecated; use the current Power Apps grid control for new work. Microsoft Learn

5. What are Quick Create and Quick View forms?
Form	Purpose	Example
Quick Create	Create a record with a small set of fields	Create a Contact while working on an Opportunity
Quick View	Display related-record information, generally read-only	Show the selected Account’s phone and address on a Contact form


Remember: Quick Create creates; Quick View displays related information.

6. What form types are available?

The commonly discussed types are:
- Main: Full record interface.
- Quick Create: Simplified creation.
- Quick View: Related-record information.
- Card: Compact record presentation where supported.
Availability varies by table and app experience.

7. What is an autonumber seed?

The seed specifies the starting point for the sequential portion of an autonumber column.

Example: Format ENQ-{SEQNUM:5}, with seed 1000, produces a number such as ENQ-01000.

Autonumber sequences can contain gaps; don’t promise gap-free numbering.

8. What is the purpose of keys?

A primary key uniquely identifies a row using a GUID. An alternate key uniquely identifies a row using business columns.

Example: Make Customer Number an alternate key so an integration can identify customers without knowing their GUIDs.

9. How do we enable auditing?

Enable auditing at three levels:
1. Environment.
2. Table.
3. Required columns.
Example: Audit changes to an Account’s credit limit to identify who changed it and when. Microsoft Learn

10. How do we enable Relevance Search?

The current term is Dataverse Search. Enable it in the environment settings in the Power Platform admin center, then configure searchable tables and columns.

11. How do we include a table in Dataverse Search?

Add the supported table to the search configuration, configure its Quick Find view, and ensure it is included in the relevant model-driven app. Publish and allow indexing time.

12. How do we make a column searchable?

For Dataverse Search, configure the supported column in the table’s Quick Find view → Find columns.

Example: Add Customer Number so searching CUST-1001 finds the customer.

Find columns control search matching; View columns control what is displayed. Microsoft Learn

13. How do we delete audit history?

Use the supported audit management interface or audit deletion APIs, with the appropriate privileges.

Example: Delete audit data outside the organisation’s approved retention period.

Disabling auditing does not delete existing history. Deleted audit history cannot be viewed afterward. Microsoft Learn

14. What can we add to dashboards?

Depending on dashboard type, components include charts, lists, web resources, embedded content and supported Power BI components.

Example: A sales dashboard showing opportunities by stage and a list of overdue activities.

15. How do we filter a child lookup using a parent lookup?

Use related-record filtering when the relationship supports it. For more complex conditions, use JavaScript with addPreSearch and addCustomFilter.

Example: After selecting an Account, the Contact lookup should show only Contacts belonging to that Account.

16. What is a rollup column?

A rollup column aggregates values from related records using functions such as SUM, COUNT, MIN, MAX and AVG.

Example: An Account’s Total Open Opportunity Value sums estimated revenue from its open opportunities.

17. How often are rollups calculated?

They are normally calculated asynchronously:
- Initial mass calculation is scheduled 12 hours after creation or modification by default.
- Incremental calculation has a default minimum recurrence of one hour.
- Users can request recalculation where supported.
Interview point: Rollup values are not automatically real-time. Microsoft Learn

18. Can business rules trigger on rollup columns?

Don’t design business rules around rollup changes. Microsoft documents rollup columns as unsupported in the form business rule designer, and background recalculation does not act like a user changing a form field. Microsoft Learn

19. What are rollup limitations?

Important limitations include:
- Background calculation can leave values temporarily stale.
- They are read-only calculated results.
- Supported relationships, column types and expressions are restricted.
- Manual recalculation has processing limits.
- A rollup cannot simply reference another rollup.
Example: Use a different design when an immediately accurate balance is required during a transaction. Microsoft Learn

20. Can we change a table or column schema name?

After creation, the schema/logical name generally cannot be renamed. The display name can be changed.

Example: Rename the label “Customer Category” to “Customer Segment” while its logical name remains new_customercategory.

If a different schema name is essential, create a replacement and migrate dependencies and data.

21. What actions can business rules perform?

Depending on scope and client support, they can:
- Set or clear values.
- Set default values.
- Change requirement levels.
- Show or hide fields.
- Enable or disable fields.
- Display validation messages and recommendations.
Example: If Customer Type is Business, make Company Name required.

22. Why use business rules?

They implement simple business logic without JavaScript.

Example: Show an explanation field only when an enquiry is rejected.

Use them for straightforward conditions; use code for logic beyond their capabilities.

23. Set Field Value versus Set Default Value?
Action	Behaviour
Set Field Value	Assigns a value when the condition is met and may replace an existing value
Set Default Value	Supplies a value when the target field is empty


Example: Default Country to India, while allowing the user to choose another country.

24. What are business rule scopes?
Scope	Where it applies
Specific form	Selected form
All forms	Supported forms for the table
Entity/Table	Server-side supported logic and supported model-driven forms


Visibility and control actions apply to the form interface, not to server-side data operations. Microsoft Learn

25. What JavaScript events are available?

Common events include:
- Form OnLoad.
- Column OnChange.
- Form OnSave.
- Tab state changes.
- Grid events where supported.
Example: Validate a phone number when the phone column changes.

26. How do we implement JavaScript?

Create a JavaScript web resource, add it as a form library, register the function on an event, and select Pass execution context as first parameter. Save and publish.
function onFormLoad(executionContext) {
    const formContext = executionContext.getFormContext();
    const name = formContext.getAttribute("name")?.getValue();

    console.log(name);
}

Use column logical names, not display labels. formContext is the supported approach for accessing the relevant form. Microsoft Learn

27. How do we make a field read-only?

Disable its control:
function lockAccountName(executionContext) {
    const formContext = executionContext.getFormContext();

    formContext.getControl("name")?.setDisabled(true);
}

This changes the form interface; it does not prevent updates through APIs or other interfaces. Microsoft Learn

28. How do we make a field required?
function requirePhone(executionContext) {
    const formContext = executionContext.getFormContext();

    formContext
        .getAttribute("telephone1")
        ?.setRequiredLevel("required");
}

Accepted values are "required", "recommended" and "none".

Client-side requirement changes do not override server-required constraints. Microsoft Learn

29. How do we identify the form type?
const type = formContext.ui.getFormType();

if (type === 1) {
    // Create form
} else if (type === 2) {
    // Update form
}

Value	Meaning
0	Undefined
1	Create
2	Update
3	Read-only
4	Disabled
6	Bulk edit


These are runtime form modes, different from Main/Quick Create form definitions. Microsoft Learn

30. Which executes first: a business rule or JavaScript?

Avoid giving a universal “always first” answer. Execution depends on the event, business rule scope and registered handlers.

Good interview answer: “I avoid having both mechanisms compete to update the same field. I consolidate related logic and test the actual event sequence.”

JavaScript handlers registered on the same form event can be ordered in the event configuration.

31. How do we display messages using JavaScript?

A form notification:
formContext.ui.setFormNotification(
    "Please review the customer details.",
    "WARNING",
    "customer_review"
);

// Remove it later:
formContext.ui.clearFormNotification("customer_review");

A field validation message:
formContext.getControl("telephone1")
    ?.setNotification("Enter a valid phone number.", "phone_error");

An alert dialog:
Xrm.Navigation.openAlertDialog({
    text: "The request has been submitted."
});

Form notifications support INFO, WARNING and ERROR. A form notification alone does not block saving. Microsoft Learn

32. Can we use Xrm.Page?

It is deprecated, though retained for backward compatibility in existing scenarios. For new form scripts use:
const formContext = executionContext.getFormContext();

For organisation/user context use:
const globalContext = Xrm.Utility.getGlobalContext();

Deprecation does not mean every existing script immediately stops working. Microsoft Learn

33. Which privileges exist in security roles?

The eight standard table privileges are:
Privilege	Meaning
Create	Add records
Read	View records
Write	Update records
Delete	Remove records
Append	Associate this record with another
Append To	Allow another record to be associated with this record
Assign	Change ownership
Share	Grant record access


Security roles also contain other privileges, such as administrative and export capabilities. Microsoft Learn

34. What privilege access levels are available?

For user/team-owned tables, common levels are:
- User/Basic: Accessible records at user level.
- Business Unit/Local: Records within the applicable business unit.
- Parent:Child Business Units/Deep: Applicable business unit and descendants.
- Organisation/Global: Across the environment.
- None: Privilege not granted.
Example: A salesperson reads their own opportunities; a sales manager reads their business unit’s opportunities. Microsoft Learn

35. Append versus Append To?

When associating a Contact with an Account:
- Append on Contact: Permits attaching the Contact to another record.
- Append To on Account: Permits the Account to receive the association.
Read access and other operation-specific permissions may also be required.

Remember: Append = record being attached; Append To = record receiving the attachment. Microsoft Learn

36. What security model does CRM use?

Dataverse combines role-based security, business units, ownership, teams, sharing, hierarchy access and column security.

Permissions from multiple roles are generally cumulative.

Example: A salesperson role grants customer access, while an additional role grants export permissions. Microsoft Learn

37. What provides record-level security?

Record access can come through:
- Ownership.
- Security role access levels.
- Owner/group teams.
- Sharing and access teams.
- Hierarchy security, when configured.
Example: Share one opportunity with a specialist without granting access to every opportunity. Microsoft Learn

38. How do we configure access team templates?

Enable access teams for the table, create a template defining the table and access rights, and configure the form’s access team subgrid.

Example: An Opportunity Collaboration team template grants Read and Write access to a particular opportunity.

An access team grants record access; it does not own the record or carry security roles.

39. What is field-level security?

It restricts access to eligible sensitive columns independently of normal record access.

Example: A user can read an employee record but cannot view its salary column.

Enable column security and assign the appropriate column security profile.

40. Which permissions exist in field security profiles?

The traditional permissions are Read, Create and Update.

Example: HR can read and update Salary; a recruiter can create a value but cannot subsequently read it.

Current column security can also involve masking-related capabilities. Explain the permissions relevant to the configured environment.

41. What is hierarchy security?

It extends record access using either:
- Manager hierarchy: Based on manager relationships.
- Position hierarchy: Based on configured positions.
Configure the hierarchy model, depth and applicable tables.

Example: A manager receives access to qualifying subordinate-owned records. It does not automatically bypass column security or every other security requirement. download.microsoft.com

42. What is the POA table?

PrincipalObjectAccess stores record access information associated with principals—users or teams—particularly sharing and inherited sharing.

Example: Sharing an Account with another user can create access represented through POA.

It does not contain every permission granted by security roles. Avoid unsupported direct modifications.

43. How do we enable plug-in tracing?

Configure plug-in trace logging in the environment settings. The options are:
Option	Behaviour
Off	No plug-in trace logging
Exception	Retain traces for exceptions
All	Retain traces for all executions


Use ITracingService in code:
var tracing = (ITracingService)serviceProvider.GetService(
    typeof(ITracingService));

tracing.Trace("Customer validation started.");

Use detailed logging temporarily when troubleshooting and review storage impact.

44. What are the plug-in pipeline stages?
Stage	Number	Typical use
PreValidation	10	Reject an invalid operation early
PreOperation	20	Modify incoming data before the core operation
MainOperation	30	Platform core operation
PostOperation	40	Process results after the core operation


Ordinary custom plug-ins register on stages 10, 20 or 40. PreOperation and synchronous PostOperation participate in the transaction; asynchronous PostOperation runs afterward.

Example: Populate a normalised customer reference in PreOperation. Microsoft Learn

45. What are plug-in entity images?

Images are snapshots of selected columns:
- Pre-image: Before the core operation.
- Post-image: After the core operation.
Example: Compare the previous credit limit with the updated limit.
if (context.PreEntityImages.TryGetValue("PreImage", out var preImage))
{
    var oldName = preImage.GetAttributeValue<string>("name");
}

Configure the image alias and required columns during step registration.

46. Can Create have a pre-image?

No. The record does not exist before creation. A supported PostOperation Create step can have a post-image.

47. Can Delete have a post-image?

No. The record no longer exists after deletion. Use a pre-image to access its previous values.

For Update, supported PostOperation steps can provide both images. Microsoft Learn

48. How do we show a plug-in validation error?

Throw InvalidPluginExecutionException from synchronous validation logic.
if (creditLimit < 0)
{
    throw new InvalidPluginExecutionException(
        "Credit limit cannot be negative.");
}

A synchronous exception can reject the operation. An asynchronous plug-in cannot return an immediate form validation error to the original user.

49. How do we save a record using JavaScript?
async function saveRecord(executionContext) {
    const formContext = executionContext.getFormContext();

    try {
        await formContext.data.save();
    } catch (error) {
        await Xrm.Navigation.openAlertDialog({
            text: error.message
        });
    }
}

Avoid creating a save loop by calling this indiscriminately from an OnSave handler.

50. How do we pass formContext to a ribbon action?

For a classic form ribbon command, pass PrimaryControl as a CRM parameter. The function receives the form context directly:
function onButtonClick(primaryControl) {
    const formContext = primaryControl;
    const recordId = formContext.data.entity.getId();
}

Unlike a normal form event, do not assume this parameter is an execution context requiring getFormContext().

51. Display rules versus enable rules?
Rule	Purpose
Display rule	Determines whether a command is displayed
Enable rule	Determines whether an available command is enabled


Example: Show Approve only in the relevant context; enable it only when status is Pending.

The exact visual behaviour can depend on the command bar experience.

52. How do we control Power Pages page visibility?

Use page permissions associated with web roles.

Example: Restrict the Customer Dashboard page to authenticated customers.

Hiding a navigation link alone does not secure the page.

53. Where are Power Pages users stored?

Site users are represented by Dataverse Contact records. External identity information links the Contact to its authentication provider.

These users are different from internal Dataverse systemuser records.

54. How do we enable portal sign-in?

Configure an authentication provider in Power Pages, such as Microsoft Entra External ID, then configure registration/sign-in settings and test the identity-to-contact association.

Authentication establishes who the user is; web roles and permissions determine access. Microsoft Learn

55. How do we display plug-in/workflow errors on Power Pages?

For custom plug-in errors, configure the site setting:
Site/EnableCustomPluginError = true

Return an appropriate synchronous plug-in exception. For diagnostics, use supported error logging/custom-error settings in a controlled environment.

An asynchronous workflow failure will not automatically appear as an immediate form error. Avoid exposing technical stack traces to public users. Microsoft Learn

56. Where are portal user records stored?

This repeats question 53: Dataverse Contact records, linked to their authentication identities.

57. How do we manage portal data access?

Configure table permissions, associate them with web roles, and assign the roles to the appropriate Contacts.

Example: Contact-scoped permission lets a customer view only enquiries related to their Contact record.

Page permissions protect pages; table permissions protect Dataverse data. Microsoft Learn

58. How do we reset a portal user’s password?

It depends on authentication:
- External provider: Use the provider’s password-reset process.
- Local authentication: Use the site’s configured local-account reset process.
Example: An Entra External ID user resets their password through that provider, rather than by changing an ordinary Contact field.

59. What Power Automate flow types exist?
Type	Trigger/example
Automated cloud flow	A Dataverse enquiry is created
Instant cloud flow	User selects a button
Scheduled cloud flow	Run every morning
Desktop flow	Automate desktop application tasks


Business process flows guide users through stages in model-driven apps; they are different from background cloud automation. Microsoft Learn

60. Are Power Automate flows synchronous or asynchronous?

Dataverse-triggered cloud flows run asynchronously, outside the originating database transaction.

Example: Saving an enquiry triggers an email flow afterward. An email failure does not normally roll back the enquiry save.

Some calling patterns wait for a flow response, but that does not make the flow a transactional synchronous Dataverse plug-in.

61. How do we handle flow exceptions?

Use Scopes, Configure run after, suitable retry policies and logging.
Scope	Purpose
Try	Main actions
Catch	Run after Try fails or times out
Finally	Run after the outcomes you configure


Example: If creating a record fails, log the error and notify support.

An expression inside the Catch path can inspect a scope’s action results:
result('Try')

Retry transient errors, rather than repeatedly retrying invalid data. Microsoft Learn

62. How do we retrieve more than 5,000 records?

For the standard Dataverse List rows approach, enable Pagination in the action settings and set a suitable threshold.

Example: To retrieve about 12,000 matching rows, set a threshold above that number, subject to supported limits.

Also:
- Filter rows at the source.
- Select only required columns.
- Use paging/batches for larger workloads.
- Handle throttling and retries.
The documented configurable pagination threshold is up to 100,000. FetchXML queries require attention to their own paging behaviour; don’t assume the same pagination switch handles every query mode. Microsoft Learn

63. What types of CRM are there?

If the interviewer means business categories:
Category	Focus
Operational CRM	Sales, marketing and service processes
Analytical CRM	Customer insights and analysis
Collaborative CRM	Sharing customer information across teams/channels


If they mean deployment, discuss cloud versus on-premises. Clarify the question first.

64. Dynamics 365 online versus on-premises?
Area	Online/cloud	On-premises
Hosting	Microsoft-managed service	Organisation-managed infrastructure
Maintenance	Platform service maintained by Microsoft	Organisation manages applicable infrastructure and upgrades
Direct database access	No supported direct write access to the service database	Database administration access exists, but direct application-table writes remain unsupported
Capabilities	Cloud integrations and service capabilities	Features depend on the installed product/version


Interview point: Check feature parity and support requirements rather than assuming both deployments have identical capabilities.

65. What is the custom report file extension?

For an SSRS report, the extension is:
.rdl

It means Report Definition Language.

For comparison, a Power BI Desktop report uses .pbix; that is a different report technology.

66. How do we retrieve the current record in a report?

For a Dynamics SSRS/FetchXML report, configure record-context prefiltering and the report’s table/context settings.

Example FetchXML configuration:
<fetch>
  <entity name="account"
          enableprefiltering="1"
          prefilterparametername="CRM_FilteredAccount">
    <attribute name="accountid" />
    <attribute name="name" />
  </entity>
</fetch>
