# Host remote MCP servers built with official MCP SDKs on Azure Functions

This repo contains instructions and samples for how to turn an MCP server built with the Node MCP SDK into a custom app that can be run on Azure Functions. The repo uses the weather sample server to demonstrate how this can be done. You can clone to run and test the server locally, follow by easy deploy with `azd up` to have it in the cloud in a few minutes. You can follow the instructions provided to manually add the required Functions related artifacts, or have VSCode Copilot make those additions for you by using the experimental prompt provided. 

Find the repo for other languages
| Language (Stack) | Repo Location |
|------------------|---------------|
| C# (.NET) | [dotnet-mcp-sdk-functions-hosting]() |
| Python | [python-mcp-sdk-functions-hosting]() |

## Running MCP server as custom app on Azure Functions
Recently Azure Functions released the [Functions MCP extension](https://techcommunity.microsoft.com/blog/appsonazureblog/build-ai-agent-tools-using-remote-mcp-with-azure-functions/4401059), allowing developers to build MCP servers using Functions programming model, which is essentially Function's event-driven framework, and host them remotely on the serverless platform. 

However, for those who have already built servers with Anthropic's MCP SDKs, it is also possible host the servers on Azure Functions with little to no code changes. How we do this is by leveraging the platform's ability to run custom apps that don't use Azure Function's programming framework, but can still benefit from the platform's bursty scale, serverless pricing model, and security features. These custom apps are called _custom handler_ in Azure Functions. 
<div align="center">
  <img height="250" alt="image" src="https://github.com/user-attachments/assets/f7f4c592-847a-4d61-ad4c-288dd7aebb97" />
</div>

## Quickstart
The sample server in this repo has all the required Functions artifacts and can be easily deployed as is doing the following:

1. Install the [Azure Developer CLI]()
2. `git clone`
3. Open up the sample in VSCode and run `azd up` in the root directory

The last step will help you create a resource group with all the required resources, as well as deploy the server to Azure. Example resource group:


After deployment completes, go to the Function App resource on Azure portal and find the app's endpoint and key:


## Convert MCP server to custom handler

If you have already have server, follow instructions below to add the required artifacts. 


### Use experimental prompt
Instead of manually making the additions above, you can try out the [Azure Functions MCP server converter](https://raw.githubusercontent.com/anthonychu/create-functions-mcp-server/refs/heads/main/prompts/create-functions-mcp-server.prompt.md
) and have VSCode's Copilot follow the prompt's instructions to make those changes for you. 


## Resources

(Any additional resources or related projects)

- Link to supporting information
- Link to similar sample
- ...
