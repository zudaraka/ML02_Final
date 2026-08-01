# System architecture

HeritageLens contains four connected layers.

## 1. User and interface layer

The visitor uploads an image and enters a question through Gradio. The interface later displays the computer-vision prediction, uncertainty information, retrieved evidence cards, citations, and conversational answer.

## 2. Computer-vision pipeline

The image is decoded as RGB, resized to 224 × 224, and passed to the official leakage-controlled EfficientNet-B0 V2 classifier. Softmax probabilities are converted into a structured result containing the predicted style, confidence, top-three classes, probability margin, and uncertainty status.

## 3. Retrieval pipeline

The user question is combined with the classifier result and relevant conversation context. MiniLM converts the query to an embedding. Chroma performs semantic retrieval over the 71-record `heritagelens_architecture_v2` collection and returns up to eight candidate passages. Style filtering is used for style-specific questions and relaxed for comparison questions. A cross-encoder reranks the candidates and selects the strongest three passages.

## 4. Grounded generation and memory

LangChain constructs a prompt containing the structured prediction, three evidence passages, source metadata, and session history. Gemini generates a contextual answer using `[S1]`–`[S3]` citations. Per-session message history enables follow-up questions without mixing conversations between users.

The architecture diagram in `system_architecture.png` shows the complete information flow and the handoff between the classifier and RAG pipeline.
