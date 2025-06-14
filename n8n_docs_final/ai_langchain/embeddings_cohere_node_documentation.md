# Embeddings Cohere node documentation

**Source:** https://docs.n8n.io/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.embeddingscohere/

---

# Embeddings Cohere node

Use the Embeddings Cohere node to generate [embeddings](../../../../../glossary/#ai-embedding) for a given text.

Credentials

You can find authentication information for this node [here](../../../credentials/cohere/).

Parameter resolution in sub-nodes

Sub-nodes behave differently to other nodes when processing multiple items using an expression.

Most nodes, including root nodes, take any number of items as input, process these items, and output the results. You can use expressions to refer to input items, and the node resolves the expression for each item in turn. For example, given an input of five `name` values, the expression `{{ $json.name }}` resolves to each name in turn.

In sub-nodes, the expression always resolves to the first item. For example, given an input of five `name` values, the expression `{{ $json.name }}` always resolves to the first name.

## Node parameters

- **Model**: Select the model to use to generate the embedding. Choose from:
  - **Embed-English-v2.0(4096 Dimensions)**
  - **Embed-English-Light-v2.0(1024 Dimensions)**
  - **Embed-Multilingual-v2.0(768 Dimensions)**

Learn more about available models in [Cohere's models documentation](https://docs.cohere.com/docs/models).

## Templates and examples

[Browse Embeddings Cohere integration templates](https://n8n.io/integrations/embeddings-cohere/), or [search all templates](https://n8n.io/workflows/)

## Related resources

Refer to [Langchain's Cohere embeddings documentation](https://js.langchain.com/docs/integrations/text_embedding/cohere/) for more information about the service.

View n8n's [Advanced AI](../../../../../advanced-ai/) documentation.

## AI glossary

- **completion**: Completions are the responses generated by a model like GPT.
- **hallucinations**: Hallucination in AI is when an LLM (large language model) mistakenly perceives patterns or objects that don't exist.
- **vector database**: A vector database stores mathematical representations of information. Use with embeddings and retrievers to create a database that your AI can access when answering questions.
- **vector store**: A vector store, or vector database, stores mathematical representations of information. Use with embeddings and retrievers to create a database that your AI can access when answering questions.
