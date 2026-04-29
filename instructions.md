# Workshop Overview

In this bootcamp, you will build and test an Intergalactic Banking API from end to end. The workshop covers API testing, automation with Postman Agent Mode, and building an MCP server to track transactions between astronauts.

By the end of the session, you will have hands-on experience with a complete workflow for building and validating AI-ready APIs and MCP servers using techniques you can apply immediately in your own projects.

## Resources

| Resource | Link |
| --- | --- |
| **Live Banking API (this session)** | [ai-powered-bootcamp-production.up.railway.app](https://ai-powered-bootcamp-production.up.railway.app/) |
| **Banking API Git Repository** | [github.com/Postman-Devrel/Banking-API-Demo](https://github.com/Postman-Devrel/Banking-API-Demo) |
| **Postman Bootcamp Workspace** | [postman.com/devrel/ai-powered-api-mcp-bootcamp](https://www.postman.com/devrel/ai-powered-api-mcp-bootcamp/overview) |
| **Slides** | [AI-Powered API & MCP Bootcamp.pptx](https://docs.google.com/presentation/d/1VcF-BT7PYGcL4WURUsw9eG9ms-GO2IVn/edit) |
| **Meet Agent Mode** | academy.postman.com/meet-agent-mode |
| **Agent Mode Prompt Library** | postman.com/templates/agent-mode/ |
| **Postman MCP Server** | github.com/postmanlabs/postman-mcp-server |
| **Postman Claude Plug-In** | github.com/Postman-Devrel/postman-claude-code-plugin |

## Prerequisites

Create a brand new Postman Account. You should see the Enterprise Free trial.

---

# Workflow 1: Import the API Spec into Postman

## Step 1 — Create a New Workspace

In Postman, create a **Blank Workspace** and name it in the following format: **Your Name – Intergalactic Banking**

- [ ] Set the visibility to **Internal**
- [ ] Set access to **Everyone in the Team**

## Step 2 — Working with a Forked Collection

Fork **[Do It Yourself] Intergalactic Bank API** from the public workspace into your newly created workspace:
[https://www.postman.com/devrel/ai-powered-api-mcp-bootcamp/overview](https://www.postman.com/devrel/ai-powered-api-mcp-bootcamp/overview)

> **Note:** You may need to download the Postman Desktop Agent. Navigate to the bottom right corner of the screen, locate the Desktop Agent icon, and toggle on **Auto Select** and **Desktop Agent**. You may be prompted to download it automatically.

---

# Workflow 2: Working with Agent Mode

## Step 1 — Set up Agent Mode Models and Create Environment Variable File

Set up Agent Mode by selecting **Claude Sonnet 4.6** as your model and configuring Agent Mode to **Auto Run**.

**You can set Agent Mode context in one of two ways:**

- [ ] Click on the element you want to use as context, such as a collection name or request.
- [ ] Use the **@** command and select your desired context.

Use **Agent Mode** to create an Environment file called **Banking.local** - use the collection as context.

**Set the collection as context and send this prompt:**

> **Agent Mode Prompt:** `Create an Environment Variable file called Banking.local`

Switch to your new environment using the **Environment Selector** dropdown in the top right corner.

## Step 2 — Set the Base URL as a Collection Variable

Use **Agent Mode** to replace all hardcoded localhost URLs with a reusable **Collection Variable**. Ensure the **Collection** is set as the context before running.

**Set the collection as context and send this prompt:**

> **Agent Mode Prompt:** `For all the requests in this collection, add https://ai-powered-bootcamp-production.up.railway.app as a environment variable called baseUrl and update all the URLs in the collection to use {{baseUrl}}.`

Verify that the `baseUrl` variable has been automatically populated in the **Variables** tab.

## Step 3 — Set the api key as an Environment Variable

Send the **Generate API Key** GET request, then verify that the environment variable has been set in the **Environment** tab next to the AI Panel on the top right corner next to AI.

> **Note:** Go to your Environments on the side panel and set the `apiKey` value to **sensitive**.

Then, use the following **Agent Mode** prompt to capture the response values as environment variables.

## Step 3 — Add Post Request Scripts to FromAccount & To Account

**Set the fromAccount request as context and send this prompt:**

> **Agent Mode Prompt:** `Programmatically add a post-response script that parses the response body, reads the accountId field, and saves its value as an environment variable called fromAccount in the Banking.local environment.`

Once you send the **fromAccount** request, verify that the variable appears in the **Variables** tab.

**Set the toAccount request as context and send this prompt:**

> **Agent Mode Prompt:** `Programmatically add a post-response script that parses the response body, reads the accountId field, and saves its value as an environment variable called toAccount in the Banking.local environment.`

Verify the variables are populated by sending both requests, then send the **GET List All Accounts** request to view the randomly generated accounts.

## Step 4 — Add Post Request Scripts to New Transaction

Then send the request — you should see the **transactionId** in the response. You can now use the following **Agent Mode** prompt to capture the transaction ID as a variable as well.

**Set the Create new transaction request as context and send this prompt:**

> **Agent Mode Prompt:** `Programmatically add a post-response script that parses the response body, reads the transactionId field, and saves its value as an environment variable called transactionId in the Banking.local environment.`

Send the request to see the ID populated. Now, if you send the **GET Transaction by ID** request, you should see a **200 OK** response.

---

# Workflow 3: Testing and Automation

## Step 1 — Write Tests with Agent Mode

Once your full API request workflow is producing the expected happy-path responses, use **Agent Mode** to generate a test suite for the collection. Set the **Collection** as the context and send the following **Agent Mode** prompt:

**Set the collection as context and send this prompt:**

> **Agent Mode Prompt:** `Write tests for all the requests in this collection. Include only status code tests and response time tests.`

## Step 2 — Run the Collection Runner

Walk through the **Collection Runner** interface. Demonstrate how to execute all requests in sequence and review the results in the **Test Results** panel.

**Set the collection as context and send this prompt:**

> **Agent Mode Prompt:** `Run all tests using the Collection Runner.`

---

# Workflow 4: Connect the Postman MCP Server

## Step 1 — Generate Your Postman API Key

In Postman, click your **user icon** in the top right, go to **Settings**, then navigate to **API Keys**. Generate a new key and give it an appropriate name (e.g. **Workshop**). Copy the key and store it somewhere accessible — you will not be able to view it again.

## Step 2 — Create an MCP Request

Return to your **Your Name – Intergalactic Banking** workspace and select **MCP Request**. Set the transport type to **HTTP** and use the following MCP Server URL:

```
https://mcp.postman.com/mcp
```

Set the authentication type to **Bearer Token** and enter the API key you generated. You can find additional guidance in the Learning Center.

## Step 3 — Get Collections using MCP Server

Navigate to **Tool 49 – getCollection** and run the request using your **Workspace ID**.

You can find your **Workspace ID** in the **Overview** tab.

---

# Optional Steps - Claude

Explore the **Postman MCP Server** on GitHub: [https://github.com/postmanlabs/postman-mcp-server](https://github.com/postmanlabs/postman-mcp-server)

## Step 1 — Add the MCP Server to Claude Code

Run the following command in your terminal to register the **Postman MCP Server** with **Claude Code**:

```bash
claude mcp add --transport http postman https://mcp.postman.com/mcp --header "Authorization: Bearer <YOUR_API_KEY>"
```

**Expected mcp.json configuration:**

```json
{
  "mcpServers": {
    "postman_mcp_server": {
      "url": "https://mcp.postman.com/mcp",
      "headers": {
        "Authorization": "Bearer PMAK-YOUR-KEY-HERE"
      }
    }
  }
}
```

## Step 2 — Verify the Connection

Use `claude mcp list` in your terminal or `/mcp` in **Claude** to list your registered MCP servers.

> **Claude Prompt:** `List all my Postman workspaces.`

You should receive a list of your Postman workspaces. If so, everything is configured correctly.

## Step 3 — Add Tests via the MCP Server

Use the MCP server to locate your workshop workspace ID and then add tests to the collection.

**Get the workspace ID:**

> **Claude Prompt:** `Get the workspace ID for "[WORKSHOP-WORKSPACE-NAME]".`

**Add tests to the collection:**

> **Claude Prompt:**
> ```
> Using the Postman MCP server, add tests to [workshop collection name].
> For each request:
>   1. Add a status code check (200 OK)
>   2. Validate the response has a 'success' property set to true
> ```

**Run the tests:**

> **Claude Prompt:** `Run the "[workshop collection name]" collection and show me the test results.`
