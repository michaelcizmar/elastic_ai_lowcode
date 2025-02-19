# Dify Chat with Tools

This example incorporates a chat agent with tools.

## Instructions to import a project

1. Open a browser window and visit the Dify dashboard at [http://localhost/apps](http://localhost/apps)
2. In the left side of the screen, select "Import DLS File", then import one of the `.yml` files from this folder.

### Configuring the AI Models

The LLM modules use AI models configured in your Dify instance. Multiple models from multiple providers can be configured in Dify, and so it may happen that you don't have the same model configured that the project you imported uses.

For example, you may have imported a project with an LLM module configured to use OpenAI's GPT-4o, but you may not have this specific model and provider configured in your system.

In these cases, select the project you imported, click the LLM module to open its configuration, click on the AI model at the top (it should be highlighted in red if you don't have the model) and select a different model you have configured.

If you don't have any model configured:

1. Go to the dashboard at [http://localhost/apps](http://localhost/apps)
2. Click on your user in the upper-right corner of the screen, then go to "Settings".
3. In the left panel, select "Model Provider".
4. Select a provider and configure the model of your choice. Afterwards, it will be available to be used in the LLM modules.

## Project Notes

### CAP Chat With Data Agent

- The chatbot requires the [elastic_retrieval_tool](./elastic_retrieval_tool.yml), so this tool needs to be imported and published as a tool to be abailable for the agent orchestration to use it:
    1. Import the `elastic_retrieval_tool` tool following the import instructions above.
    2. Select the tool, and in the upper-right corner, select "publish", "configure". Input `elastic_retrieval_tool` under "name", and under "tool_call_name" input `search_documents`. The rest of the params can be filled at will.
    3. Save and publish.
    4. Import the `chat_with_data_agent` chatbot.
    5. Select it, and verify that the `elastic_retrieval_tool` is listed under "Tools". If not, add it.
- Due to an issue with the validation of the self-signed https certificates of the elasticsearch service instance, this flow uses the [es_search_ui_proxy](../../es_search_ui_proxy/README.md) api as a middleware to communicate with Elasticsearch. As such, this service should be running in the background (it should be running by default, as it's included in the root [docker-compose.yaml](../../docker-compose.yaml) file alongside Dify)..
