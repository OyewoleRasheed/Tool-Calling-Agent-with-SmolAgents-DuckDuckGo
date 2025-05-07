# Tool-Calling Agent with SmolAgents & DuckDuckGo

This project demonstrates the use of a **Tool-Calling Agent** built with the `smolagents` library. The agent leverages the **DuckDuckGoSearchTool** to perform web searches and provides answers based on the search results.

## Features

* **SmolAgents**: An easy-to-use framework for building agents that call external tools.
* **DuckDuckGoSearchTool**: Performs web searches through DuckDuckGo to fetch relevant information.
* **Hugging Face Integration**: Uses the Hugging Face API to interact with models.

## Installation

To install the required libraries, run the following commands in your notebook or terminal:

```bash
!pip install -U smolagents
!pip install duckduckgo-search
```

## Usage

1. **Login to Hugging Face Hub**:
   Begin by logging in to your Hugging Face account for model access:

   ```python
   from huggingface_hub import notebook_login
   notebook_login()
   ```

2. **Create and Run the Agent**:
   After logging in, create an agent instance with the DuckDuckGo search tool and execute a query:

   ```python
   from smolagents import ToolCallingAgent, DuckDuckGoSearchTool, HfApiModel

   agent = ToolCallingAgent(tools=[DuckDuckGoSearchTool()], model=HfApiModel())
   agent.run("Search for the best music recommendations for a party at the Wayne's mansion.")
   ```

## How It Works

* **ToolCallingAgent**: This agent can interact with external tools to fetch information. In this case, it's using the DuckDuckGoSearchTool to search the web.
* **DuckDuckGoSearchTool**: Performs a web search and returns the most relevant results based on the query.
* **HfApiModel**: Utilizes Hugging Face's API to interact with models and APIs for processing the query.

## Requirements

* Python 3.x or later
* Hugging Face account (for notebook login)
* Active internet connection for running the search query

## Example Use Cases

* **Finding Recommendations**: You can modify the query in `agent.run()` to find recommendations for any topic, e.g., party music, best books, top tech gadgets, etc.
* **Tool Customization**: Add more tools to the agent for more advanced use cases (e.g., different search engines, APIs, or custom functions).

## Learn More

For a deeper dive into building tool-calling agents with **SmolAgents**, refer to the official Hugging Face course:
[SmolAgents: Tool-Calling Agents](https://huggingface.co/learn/agents-course/unit2/smolagents/tool_calling_agents)
