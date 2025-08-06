# Knowledge_Graph_Builder (Graph Database Integration)

## Overview

This project demonstrates two approaches to build a Knowledge Graph (KG) from a movie dataset and store it in a Neo4j graph database:

1. **Manual Approach**: Building the KG from scratch by defining node properties and relationships manually.
2. **LLM-Enhanced Approach**: Automating the generation of node definitions, relationships, and Cypher queries using LangChain with a language model (LLM).

Both approaches involve data cleaning, Neo4j integration, and query execution, but differ in the way nodes and relationships are generated:

## Approaches

### 1. **Manual Approach**

In this approach, nodes (e.g., movies, directors, actors) are created manually by specifying their properties and relationships. The steps are:

- Clean the data to ensure consistency and remove duplicates.
- Define Cypher queries manually to insert nodes and establish relationships (e.g., `MERGE` statements for nodes and relationships like `[:ACTED_IN]`).
- Execute the queries to load the data into Neo4j.

### 2. **LLM-Enhanced Approach**

In this approach, LangChain and a language model (LLM) are used to automate the process of building the graph:

- **Node Definitions**: LangChain analyzes the dataset structure and generates node labels and properties based on the dataset columns.
- **Relationship Detection**: The LLM identifies relationships (edges) between nodes by analyzing dataset structure and node definitions.
- **Cypher Query Generation**: Based on the node definitions and relationships, LangChain generates Cypher queries that create nodes and relationships in Neo4j.

This method leverages the power of LLMs to infer and automate graph structure generation, reducing the need for manual definition.

You can choose between two LLM options:
- **Ollama LLM**: An open-source LLM that can be used locally.
- **Google Gemini API Key**: Use Google’s Gemini model for cloud-based LLM processing.

## Key Concepts

1. **Data Cleaning**: Preparing and normalizing the dataset for graph integration.
2. **Neo4j Integration**: Inserting movie data into Neo4j, either manually or via automated Cypher queries.
3. **Node and Relationship Generation**: Manually defining or using LLM to automatically infer node structures and relationships.
4. **Cypher Query Execution**: Using generated or manually defined Cypher queries to build the graph.

## Requirements

- Python 3.10+
- Neo4j Database (local or remote)
- Required Python packages listed in `requirements.txt`
- Optional: Ollama or Google Gemini API Key for LLM integration

## Setup

1. **Install Dependencies**: Run `pip install -r requirements.txt` to install required libraries.
2. **Set up Neo4j**: Ensure Neo4j is running and accessible (local or remote).
3. **Configure Environment**: Add environment variables (e.g., API keys) to a `.env` file.

   - For Ollama: Install Ollama and use the API endpoint.
   - For Gemini: Obtain a Google API Key and set it up in the `.env` file.

## Features

- **Manual Node & Relationship Creation**: Build a graph manually by defining nodes and relationships.
- **LLM-Automated KG Building**: Use LangChain and LLMs (Ollama or Gemini) to automate node and relationship generation.
- **Error Handling & Logging**: Track progress and handle errors during the data loading process.

## Contributing

Feel free to fork the repository and submit pull requests.
