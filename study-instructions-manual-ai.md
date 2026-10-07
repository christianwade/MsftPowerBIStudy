# Create Semantic Model with AI

Thank you for taking part in this study. This will help guide future investment of Power BI and Fabric.

You will create two semantic models based on the same set of requirements. One will be created manually and the other using AI.

## Sign into Fabric

Go to [Power BI](https://app.powerbi.com) and sign in with the Entra ID account provided for the study. It will follow the format powerbitestuserX@msftpowerbistudy.onmicrosoft.com.

Create your models in the workspace already created for you following powerbitestuserX naming.

   ![Study workspace](resources/img/study-workspace.png)
   
## Create semantic model using AI

Take the following prompt text and replace the login and workspace names with the ones provided to you for this study. In GitHub Copilot App, start by entering the text so start a Copilot session. This is a safeguard to avoid cached credentials to other tenants,  associated previous Copilot usage patterns and/or other previously installed MCP servers or plugins.

```text
During this session, authenticate only using powerbitestuser1@msftpowerbistudy.onmicrosoft.com. Create items only in the powerbitestuser1 workspace and use only the following MCP servers.
- Power BI Authoring MCP Server (Hosted)
- FabricIQ
- fabric-sqlendpoint
```

Using the same Copilot session, create a semantic model called **ZavaSemanticModel-AI** based on the the [Semantic Model Requirements](semantic-model-and-query-requirements.md#semantic-model-requirements).

Once the model is created, create and execute queries based on the [Query Requirements](semantic-model-and-query-requirements.md#query-requirements). Place queries and results (copy/paste tables or screenshots) into a Word document with name as follows to be returned to Sida.Peng@microsoft.com. Remember to replace the login name with yours.

`powerbitestuserX_QueryResults_AI.docx`
