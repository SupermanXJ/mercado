<div class="inner-content">

## 1. MCP Server from Mercado Libre

The Model Context Protocol (MCP) is an open protocol that standardizes
the connection of artificial intelligence models with different data
sources and tools. In this context, the MCP Server from Mercado Libre
offers utilities so that developers can easily interact with Mercado
Libre’s APIs and resources using natural language, simplifying tasks and
product integrations.

## 2. Prerequisites

Before starting, make sure you have the following environment:

| Requirement | Description                                                                                                                                             |
|-------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| MCP Client  | A compatible client (for example, Cursor, Windsurf, Cline, Claude Desktop, ChatGPT, etc).                                                               |
| Credentials | [Access Token](https://global-selling.mercadolibre.com/devsite/authentication-and-authorization-global-selling) from your application in Mercado Libre. |

  

## 3. Installation and configuration

## 3.1 Cursor

To connect to our MCP from Mercado Libre, you must first connect with
the client that best fits your integration. Check the step-by-step
according to the client type.

In Cursor, you can click the button below or follow the steps manually.

<div style="text-align:center">

[![](https://http2.mlstatic.com/storage/developers-site-cms-admin/155791267080-cursor.png)](https://cursor.com/en/install-mcp?name=mercadolibre-mcp-server&config=eyJ1cmwiOiJodHRwczovL21jcC5tZXJjYWRvbGlicmUuY29tL21jcCIsImhlYWRlcnMiOnsiQXV0aG9yaXphdGlvbiI6IkJlYXJlciBBY2Nlc3NfVG9rZW4ifX0%3D)

</div>

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

Replace Access\_Token ; with your Access Token. More
[information](https://global-selling.mercadolibre.com/devsite/authentication-and-authorization-global-selling)
on how to obtain it.

</div>

</div>

</div>

</div>

To connect to the MCP server of Mercado Libre from Cursor manually,
follow these steps:

``` language-javascript
Cursor Settings > Tools & Integrations > New MCP Server
```

This will open a tab where you can view and configure the available MCP
servers.  
In the configuration, be sure to include the following JSON block to
connect to the Mercado Libre MCP server

**JSON:**

``` language-javascript
{
  "mcpServers": {
    "mercadolibre-mcp-server": {
      "url": "https://mcp.mercadolibre.com/mcp",
      "headers": {
       "Authorization": "Bearer Access_Token"
      }
    }
  }
}
```

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

Replace Access\_Token; with your Access Token. More
[information](https://global-selling.mercadolibre.com/devsite/authentication-and-authorization-global-selling)
on how to obtain it.

</div>

</div>

</div>

</div>

## 3.2 Windsurf

To connect to Mercado Libre's MCP server from Windsurf, follow these
steps:

``` language-javascript
 Cascade > MCP Servers > Configure 
```

**JSON:**

``` language-javascript
{
  "mcpServers": {
    "mercadolibre-mcp-server":{
      "serverUrl": "https://mcp.mercadolibre.com/mcp",
      "headers": {
        "Authorization": "Bearer Access_Token"
      }
    }
  }
}
```

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

Replace Access\_Token with your Access Token. More
[information](https://global-selling.mercadolibre.com/devsite/authentication-and-authorization-global-selling)
about how to get it.

</div>

</div>

</div>

</div>

<div style="text-align:center">

[![](https://http2.mlstatic.com/storage/developers-site-cms-admin/155737982389-windsurf.png)](https://docs.windsurf.com/plugins/cascade/mcp#model-context-protocol-mcp)

</div>

  

## 3.3 Other IDEs

Open the IDE settings and look for the JSON file related to MCP
servers.  
Then, fill the “Authorization” fields with your Access Token.

**JSON:**

``` language-javascript
{
  "mcpServers": {
    "mercadolibre-mcp-server": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://mcp.mercadolibre.com/mcp",
        "--header",
        "Authorization:${AUTH_HEADER}"
      ],
      "env": {
        "AUTH_HEADER": "Bearer Access_Token"
      }
    }
  }
}
```

<div style="text-align:center">

[![](https://http2.mlstatic.com/storage/developers-site-cms-admin/155737964545-cline.png)](https://docs.cline.bot/mcp/configuring-mcp-servers)

</div>

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

Replace &lt;Access\_Token&gt; with your Access Token.

</div>

</div>

</div>

</div>

## 4. MCP Server connection

1.  Establish the remote connection from your preferred client (e.g.
    Cursor).
2.  Make sure the MCP server is available and correctly configured in
    your client.
3.  If it doesn't appear, check the configuration and reload the MCP
    servers list.

  

<div style="text-align:center">

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/155725068615-Captura-de-pantalla-2025-07-01-a-la-s--12.01.50.png)

</div>

  

## 5. Available tools

The MCP Server from Mercado Libre offers tools to make integration and
information queries easier.

## search\_documentation

Enables searching for specific terms or key concepts across all the
technical documentation for Mercado Libre developers.

-   **query**: Keywords to search for within the documentation
    (Required)
-   **language**: Language of the documentation to consult (e.g.,
    en\_us, es\_ar, pt\_br) (Required)
-   **siteId**: Country ID to filter results (e.g., MLA, MLB, MLM, etc)
    (Optional)
-   **limit**: Maximum number of results to return (Optional)
-   **offset**: Number of results to skip (Optional)

## get\_documentation\_page

Retrieves the full content of a specific documentation page, useful for
accessing detailed specifications or use cases.

-   **path**: Path of the page to retrieve (Required)
-   **language**: Language of the documentation to consult (e.g.,
    en\_us, es\_ar, pt\_br) (Required)
-   **siteId**: Country ID to filter results (e.g., MLA, MLB, MLM, etc)
    (Optional)

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

**Important:**

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

Make sure to include in the prompt that the CBT documentation is
consulted, as by default all available information (marketplace and CBT)
is consulted. Example: “Use Mercado Libre’s MCP to consult only official
docs—explicitly including Global Selling—and identify the endpoints,
auth, and exact request body parameters to publish a clip.”  

</div>

</div>

</div>

</div>

## 6. Use cases

MCP Server ensures that common developer activities are optimized easily
and quickly. Below, find some use cases to implement in your
integration.

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

**Important:**

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

The examples in this section use Cursor as the MCP client, but you can
use any MCP client you prefer.  

</div>

</div>

</div>

</div>

## 6.1 Search documentation from your IDE

The tools are not used directly by the user or developer, but by the
Agent IDE. For example:

The tool allows the Agentic IDE to search for keywords throughout the
official Mercado Libre documentation and retrieve the most relevant
endpoints or routes for the consulted context.

Then, with the *get\_documentation\_page* tool, the Agentic IDE accesses
the complete content of the routes identified in the previous step,
allowing it to obtain specific information and concrete use cases
directly from the documentation.

This way, the IDE automates querying and browsing documentation, making
it easier for the developer to receive contextualized and precise
answers without having to search manually.

## 6.2 Generate integration code

In addition to consulting documentation, **MCP tools are used by the
Agentic IDE** to generate code and assist in product integration in your
projects.

For example, you can ask the assistant to review the documentation of
the product you want to integrate and identify the steps required to
complete the integration. MCP Server provides the relevant context
(including code samples and technical documentation) that the Agentic
IDE uses to suggest or even directly apply the necessary changes in your
project.

**In this way, the IDE automates querying, analysis, and implementation
of integrations, making the developer's work easier and speeding up the
development process.**

You can request recommendations to implement specific integrations, for
example:

## 7. Errors and solutions

## 7.1 Invalid or missing token

If when trying to connect, the application remains in "Loading Tools"
state indefinitely or fails to connect to the server, there may be a
problem with the authentication token.

**Possible causes:**

-   No authentication token was provided in the request.
-   The provided token has expired or is incorrect.
-   The token format is invalid (e.g., missing or incorrectly copied
    characters).
-   The token does not have the necessary permissions to access the
    requested resource.

**Suggested solutions:**

-   Check that the token is present in the request header (in
    Authorization: Bearer &lt;Access\_Token&gt;).
-   Make sure the token has not expired. If so, request a new one.
-   Copy the full token, with no additional spaces or missing
    characters.

</div>
