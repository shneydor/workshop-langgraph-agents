# LangGraph Agents Workshop

This repository contains the materials and code examples for the **LangGraph Agents on AWS** Workshop, designed to teach you how to build sophisticated AI agents using LangGraph and Amazon Bedrock. 

## 🎯 Workshop Overview

This hands-on workshop explores the latest advancements in AI agents and agentic workflows, leveraging improvements in function-calling LLMs and specialized tools. You'll learn to build production-ready AI agents that can reason, act, and collaborate to solve complex tasks.

## 🔗 Workshop Studio

This workshop is available in AWS Workshop Studio: [LangGraph Agents Workshop](https://catalog.us-east-1.prod.workshops.aws/workshops/50bb135b-8301-49da-bd75-14c821091926/en-US)

## 🧠 What You'll Learn

### Core Concepts
- **Multi-Agent Systems**: Design and orchestrate multiple specialized agents working together
- **LangGraph Framework**: Master the graph-based approach to building stateful, controllable agents  
- **Agentic Workflows**: Implement planning, tool use, reflection, and multi-agent communication patterns

### Practical Applications
- Build a basic ReAct (Reasoning and Acting) agent from scratch
- Implement agents with cyclic graphs using LangGraph's nodes, edges, and state management
- Integrate agentic search tools for enhanced AI capabilities

## 🛠 Technology Stack

- **LangGraph**: Graph-based orchestration framework for building stateful agents
- **Amazon Bedrock**: Access to foundation models 
- **LangChain**: Core framework for LLM application development
- **Tavily API**: Agentic search capabilities for dynamic information retrieval
- **Python**: Primary programming language

## 🚀 Getting Started

### Prerequisites

- **AWS Account**: Will be provided to you as part of the event. 

## 📖 Usage Examples

### Basic Agent Creation
```python
from langgraph.prebuilt import create_react_agent
from langchain_aws import ChatBedrock

# Initialize the model
model = ChatBedrock(model_id="anthropic.claude-3-sonnet-20240229-v1:0")

# Create a simple agent
agent = create_react_agent(
    model=model,
    tools=[your_custom_tools],
    prompt="You are a helpful assistant"
)

# Run the agent
response = agent.invoke({
    "messages": [{"role": "user", "content": "Your query here"}]
})
```

### Custom Graph Agent
```python
from langgraph.graph import StateGraph, MessagesState

# Define your agent workflow
workflow = StateGraph(MessagesState)
workflow.add_node("agent", agent_node)
workflow.add_node("tools", tool_node)
workflow.set_entry_point("agent")
# Add edges and conditional logic...

app = workflow.compile()
```

## 🏷 Tags

`ai-agents` `langgraph` `langchain` `amazon-bedrock` `aws` `multi-agent-systems` `llm` `generative-ai` `python` `workshop`

---

**Ready to build the future of AI agents?** Start with the workshop and contact nir.shneydor@automat-it.com to discuss the endless possibilities of LangGraph and Amazon Bedrock integration!
