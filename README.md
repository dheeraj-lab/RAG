# RAG-Based Question Answering System

A simple Retrieval-Augmented Generation (RAG) system that answers questions using relevant information retrieved from a collection of text-based knowledge.

## Overview

This project implements a basic RAG pipeline by combining semantic search with a small language model. It retrieves relevant text chunks from a knowledge base and uses them as context to generate answers.

The system is designed to answer questions based on the available context rather than relying entirely on the language model's internal knowledge.

## Features

- Text-based knowledge base with document chunking.
- Semantic search using sentence embeddings.
- Cosine similarity-based retrieval.
- Similarity threshold to filter irrelevant results.
- Context-based answer generation.
- Returns "Answer does not exist" when no relevant context is retrieved.

## Technologies Used

- Python
- Google Colab
- Sentence Transformers
- Hugging Face Transformers
- all-MiniLM-L6-v2
- Qwen2.5-0.5B-Instruct

## How It Works

The system follows three main stages:

1. **Retrieve:** The user's question is converted into an embedding and compared with stored document embeddings to find the most relevant text chunks.
2. **Augment:** The retrieved chunks are added to the prompt as context.
3. **Generate:** The language model generates a short answer using the provided context.

## Implementation Details

- The knowledge base contains 36 text chunks.
- Sentence embeddings are generated using `all-MiniLM-L6-v2`.
- Each chunk is represented by a 384-dimensional vector.
- The retrieval function selects the top 2 relevant chunks.
- A similarity threshold of 0.3 filters retrieved results.
- Qwen2.5-0.5B-Instruct is used for text generation.

## Installation

Install the required libraries:

```bash
pip install sentence-transformers transformers
```

## How to Run

1. Open the notebook in Google Colab.
2. Run the installation cell.
3. Load the Sentence Transformer model.
4. Prepare the text knowledge base and generate embeddings.
5. Run the retrieval function.
6. Load the Qwen language model.
7. Use the `ask()` function to ask questions.

Example:

```python
ask("What does backpropagation do?")
```

## Example Results

| Question | Result |
|---|---|
| What does backpropagation do? | Computes gradients |
| Why is Hindi expensive in GPT-2? | Hindi requires more tokens than English |
| Who won the cricket world cup? | Answer does not exist. |

## Project Structure

```text
RAG/
│
├── README.md
└── rag_based_qa_system.ipynb
```

## Future Improvements

- Support PDF and multiple document uploads.
- Improve document chunking and retrieval.
- Experiment with different embedding models.
- Evaluate answer accuracy and retrieval performance.
- Build a simple user interface.

## Author

**Dheeraj**

GitHub: [dheeraj-lab](https://github.com/dheeraj-lab)

---

*This project demonstrates the basic working of Retrieval-Augmented Generation by combining semantic retrieval and context-based text generation.*
