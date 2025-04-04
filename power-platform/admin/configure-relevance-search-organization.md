---
title: Configure Dataverse search for your environment
description: Configure Dataverse search for your environment to improve search results and performance in model-driven apps. 
author: marianaraujo 
ms.component: pa-admin
ms.topic: get-started
ms.date: 04/03/2025
ms.subservice: admin
ms.author: maaraujo
ms.reviewer: EllenWehrle
search.audienceType: 
  - admin
contributors:
- wobushixinxin67

---
# Configure Dataverse search for your environment

[!INCLUDE[new-PPAC-banner](~/includes/new-PPAC-banner.md)]

Dataverse search delivers fast and comprehensive search results across multiple tables in a single list, sorted by [relevance](/azure/search/index-similarity-and-scoring), to give you an easy and well-informed search experience in model-driven apps. As an administrator with environment-level permissions, you can go to the [Power Platform admin center](/power-platform/admin/new-admin-center) to configure Dataverse search for all the model-driven apps within a specific environment using Quick Find views to manage global, quick find, and lookup search behavior.

With Dataverse search enabled, a search box is always available at the top of every page in all the model-driven apps in the environment. The search box allows you to start a new search and quickly find the information you're looking for from the searchable tables included in the app. With Dataverse search enabled, it's the default, and only, global search experience in all model-driven apps in the environment—you can't disable Dataverse search per app and users can't switch to [quick find search](/powerapps/user/quick-find), formerly known as categorized search.  

[Dataverse search can be extended to other Microsoft Search canvases](/microsoftsearch/manage-dynamics365), including SharePoint Online, Bing, and Office. With a connector enabled, you can search for and find information from the selected canvas as if you are searching in the app. For example, you can quickly look up a contact's phone number or email address without opening the app.

## Learn about the benefits of Dataverse search

Dataverse search helps you quickly find what you are looking for in model-driven apps. As part of its search capabilities, indexed data is used across generative AI experiences&mdash;such as Copilot experiences&mdash;to fetch records and use them as answers. Dataverse search is how Microsoft allows rich search and AI-powered experiences across different products that use Dataverse as one of the data sources, subject to Copilot feature availability.

Dataverse search has these benefits:

- **Fast and accurate search**. Provides a precise and quick search experience for model-driven apps, and performance that's superior to [categorized search](/power-apps/user/quick-find#multiple-table-quick-find-categorized-search).

- **Generative AI experiences**. Provides generative AI-powered search and work experiences using Copilot when Dataverse tables and files are uploaded in Microsoft Copilot Studio,

> [!NOTE]
> Searching across images isn't supported.

- **Suggested results as you type**. Finds what you're looking for and shows you the top results, as you type.

- **Better matching**. Finds matches to any word in the search term for columns in a table. Provides a better user experience compared to [quick find](/power-apps/user/quick-find) search, where all words in the search term must be found in one column.

- **Smart**. Finds matches that include inflectional words such as **stream**, **streaming**, or **streamed**.

- **Search activities**. Search includes notes and attachments in activities.

- **Understanding of underlying data**. Understands data types like **Choice** and **Lookup**, so it can effectively interpret a search query that includes multiple search terms.

- **Operators for advanced search**. Lets you use simple Boolean operators in your search term and craft the query to get the results you want.

- **Intelligence**. Applies AI technology to interpret natural language such as misspellings, common abbreviations, and synonyms to deliver quality results.
  
- **Search across documents in Microsoft Dataverse**. Search for and find information contained in PDF, Microsoft Office document, HTML, XML, ZIP, EML, plain text, and JSON file formats. It also searches text in notes and attachments.
  
For more information about Dataverse search, see [Search for tables and rows by using Dataverse search](/powerapps/user/relevance-search).

### Dataverse search composition

Dataverse search consists of two separate indexes that power different experiences:

- **Dataverse search structured index** is the index powering experiences across structured or tabular data stored in Dataverse. Examples of this index include search indexes over tables Dataverse like Accounts, Contact, custom tables, Dataverse relevance search, and others.
- **Dataverse search unstructured index** is the index powering experiences across unstructured data stored in Dataverse. Examples of this index include search indexes over files uploaded in Microsoft Copilot Studio custom agents, customer service agents, and others.

### Availability and language support

- Dataverse search is available in customer engagement apps such as Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation.

- Dataverse search isn't available for Customer Engagement (on-premises) organizations. Quick Find is the only search option for (on-premises) customer engagement apps organizations and Customer Engagement (on-premises) organizations.

- Full-text Quick Find is available for Customer Engagement (on-premises) organizations, starting with Dynamics CRM 2015 Update Rollup 1.

- For a more detailed comparison of the searches available in Microsoft Dataverse, go to [Compare search options in Microsoft Dataverse](/powerapps/user/search).

- All searchable fields in Dataverse search are processed in the language most closely matching the organization's base language, except Kazakh where all fields are processed using a basic, language-agnostic text processor.

## Enable Dataverse search

Dataverse search is an opt-out feature, set to **On** for all new production environments or **Default** for all other new environment types by default. We recommend turning on Dataverse search so users have a superior search experience in model-driven apps, and to allow generative AI-powered experiences like Copilot.

- When set to **On**, you see the search bar in the header of all model-driven apps in the environment enabling your users to have a global-search experience and enjoy the benefits of searching and working with AI.
- When set to **Default**, you don't see the search bar in the header of all model-driven apps in the environment. However, generative-AI experiences using Dataverse data remain available.
- When set to **Off**, you don't see the search bar in the header of all model-driven apps in the environment and generative-AI experiences using Dataverse data are limited.

Note: The enablement of these AI experiences can occur via the following methods:

- Turning on the Copilot feature in Power Platform admin center
- Adding a Dataverse table or uploading a File onto a Microsoft Copilot Studio agent
- Creating a Microsoft Copilot Studio skill
- Prompting a Microsoft Copilot Studio agent requiring files or Dataverse knowledge

Dataverse search storage consumption is only reported when there is indexed data.

Individual users aren't able to switch to [Quick Find search, formerly known as categorized search](/powerapps/user/quick-find). Tables must be included in the application you're using with Dataverse search. Be sure that any table you want users to search on are included in your application.

> [!IMPORTANT]
> Dataverse search is automatically allowed (turned **On**) to ensure business continuity if you already use Dataverse search or any of the related AI-powered experiences. If you're using your own encryption key, you can turn off Dataverse search after enabling early access of 2021 release wave 2 in the [Power Platform admin center](https://admin.powerplatform.microsoft.com/).
> Dataverse search is set to **Default** if you aren't currently using Dataverse search or any of the related AI-powered experiences. When set to default, you only trigger data indexing when you turn on the Copilot setting, create a Microsoft Copilot Studio skill, or upload a Dataverse table or a file to an agent.

:::image type="content" source="media/model-app1.png" alt-text="The image shows first sample model-driven app.":::

:::image type="content" source="media/model-app2.png" alt-text="The image shows second sample model-driven app.":::

> [!NOTE]
> Dataverse search doesn't support lifecycle operations such as create, delete, backup, recover, copy, and reset. In the event of such an operation, be sure to turn on Dataverse search again.

Take these steps to turn on Dataverse search:

1. Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/) as a system administrator.

2. Select **Manage**.

3. Select an environment.

4. Select **Settings** > **Product** > **Features**.

5. Under **Dataverse search**, set **Dataverse search** to **On**.

6. Select **Save**.

   :::image type="content" source="media/ppac-dataverse-search3.png" alt-text="This image shows Dataverse search set to On.":::

Turning on Dataverse search enables global-search and generative-AI experiences in all of your model-driven apps within that environment. You can't turn it off in specific apps.

When you provision a Dataverse search index, an indication that provisioning is in progress is visible. Once index provisioning is complete, it may take anywhere between an hour or more to complete a full sync for average size organizations, to a couple of days for large organizations.

> [!IMPORTANT]
> Turning off Dataverse search deprovisions and removes the index within a period of 12 hours. If you turn on Dataverse search after its been off for 12 hours, it provisions a fresh index that needs to go through a full sync. Syncing may take up to an hour or more for average size organizations, and a couple of days for large organizations. Be sure to consider these implications when you turn off Dataverse search temporarily.

## Help improve Dataverse search

Share your environment's Dataverse search queries in Dynamics 365 and Power Platform applications with Microsoft to help Microsoft improve Dataverse search. This data helps Microsoft build, improve, and validate the Microsoft machine learning model for the Dynamics 365 Natural Language search query technology.

People using secured computers in the United States review your queries and results. Aggregate data about queries and results are used by Microsoft engineers and data scientists to improve future search query results for all users worldwide. Your data remains your property. Your organization's data is stored within your tenant's compliance boundary and is automatically deleted after 30 days. You can delete the data at any time by navigating to the Power Platform admin center and toggling the **Share anonymized search analytics with Microsoft** option to **Off**. For more information, go to **Terms of Service** in the Power Platform admin center.

The **Share anonymized search analytics with Microsoft** option is **Off**, by default. To turn it on:

1. Sign in to [Power Platform admin center](https://admin.powerplatform.microsoft.com/), select an _environment_.

2. Select **Settings** > **Product** > **Features**.

3. Under **Search**, set **Share anonymized search analytics with Microsoft** to **On**.

4. Select **Save**

   :::image type="content" source="media/ppac-dataverse-search2.png" alt-text="Set Share anonymized search analytics with Microsoft to On.":::

## Set up Dataverse search

Setting up Dataverse search after turning it on in the Power Platform admin center involves four steps:

1. Select the _searchable tables_ for Dataverse search.

2. Review the columns that will be searched, the columns that will be displayed, and the filter conditions that will be applied in model-driven Power Apps as detailed in the [_Select searchable fields and filters for each table_](#select-searchable-fields-and-filters-for-each-table) section.

3. Be sure to include the tables allowed for Dataverse search in the model-driven app. Use the app designer to verify table inclusion in an app's components. For more information, go to [Add or edit model-driven app components](/powerapps/maker/model-driven-apps/add-edit-app-components#add-a-component).

4. Make sure your table is customizable and that the settings to **Track changes** and **Appear in search results** in the **Advanced options** area are both set to **On**. For more information, go to [Create and edit tables using Power Apps](/power-apps/maker/data-platform/create-edit-entities-portal?tabs=excel).

### Select tables for Dataverse search

Setting up search starts with reviewing the tables that are allowed for Dataverse search, in context of a solution. Using the new solution explorer, you can see a snapshot of the Dataverse search index on the **Overview** page.

   > [!NOTE]
   > If you're selecting tables for Dataverse search on a Power Apps US Government environment, use the legacy solution explorer to choose the tables to be indexed for Dataverse search.
   > :::image type="content" source="media/legacy-solution-explorer-small.png" alt-text="Image of legacy solution explorer":::

1. Sign in to [Power Apps](https://make.powerapps.com/).

2. Select **Solutions**.

3. Select the solution you want to make the changes in, and then select **Overview**.

   :::image type="content" source="media/maker-portal1.png" alt-text="Image of where to select the solution and then select Overview.":::

4. Select **Manage search index**.

   :::image type="content" source="media/maker-portal2.gif" alt-text="Image of how to select tables to index in the Manage-search-index panel.":::

Although there's no limit on how many tables you can index for Dataverse search, there's a limit on the total number of **fields** that you can enable for Dataverse search. Dataverse search indexes 50 fields by default. Since the maximum is 1,000 searchable fields for an organization, this means you can configure up to **950 searchable fields**.

> [!IMPORTANT]
> Some columns are common to all tables, like **Primary Name** and **ID**, which are part of the 50 fields indexed by default for all tables, and are not counted for every table.

When you select a table to index for Dataverse search, you can see the number of fields that are added to the index.

:::image type="content" source="media/maker-portal3.png" alt-text="Manage search index pane with number of fields highlighted.":::

The number of fields indexed for a table is dependent on the tables Quick Find view. Additionally, some field types are treated as multiple fields in the Dataverse search index, as indicated in this table.

| Field type          |  Number of fields used in <br /> the Dataverse search index  |
|----------------------------------------------------|----|
| Lookup (customer, owner, or Lookup type attribute) | 3   |
| Option Set (state, or status type attribute)       | 2   |
| All other types of fields                          | 1  |

The progress bar at the bottom shows the percentage of indexed fields as a fraction of the maximum allowed number of searchable fields.

:::image type="content" source="media/maker-portal4.png" alt-text="Search pane with progress bar highlighted.":::

A warning message appears when you reach the indexed field limit. If you want to add more fields to the index, you have to free up space, either by removing some of the fields that are already in the index or removing entire tables from Dataverse search scope.

By default, the following system tables are indexed for Dataverse search. However, you must add custom tables to Dataverse search for them to be searchable. In the table, the numbers in parenthesis indicate the total number of columns included in the index for that table.

| Tables used for Dataverse search <br /> without Dynamics 365 apps allowed | Tables used for Dataverse search <br /> with Dynamics 365 apps allowed |
|-------------------------|-------------------------|
| Account (8)</br>Contact (11)</br>Goal (19)</br>Goal Metric (3)</br>Knowledge Article (56) | Campaign (2)</br>Campaign Activity (4)</br>Campaign Response (6)</br>Case (5)</br>Competitor (1)</br>Contract (7)</br>Invoice (4)</br>Lead (6)</br>Marketing List (5)</br>Opportunity (11)</br>Opportunity Product (8)</br>Order (4)</br>Product (5)</br>Quote (4)</br>Service (1)</br>Service Activity (9) |

> [!NOTE]
> Changes made to the Dataverse search configuration or to the searchable data may take up to 15 minutes to appear in the search service. It may take up to an hour or more to complete a full sync for average-size organizations, and a couple of days for large-size organizations.

### Select searchable fields and filters for each table

The table's Quick Find view drives the searchable table fields and filters used for Dataverse search. The complete set of **Find columns**, **View columns**, and **Filter columns** in a table's Quick Find view become part of the Dataverse search index when you enable it for Dataverse search. There's no limit to how many searchable fields you can add for each table. However, as previously noted, there's a limit on the total number of indexed fields.

- The **Find columns** on a Quick Find view define the searchable fields in the Dataverse search index. Text fields such as _Single Line of Text_ and _Multiple Lines of Text_, _Lookups_, and _Option Sets_ are searchable. **Find columns** of all other data types are ignored.
  > [!NOTE]
  > Currency fields must be added to the **Find Columns** so the currency symbol that is visible on the record will be returned in the search results. If the currency field isn't added to the search index, users see the currency symbol localized according to their language settings.

- The **View columns** on a Quick Find view define the fields that are displayed in model-driven apps' search results page when the matched results are returned.

- The **Filter conditions** on a Quick Find view are applied to the Dataverse search results. This table provides a list of filter clauses **not supported** by Dataverse search.

| Operator          |
|-----------------------|
| Like             |
| NotLike          |
| BeginsWith       |
| DoesNotBeginWith  |
| EndWith           |
| DoesNotEndWith    |
| ChildOf           |
| Mask              |
| NotMask           |
| MaskSelect        |
| EqualUserLanguage |
| Under             |
| NotUnder          |
| UnderOrEqual      |
| Above             |
| AboveOrEqual      |
| NotNull           |
| Null              |

To edit the searchable fields of a table:

1. Sign in to [Power Apps](https://make.powerapps.com/).

2. Select **Dataverse** > **Tables**.

3. Select the table you want to make the changes to and then select the **Views** tab.

4. Select **Quick Find view** type in the list of views.

5. Edit _View_ columns and _Find_ columns by adding, removing, or reordering columns. For a more detailed description of how to add or remove columns in a view, go to [Choose and configure columns in model-driven app views in Power Apps](/powerapps/maker/model-driven-apps/choose-and-configure-columns).

   :::image type="content" source="media/maker-portal5.gif" alt-text="Image shows how to edit searchable fields of a table":::

6. Select **Publish** to publish the changes to the view.

> [!IMPORTANT]
> Changes to Quick Find view also apply to single-table and multi-table Quick Find configurations. Therefore, **we don't prevent you from including fields that aren't supported for Dataverse search when you configure Quick Find view**. However, unsupported fields aren't synced to the Dataverse search index and don't appear in the Dataverse search results.

> [!TIP]
> You can use the **Quick Find view** to define which fields appear as facets in model-driven apps with Dataverse search enabled. All **View columns** with data types other than _Single Line of Text_ and _Multiple Lines of Text_ are marked as facetable and filterable in the index. By default, the first four facetable fields in the **Quick Find view** for the selected table appear as facets when users search by using Dataverse search. At any time, you can only select four fields as facets.

> [!NOTE]
>
> - Changes made to the Dataverse search configuration or to the searchable data may take up to 15 minutes to appear in the search service. It may take up to an hour or more to complete a full sync for average size organizations, and a couple of days for very large size organizations.
>
> - The maximum search-term size is 1,024 characters.
>
> - Although you can have related table fields as a **View column** or a **Find column** or a **Filter column** in a table's Quick Find view, related table fields are not supported by Dataverse search and hence ignored.
>
> - If you change the length of text in a table column and the column is set to **Simple Search view**, the import may not be successful and you may see this error:
>
> - _Length is not valid because this is an indexed attribute and hence cannot have size greater than 1,700_.
>
> - The indexed attribute can't extend beyond 1700 bytes. If the corresponding column is registered in the **Quick Find view**, remove the corresponding column from the **Quick Find view** and try to re-export after a time interval. If you change or delete a **Quick Find view** setting, it may take up to 24 hours to be reflected in the index, as it's a once-a-day maintenance job for the on-premises product. For more information, go to [Maximum capacity specifications for SQL Server](/sql/sql-server/maximum-capacity-specifications-for-sql-server?view=sql-server-ver16&preserve-view=true).
>
> - Updates to calculated fields and lookups do not automatically sync in Dataverse search. Data is refreshed whenever a field configured for Dataverse search is updated in a record.
>
> - There are some common fields, that are part of every table in Dataverse, so you see these fields in the Dataverse search index by default. Some common field examples are:
>
>   - **ownerid** (Name of lookup)
>   - **owningbusinessunit** (Name of lookup)
>   - **statecode** (Label of optionset)
>   - **statuscode** (Label of optionset)
>   - **name** (Primary name field of any table that may or may not be the same as the logical name, such as _fullname_ or _subject_, of the table.)
>
> - If you add a common field to any table for Dataverse search, search is performed for that common field across all entities. However, once you choose a specific table through the Record Type facet, Dataverse search follows the tables' defined settings you set up through Quick Find view.

### Configure quick actions that appear with Dataverse search in model-driven apps

Dataverse search experience brings some of the most frequently used actions closer to search results, to help users complete their tasks without having to navigate to the record page in model-driven apps. _Quick actions_ are a small set of commands specific to a table. Users can see quick actions when they're interacting with search in model-driven apps running on a web browser. Some of the commonly used tables are configured to show a set of commands to help them complete their task without losing context.

| Table            | Quick actions      |
|-------------|------------------------------------------------------------|
| Account     | Assign, Share, Email a link                                |
| Contact     | Assign, Share, Email a link                                |
| Appointment | Mark complete, Cancel, Set Regarding, Assign, Email a link |
| Task        | Mark complete, Cancel, Set Regarding, Assign, Email a link |
| Phone call  | Mark complete, Cancel, Set Regarding, Assign, Email a link |
| Email       | Cancel, Set Regarding, Email a link                        |

Quick actions are a subset of the table's homepage grid commands. For example, when you select an account in its homepage grid, the Account table's quick actions are derived from the set of commands at the top of the page. You can use the ribbon's **EnableRule** to hide or show quick actions for a table. To learn more about defining ribbon-enable rules in Power Apps, go to [Define ribbon enable rules](/powerapps/developer/model-driven-apps/define-ribbon-enable-rules).

These three new enable rules give you the flexibility to optimize quick actions:

- **ShowOnQuickAction rule** is a rule to make a command appear only as a quick action.

  ```XML
  <CommandDefinition Id="new.contact.Command.Call">
    <EnableRules>
      <EnableRule Id="Mscrm.SelectionCountExactlyOne" />
      <EnableRule Id="Mscrm.ShowOnQuickAction" />
    </EnableRules>
    <DisplayRules />
    <Actions>
      <JavaScriptFunction FunctionName="simplealert" />
    </Actions>
  </CommandDefinition>
  ```

- **ShowOnGridAndQuickAction rule** is a rule to make a command appear on the homepage grid and as a quick action.

- **ShowOnGrid rule** is a rule to make a command appear only on the homepage grid. You can use this command to hide an existing quick action.

> [!NOTE]
> Each table can have up to six quick actions.
>
> Quick actions currently show up only in the context of search—alongside suggestions and in the results page on the primary column. The same set of quick actions appears alongside suggestions and in the results page.

## Set managed properties for Dataverse search

If you include a table for Dataverse search, the **Can enable sync to external search index** managed property must be set to **True** for the table. By default, the property is set to **True** for some of the out-of-the-box tables and all custom tables. Some of the system tables can't be enabled for Dataverse search.

To set the managed property, take these steps:

1. Go to **Advanced Settings** > **Customizations**.

2. Select **Customize the System**.

3. Under **Components**, expand **Entities**, and then select the table you want.

4. On the menu bar, select **Managed Properties**. For **Can enable sync to external search index**, select **True** or **False** to set the property to the desired state. Select **Set** to exit, as shown here.

   :::image type="content" source="media/relevance-search-managed-properties.PNG" alt-text="Image of how to set the managed property.":::

5. Select **Publish** for your changes to take effect.

If you want to change the **Can enable sync to external search index** property to **False**, you must first _deselect_ the table from Dataverse search. This message appears if the table is included in the Dataverse search:

_This entity is currently syncing to an external search index. You must remove the entity from the external search index before you can set the **Can enable sync to external search index** property to **False**._

If **Can enable sync to external search index** is set to **False** and you try to include a table in Dataverse search, this message appears:

_Entity can't be enabled for Dataverse search because of the configuration of its managed properties_. For custom tables with sensitive data, consider setting the **Can enable sync to external search index** property to **False**._

> [!IMPORTANT]
> Once you install the managed solution on the target system, it becomes a managed property and you aren't able to change the value of the property.

## Dataverse search reporting FAQs

This section provides answers to frequently asked questions about Dataverse search reporting.

### How can I find out how much storage Dataverse search consumes?

In the past, a table called, _RelevanceSearch_ reported on the storage consumed by Dataverse search at the environment level. Now, two new reporting tables are available for both Database and file storage consumption. The two new tables are:

- **DataverseSearch-StructuredIndex** for Database storage indexing.
- **DataverseSearch-UnstructuredIndex** for Files storage indexing.

Respectively, Dataverse search is reported as part of database and files storage consumption in the **Summary** tab. You can also view Dataverse search in the **Environment** report in Power Platform admin center or **Capacity** report:

- In the new admin center, go to **Licensing > Capacity add-ons > Dataverse** tab to select the **Chart** icon for details.
- In the classic admin center, go to **Resources > Capacity > Dataverse** tab.
- In the new admin center, go to **Licensing > Dataverse > Environments** tab to select an environment and see a _Table view_ for it on the main page.
- In the classic admin center, go to **Billing > Licenses > Dataverse > Environment** tab.

### What entitlements are consumed by Dataverse search?

Dataverse search consumes against the [Dataverse entitlements available within your tenant](whats-new-storage.md).

- Dataverse search structured index consumption counts towards Dataverse database capacity.
- Dataverse search unstructured index consumption counts towards Dataverse file capacity.

### How do I manage Dataverse search

Dataverse search storage is already reported and charged at the environment level as a table called _RelevanceSearch_ and charged by its GB capacity.

There are three states associated with this setting:

#### On

- All experiences are allowed.
- All respective data is indexed immediately.
- Dataverse search storage consumption reflects reported indexed data.

#### Default

- All experiences are allowed except the global search bar in model-driven applications.
- Respective data is only indexed when triggered:

  - On Power Platform admin center Copilot setting being turned on
  - On adding a Dataverse table or uploading a file into a Microsoft Copilot Studio agent
  - On Microsoft Copilot Studio skill creation
  - On first Copilot query call (submitted prompt)

- Dataverse search storage consumption is only reflected once there is reported indexed data.

#### Off

When you turn off Dataverse search:

- You limit all the turned-on experiences.
- You allow your respective indexed data to get deleted after 12 hours.
- You don't have any Dataverse search storage consumption.

> [!NOTE]
>
> Dataverse search is turned **On** if you happen to use any of the above features in the existing environment (and for any new production environment) and **Default** by default for any other scenario or new environment.

We recommend turning on Dataverse search so users can enjoy a better search experience in model-driven apps and appreciate the benefits of generative AI capabilities. As an Environment admin, you can opt out of this feature for the purpose of managing your environments by selecting the option **Off**.

### How much will Dataverse search cost?

Dataverse search is charged at the same rate as _Database Capacity_ and _File Capacity_, respectively, based on content-storage consumption. Content-storage consumption doesn't include the storage for the Dataverse indexed data.

Dataverse search = Database capacity + Files Capacity (Measured in gigabytes)

### When does Dataverse search start getting consumed against my storage entitlements?

Starting April 7, 2025, Dataverse search starts drawing from Dataverse storage entitlements as detailed in this article.

> [!IMPORTANT]
> Dataverse search counts towards the different storage entitlements you have in the tenant.

### What happens if Dataverse search is turned off?

If you turn off Dataverse search for longer than 12 hours, all indexed Dataverse data gets deleted, and the global-search and generative-AI experiences that depend on it are limited or unusable for all users in the environment.

Environment admins have 12 hours to turn the feature back on with no implications.

- During 12 hours:

  - All Dataverse indexed data is stored.
  - Dataverse search consumption is reported.

- After 12 hours:

  - All Dataverse indexed data is deleted.
  - No Dataverse search consumption is reported.
  - Dependent experiences, such as published agents and published model-driven applications, are limited.

### How do I re-enable Dataverse search?

If you turn off Dataverse search and want to re-enable it, you have two options:

- Select **On** if you wan to immediately retrigger indexes across all enabled experiences for them to work accordingly and to resume Dataverse search consumption reporting.
- Select **Default** if you want Dataverse search consumption only reported when indexes are triggered.

### What's the impact of turning Dataverse search off across dependent experiences?

|Feature   |Maker experience  |End-User experience  |
|----------|------------------|---------------------|
|Microsoft Copilot Studio agent – add knowledge     | <ul><li> Cannot upload files. </li><li>Cannot select Dataverse tables. </li><li>Agent doesn't provide results until Dataverse is enabled for the environment (Warning banner with call to action for environment's admin to enable it).  | <ul><li>Agent doesn't provide results until Dataverse is enabled for the environment (default to fallback answer).   |
|Microsoft Copilot Studio agent – Copilot chat  | <ul><li>Agent doesn't provide results until Dataverse is enabled for the environment (Warning banner with call to action to connect with environment's admin to enable it).  |<ul><li>Agent doesn't provide results until Dataverse is enabled for the environment (default to fallback answer).  |
|Model-driven applications – Dataverse search  | <ul><li>Search bar isn't visible in model-driven applications.  | <ul><li>Same as maker experience. |
|Model-driven applications – Copilot chat  |<ul><li> Can use model-driven app for record management (add, edit, delete, etc.). </li><li> Agent doesn't provide results until Dataverse is enabled for the environment (Warning banner with call to action to connect with environment's admin to enable it).  |<ul><li>Same as maker experience.|
|Prompt actions with AI Builder/Custom AI prompts in Power Apps, Microsoft Copilot Studio, and Power Automate  | <ul><li>If enabled in the settings, prompts aren't grounded with Dataverse knowledge.|<ul><li> N/A|

### What actions can admins take?

To ensure optimal operations for the organization, admins with the proper permissions can either increase capacity storage or reduce Dataverse search by performing these steps:

1. Go to the Power Platform admin center and turn off Copilot experiences in model-driven apps
2. Disable Copilot experiences in Microsoft Copilot Studio
3. Remove knowledge in Microsoft Copilot Studio
4. Disable Copilot in Dynamics 365 applications
5. Disable AI prompts
6. Go to the Power Platform admin center and turn Dataverse search _Off_. It's strongly recommended to NOT turn off Dataverse search because it negatively impacts all dependent generative-AI experiences in your different applications, and all users using them.

### See also  

- [Search for tables and rows by using Dataverse search](/powerapps/user/relevance-search)
- [Configure facets and filters](/power-apps/user/facets-and-filters)
- [Frequently asked questions about Dataverse search](/power-apps/user/relevance-faq)
- [Dynamics 365 results in Microsoft Search](/microsoftsearch/manage-dynamics365)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
