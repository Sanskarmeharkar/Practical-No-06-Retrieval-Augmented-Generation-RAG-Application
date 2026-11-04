# Retrieval-Augmented Generation (RAG) on Space Missions (Practical No-06)

Practical No-06, MIT Academy of Engineering.

**Name:** Sanskar Ramesh Meharkar
**PRN:** 202401110029

## About

This project builds a RAG application on a collection of 8 Wikipedia articles about ISRO and NASA space missions. It retrieves the most relevant chunks with `sentence-transformers/all-MiniLM-L6-v2` and answers with the pretrained LLM `Qwen/Qwen2.5-1.5B-Instruct`. The answers are compared with the same LLM without retrieval.

- Chunking: 120 words with 30 overlap (499 chunks)
- Retrieval: cosine similarity, top-4 chunks
- Same questions and greedy decoding for both settings, so only the retrieved context changes

## Results

| Setting | Values tested | Finding |
|---|---|---|
| Keyword score (9 questions) | Without RAG vs with RAG | 0.50 without RAG, 0.83 with RAG |
| Unanswerable questions (2) | Without RAG vs with RAG | Declined 0 of 2 without RAG, 2 of 2 with RAG |
| Number of chunks (k) | 1, 2, 4, 6 | 0.56 for k = 1 and 2, 0.83 for k = 4 and 6 |

- Without retrieval the LLM gave wrong dates and names (Chandrayaan-3 landing, JWST launch) and invented answers.
- RAG fixed most of these, but it still fails when the right chunk is not retrieved (Mars Orbiter Mission orbit date).
- Keyword score is a crude check, so answers should also be read by hand.

## Run it

1. Open the notebook in Google Colab: https://colab.research.google.com/drive/1CUWpPeHZKDRNUkGDp0xGvuN0GamKHAVI?usp=sharing
2. Set the runtime to GPU (Runtime > Change runtime type > T4 GPU).
3. Choose Runtime > Run all.

## Files

- `pract6_rag_Sanskar_Meharkar.ipynb`: code and outputs
- `Practical_No-06_Sanskar_Meharkar.docx`: full report

## Tools

Python, PyTorch, Hugging Face Transformers, Sentence-Transformers, Google Colab. AI assistance: Claude (used for explanations, debugging and report writing).# Retrieval-Augmented Generation (RAG) on Space Missions (Practical No-06)

Practical No-06, MIT Academy of Engineering.

**Name:** Sanskar Ramesh Meharkar
**PRN:** 202401110029

## About

This project builds a RAG application on a collection of 8 Wikipedia articles about ISRO and NASA space missions. It retrieves the most relevant chunks with `sentence-transformers/all-MiniLM-L6-v2` and answers with the pretrained LLM `Qwen/Qwen2.5-1.5B-Instruct`. The answers are compared with the same LLM without retrieval.

- Chunking: 120 words with 30 overlap (499 chunks)
- Retrieval: cosine similarity, top-4 chunks
- Same questions and greedy decoding for both settings, so only the retrieved context changes

## Results

| Setting | Values tested | Finding |
|---|---|---|
| Keyword score (9 questions) | Without RAG vs with RAG | 0.50 without RAG, 0.83 with RAG |
| Unanswerable questions (2) | Without RAG vs with RAG | Declined 0 of 2 without RAG, 2 of 2 with RAG |
| Number of chunks (k) | 1, 2, 4, 6 | 0.56 for k = 1 and 2, 0.83 for k = 4 and 6 |

- Without retrieval the LLM gave wrong dates and names (Chandrayaan-3 landing, JWST launch) and invented answers.
- RAG fixed most of these, but it still fails when the right chunk is not retrieved (Mars Orbiter Mission orbit date).
- Keyword score is a crude check, so answers should also be read by hand.

## Run it

1. Open the notebook in Google Colab: https://colab.research.google.com/drive/1CUWpPeHZKDRNUkGDp0xGvuN0GamKHAVI?usp=sharing
2. Set the runtime to GPU (Runtime > Change runtime type > T4 GPU).
3. Choose Runtime > Run all.

## Files

- `pract6_rag_Sanskar_Meharkar.ipynb`: code and outputs
- `Practical_No-06_Sanskar_Meharkar.docx`: full report

## Tools

Python, PyTorch, Hugging Face Transformers, Sentence-Transformers, Google Colab. AI assistance: Claude (used for explanations, debugging and report writing).
