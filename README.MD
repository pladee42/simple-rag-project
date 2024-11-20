
---

# Retrieval-Augmented Generation (RAG) Notebook

This project demonstrates the implementation and usage of the Retrieval-Augmented Generation (RAG) paradigm for enhancing the performance of language models in generating contextually accurate and reliable responses.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [Examples](#examples)
- [Access Token for Gemma Model](#access-token-for-gemma-model)

## Overview

Retrieval-Augmented Generation (RAG) combines information retrieval with language generation to provide accurate and contextually relevant answers. This notebook focuses on:
1. Retrieving relevant context from a pre-encoded knowledge base.
2. Formatting prompts for Large Language Models (LLMs) using the retrieved context.
3. Generating high-quality responses without fabricating unsupported details.

## Features

- **Knowledge Retrieval**: Efficiently retrieves relevant excerpts using embeddings and similarity search.
- **Prompt Formatting**: Creates detailed, context-aware prompts for LLMs.
- **Customizable Responses**: Supports dynamic query input and customizable temperature settings for response generation.

## Requirements

- Python 3.7+
- Libraries:
  - `transformers`
  - `torch`
  - `pandas`
  - `scikit-learn`
  - Any additional dependencies listed in the notebook
- **Access Token for Hugging Face Gemma Model** (see [Access Token for Gemma Model](#access-token-for-gemma-model))

## Setup and Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/pladee42/rag-from-scratch.git
   cd rag-from-scratch
   ```

2. Install the required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

3. Download the pre-trained model and embeddings:
   - Ensure access to the Gemma model and the knowledge base required for the notebook.

## Usage

1. Open the notebook in Jupyter:
   ```bash
   jupyter notebook rag.ipynb
   ```

2. Follow the sections in the notebook to:
   - Retrieve context based on a query.
   - Generate formatted prompts.
   - Obtain detailed responses using the RAG framework.

3. To test a query:
   ```python
   query = "What are the steps involved in the retrieval process as described for Naive RAG?"
   output_text, context_items = chat(query)
   print(output_text)
   ```

## Examples

### Query Example: "RAG paradigm"

Input:
```
"What are the steps involved in the retrieval process?"
```

Output:
```
The retrieval process in Naive RAG consists of three main stages:
- Indexing
- Retrieval
- Generation
```

Context retrieved:
```
- Context details will be displayed here.
```

### Code Snippets

- Prompt Formatter:
   ```python
   def prompt_formatter(query, context_items):
       ...
   ```
- Chat Function:
   ```python
   def chat(query, temperature=0.7, max_new_tokens=256):
       ...
   ```

## Access Token for Gemma Model

To run the code successfully, you must first obtain an **access token** to use the Gemma model from [Hugging Face](https://huggingface.co). 

### Steps:
1. Create or log in to your Hugging Face account.
2. Navigate to your [Access Tokens](https://huggingface.co/settings/tokens) page.
3. Generate a new token with appropriate permissions.
4. Add the token to the Secret Key menu on Google Colab or if you run locally, just create the .env file per format below:
   ```bash
   HUGGINGFACE_TOKEN=your_hugging_face_token
   ```

---
