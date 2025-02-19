# AI Workflows and Agent Examples using Dify, Ollama, and Elasticsearch

This repository contains a collection of examples demonstrating the use of AI workflows and agents with Dify, Ollama, and Elasticsearch. The examples are designed to showcase how these technologies can be integrated to create powerful and efficient AI applications.

## Table of Contents

- [AI Workflows and Agent Examples using Dify, Ollama, and Elasticsearch](#ai-workflows-and-agent-examples-using-dify-ollama-and-elasticsearch)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Examples](#examples)
    - [Example 1: Chatbot with Dify and Ollama](#example-1-chatbot-with-dify-and-ollama)
    - [Example 2: Chat with Tools](#example-2-chat-with-tools)
    - [Example 3: Use Elastic as a Knowledge Source](#example-3-use-elastic-as-a-knowledge-source)

## Introduction

AI workflows and agents are essential components in building intelligent systems that can process, analyze, and respond to data. This repository provides a set of examples that demonstrate how Dify, Ollama, and Elasticsearch can be used together to create powerful AI applications.
Dify is an open-source framework for developing chatbots and conversational AI applications. It offers a flexible architecture and easy-to-use APIs for building custom chatbot solutions.

Ollama is a lightweight, GPU-accelerated LLM inference server that allows you to run large language models on your own hardware. With Ollama, you can easily deploy and use state-of-the-art AI models without the need for complex infrastructure setup.

Elasticsearch is a powerful search engine that provides fast and scalable full-text search capabilities. It's widely used in applications requiring efficient data retrieval and analysis.

## Examples

### Example 1: Chatbot with Dify and Ollama

This example demonstrates how to create a chatbot using Dify and provide a custom context to work.  This uses Ollama but could be recongfigure to your choice of provider.
To run this example, follow these steps:
1. Install the prerequisites (Docker, Dify, Ollama) and run the necessary services using Docker Compose.  (It is recommended not to run Ollama via Docker particularly on Mac hardware as it will not have access to the GPU)
2. Import the workflow into Dify from this repository. 
   1. The workflow is located in the chat_with_product_sheet directory here: [workflow.yml](../dify/workflow/chat_with_product_sheet/workflow.yml)
   2. Details on the workflow can be found in the [Readme](../dify/workflow/chat_with_product_sheet/README.md)
3. From a command prompt pull llama3.2 (ollama pull llama3.2)
4. Interact with the chatbot and enjoy natural language interactions powered by Ollama.
5. To stop the application, press Ctrl+C in your terminal.

### Example 2: Chat with Tools

This example showcases how to build a chatbot using Dify, Elasticsearch and Ollama or another LLM provider..
To run this example, follow these steps:
1. Install the prerequisites (Docker, Dify, Ollama) and run the necessary services using Docker Compose.  (It is recommended not to run Ollama via Docker particularly on Mac hardware as it will not have access to the GPU)
2. If you do not have access to the Elastic Stack, you can use the [dockercompose.yml](../docker-compose.yml) file provided for Elastic's startup script.
3. Install the [elastic-retrieval-tool.yml](../elastic-retrieval-tool.yml) workflow to retrieve data from
4. Create your index
5. Modify the elastic-retrieval-tool workflow's query and parameters to your environment
6. Publish the workflow within Dify and make it available as a Tool
7. Create an Agent in Dify and Add the Tool
8.  To use a different model or fine-tune the chatbot further, refer to the Dify documentation.


### Example 3: Use Elastic as a Knowledge Source

Seperately, Elastic can be integrated as a knowledge repository in Dify.  See [dify_elastic_retriver](https://github.com/mcplusa/dify_elastic_retriever)