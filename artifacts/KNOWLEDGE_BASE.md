# RAG knowledge-base artifact

The final application reconnects an existing persistent Chroma database rather than rebuilding it.

## Confirmed contract

- Collection: `heritagelens_architecture_v2`
- Expected records: 71
- Embedding model: `sentence-transformers/all-MiniLM-L6-v2`
- Retrieval: top 8 semantic candidates
- Reranking: best 3 using `cross-encoder/ms-marco-MiniLM-L-6-v2`
- Required metadata: style, title, source, source organisation, and source URL when available

Expected Google Drive location:

```text
/content/drive/MyDrive/HeritageLens/PartC_RAG/vector_database/
```

The persistent database and source-document collection are excluded from normal Git commits. Before assessment submission, provide an assessor-accessible Google Drive folder or ZIP link here. The shared package should include the vector database and the five-or-more heritage source documents used to construct it.

**Assessment link:** TO BE ADDED BEFORE PUBLISHING
