# RAG_TF-IDF_BM25

# Search Engine

## Overview
Following SE is a text-based mini search engine built from scratch. This project implements various information retrieval techniques including boolean retrieval, vector space model with TF-IDF, and BM25 ranking. Additionally, it explores Retrieval-Augmented Generation (RAG) capabilities with Large Language Models.

## Features

### Email Parsing and Preprocessing
- Reads and parses the Enron Email Dataset (a subset of 814 emails)
- Implements text preprocessing including:
  - Lowercase conversion
  - Special character and punctuation removal
  - Tokenization by whitespace
  - Filtering to keep only alphabetic tokens

### Boolean Retrieval
- Builds an inverted index for efficient document retrieval
- Supports complex boolean queries with AND, OR, and NOT operators
- Returns documents matching the specified boolean conditions

### Ranking Methods
1. **Vector Space Model with TF-IDF**
   - Implements cosine similarity for document ranking
   - Uses TF-IDF weighting for document vectors
   - Applies raw term frequency for query vectors

2. **BM25 Ranking**
   - Implements the Okapi BM25 ranking function
   - Accounts for term frequency saturation and document length normalization
   - Configurable parameters (k1=1.2, b=0.75)

### Retrieval-Augmented Generation (RAG)
- Integrates search results with Large Language Models
- Compares LLM responses with and without retrieval augmentation
- Demonstrates how retrieval can enhance LLM responses with domain-specific knowledge

## Implementation Details

### Data Structure
- Documents are stored as dictionaries with Document-ID and content
- Inverted index maps tokens to document IDs for efficient retrieval
- Term frequency and document frequency statistics are maintained for ranking

### Query Processing
- Tokenizes and preprocesses queries using the same pipeline as documents
- Supports complex boolean expressions with proper operator precedence
- Implements vector representations for similarity-based ranking

### Performance Analysis
- Compares different ranking methods (TF-IDF vs. BM25)
- Analyzes the impact of document length on ranking scores
- Evaluates the effectiveness of retrieval for augmenting LLM responses

## Key Findings
- BM25 generally provides better ranking than cosine similarity with TF-IDF, especially for handling term saturation and document length normalization
- Retrieval significantly improves LLM responses for domain-specific queries
- Boolean retrieval provides precise results but lacks relevance ranking
- Pre-processing choices significantly impact search quality

## Requirements
- Python 3.x
- Required libraries:
  - math
  - re
  - os
  - collections (defaultdict)
  - google.generativeai (for RAG implementation)

## Usage
The notebook contains complete implementations and examples for:
- Building and querying a boolean retrieval system
- Ranking documents using TF-IDF and BM25
- Implementing RAG with Google's Gemini LLM

## Future Improvements
- Implement stemming and lemmatization for better token matching
- Add support for phrase queries and proximity search
- Improve ranking by incorporating semantic similarity
- Enhance the RAG system with better document selection and prompt engineering
