# GitHub Document Loader node documentation

**Source:** https://docs.n8n.io/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.documentgithubloader/

---

# GitHub Document Loader node

Use the GitHub Document Loader node to load data from a GitHub repository for [vector stores](../../../../../glossary/#ai-vector-store) or summarization.

Credentials

You can find authentication information for this node [here](../../../credentials/github/). This node doesn't support OAuth for authentication.

Parameter resolution in sub-nodes

Sub-nodes behave differently to other nodes when processing multiple items using an expression.

Most nodes, including root nodes, take any number of items as input, process these items, and output the results. You can use expressions to refer to input items, and the node resolves the expression for each item in turn. For example, given an input of five `name` values, the expression `{{ $json.name }}` resolves to each name in turn.

In sub-nodes, the expression always resolves to the first item. For example, given an input of five `name` values, the expression `{{ $json.name }}` always resolves to the first name.

## Node parameters

- **Repository Link**: Enter the URL of your GitHub repository.
- **Branch**: Enter the branch name to use.

## Node options

- **Recursive**: Select whether to include sub-folders and files (turned on) or not (turned off).
- **Ignore Paths**: Enter directories to ignore.

## Templates and examples

[Browse GitHub Document Loader integration templates](https://n8n.io/integrations/github-document-loader/), or [search all templates](https://n8n.io/workflows/)

## Related resources

Refer to [LangChain's documentation on document loaders](https://js.langchain.com/docs/modules/data_connection/document_loaders/integrations/file_loaders/) for more information about the service.

View n8n's [Advanced AI](../../../../../advanced-ai/) documentation.

## AI glossary

- **completion**: Completions are the responses generated by a model like GPT.
- **hallucinations**: Hallucination in AI is when an LLM (large language model) mistakenly perceives patterns or objects that don't exist.
- **vector database**: A vector database stores mathematical representations of information. Use with embeddings and retrievers to create a database that your AI can access when answering questions.
- **vector store**: A vector store, or vector database, stores mathematical representations of information. Use with embeddings and retrievers to create a database that your AI can access when answering questions.
