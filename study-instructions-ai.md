# Create Semantic Model with AI

### Sign into Fabric

Go to [Fabric](https://app.fabric.com) and sign in with the Entra ID account provided for the study. It will follow the following format.

`powerbitestuser<USER_NUMBER>@msftpowerbistudy.onmicrosoft.com`

Examples:

- `powerbitestuser1@msftpowerbistudy.onmicrosoft.com`
- `powerbitestuser25@msftpowerbistudy.onmicrosoft.com`

Replace `USER_NUMBER` to match the login provided in your study invitation.

### Fabric workspace

Create semantic models in the `powerbitestuser<USER_NUMBER>` workspace that is already created for you.

   ![Study workspace](resources/img/study-workspace.png)

### GitHub Copilot App and Paid Copilot License

1. Open the **GitHub Copilot App**
2. Sign-in with your GitHub account that should have an associated paid Copilot license as set up in [Prerequisites](pre-requisites.md)
   
	![gh-app-sign-in](resources/img/gh-app-sign-in.png)

	Select the account in the bottom left and click Manage accounts.

	![gh-app-signed-in](resources/img/gh-app-signed-in.png)

3. Check you are not using a free Copilot license. The free Copilot license will not work for this study.

	![copilot-license](resources/img/copilot-license.png)

### MCP Servers and Plugins

Check the following MCP servers and plugins are installed by selecting **Customize** > **Installed**.

> [!NOTE]
> The MCP servers must be successfully connected to carry out the study. This is shown by the green checkmarks.

> [!NOTE]
> The [Power BI Modeling MCP](https://github.com/microsoft/powerbi-modeling-mcp) is a local MCP server and it must be ***uninstalled or disabled*** to carry out the study. You will get Power BI agentic modeling capabilitis from the Power BI Authoring MCP Server (Hosted) MCP server instead.

The MCP servers should have a green checkmark to show they are connected using your GitHub Copilot account.
   - Power BI Authoring MCP Server (Hosted)
   - FabricIQ
   - fabric-sqlendpoint
   - fabric-skills
   - powerbi-authoring

![gh-app-plugin-installed](resources/img/plugins-mcp.png)

### Initialize Copilot Session

Click New to start a new Copilot chat session. Enter the following prompt text. This is a safeguard to avoid cached credentials to other tenants,  associated previous Copilot usage memory and/or other previously installed MCP servers or plugins. Remember to replace `USER_NUMBER` to match the login provided in your study invitation.

```text
During this session, authenticate only using powerbitestuser<USER_NUMBER>@msftpowerbistudy.onmicrosoft.com. Create items only in the powerbitestuser<USER_NUMBER> workspace and use only the Power BI Authoring MCP Server (Hosted), FabricIQ and fabric-sqlendpoint MCP servers.
```

![gh-app-plugin-installed](resources/img/new-copilot-chat.png)

### Create semantic model using AI

Create a semantic model called **ZavaSemanticModel-AI**  based on the requirements below.

* Use all the tables in the ZavaWarehouse warehouse located in the MsftPowerBIStudy workspace.
* Do not use an existing semantic model in the workspace as a template.
* Minimize data duplication and refresh management overhead.
* Use business friendly table and measure names.
* Provide the ability to filter by all relevant dimensions.
* Follow semantic modeling best practices.
* Create a measure for Customer Count without double counting customers.
* Apply time intelligence calculations for all relevant measures, supporting Month to Date (MTD), Year to Date (YTD), Previous Year (PY), Year Over Year Percentage (YOY%).
* Create a measure for Inventory Units as a semi-additive measure to report by the last date in filter context. For example, the inventory units for a week should not be the sum of the inventory units for each of the days in that week.
* Create a measure for Online Sales Amount that applies currency conversion so it can be reported by any of the currencies for which there is data. To apply conversion, divide the USD amount by the end of day rate for each transaction day. Make sure the converted currency uses the correct format string for each currency. If there is no user filter on currency, default to US dollars.
* Make sure you leave the semantic model in a state that is ready for queries.

### Query Requirements

Use the semantic model you created to answer the following data questions. You can create and execute a DAX query for each of the following data questions. Show the queries.
1. What is online sales in USD and online sales YTD (year to date) in the Europe sales territory group for each of the months in 2026? Reuse any time intelligence capabilities you built into the model to answer this question.
2. What is the customer count, previous year value, and YOY% (year over year growth percentage) of customer count in the Europe sales territory group broken out by the months in 2026? Reuse any time intelligence capabilities you built into the model to answer this question.
3. What are the inventory units for each month in 2026 for blue products?
4. What is online sales for each month in 2026 converted to each of the following currencies? Brazilian Real, EURO, US Dollar, United Kingdom Pound, Yen. Show the output with the respective format string for each currency.

### Returning Query Results

Place queries and results (copy/paste tables or screenshots) into a Word document with name as follows to be returned to your Microsoft study contact. Remember to replace `USER_NUMBER` to match the login provided in your study invitation.

`AI_QueryResults_powerbitestuser<USER_NUMBER>.docx`


<!--
## Evaluation Criteria

Data Correctness
* Do all 4 data questions return correct results (10% each)

Best Practices
* Is the model Direct Lake on OneLake? (10%)
* Are user friendly names used for tables and measures? (10%)
* Do visible tables and measures have a business definition? (10%)
* Are foreign key columns hidden? (10%)
* Are calculation groups used for time intelligence? (10%)
* Is a date dimension table used - either dataCategory="Time" or custom calendar defined? (10%)

-->
