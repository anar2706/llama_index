# Installation and Setup

## Installation from Pip

Install from pip:

```
pip install llama-index
```

**NOTE:** LlamaIndex may download and store local files for various packages (NLTK, HuggingFace, ...). Use the environment variable "LLAMA_INDEX_CACHE_DIR" to control where these files are saved.

If you prefer to install from source, see below.

## Important: OpenAI Environment Setup

By default, we use the OpenAI `gpt-3.5-turbo` model for text generation and `text-embedding-ada-002` for retrieval and embeddings. In order to use this, you must have an OPENAI_API_KEY set up as an environment variable.
You can obtain an API key by logging into your OpenAI account and [and creating a new API key](https://platform.openai.com/account/api-keys).

```{tip}
You can also [use one of many other available LLMs](/module_guides/models/llms/usage_custom.md). You may
need additional environment keys + tokens setup depending on the LLM provider.
```

## Local Model Setup

If you don't wish to use OpenAI, the environment will automatically fallback to using `LlamaCPP` and `llama2-chat-13B` for text generation and `BAAI/bge-small-en` for retrieval and embeddings. These models will all run locally.

In order to use `LlamaCPP`, follow the installation guide [here](/examples/llm/llama_2_llama_cpp.ipynb). You'll need to install the `llama-cpp-python` package, preferably compiled to support your GPU. This will use around 11.5GB of memory across the CPU and GPU.

In order to use the local embeddings, simply run `pip install sentence-transformers`. The local embedding model uses about 500MB of memory.

## Installation from Source

Git clone this repository: `git clone https://github.com/jerryjliu/llama_index.git`. Then do the following:

- [Install poetry](https://python-poetry.org/docs/#installation) - this will help you manage package dependencies
- `poetry shell` - this command creates a virtual environment, which keeps installed packages contained to this project
- `poetry install` - this will install the core package requirements
- (Optional) `poetry install --with dev,docs` - this will install all dependencies needed for most local development
