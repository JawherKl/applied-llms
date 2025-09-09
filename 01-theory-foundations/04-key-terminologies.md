# 4. Key LLM Terminologies

As you dive deeper into the world of LLMs, you'll encounter a specific set of terms. This glossary defines the essential vocabulary you need to speak confidently about these models. Think of this as your LLM cheat sheet.

## 🎯 Core Concepts

| Term | Definition & Analogy |
| :--- | :--- |
| **Parameters** | The internal variables of the model that are learned during training. They store the model's "knowledge." <br> **Analogy:** The strength of synapses in a human brain. More parameters often mean a more capable model. |
| **Inference** | The process of using a trained model to make predictions on new data. This is what happens when you send a prompt to an LLM API. <br> **Analogy:** Using your learned knowledge to answer a new question. |
| **Context Window** | The maximum amount of text (measured in tokens) that a model can consider at one time. This includes your prompt *and* the generated output. <br> **Analogy:** The model's short-term memory or "working space." |

## 🏋️ Training Concepts

| Term | Definition & Analogy |
| :--- | :--- |
| **Pre-training** | The initial, computationally expensive phase of training an LLM on a massive, general-purpose dataset. This is how the model learns the fundamentals of language. <br> **Analogy:** Getting a broad university education. |
| **Fine-tuning** | A secondary training phase on a smaller, specific dataset to adapt a pre-trained model for a particular task or style (e.g., legal documents, chat etiquette, code generation). <br> **Analogy:** Doing a specialized internship after your general degree. |
| **Prompt Engineering** | The art and science of crafting instructions (prompts) to guide the LLM to produce the desired output without changing its parameters. <br> **Analogy:** Learning how to ask your expert friend the right question to get the best advice. |

## ⚠️ Limitations & Challenges

| Term | Definition & Analogy |
| :--- | :--- |
| **Hallucination** | When an LLM generates plausible-sounding but incorrect, nonsensical, or fabricated information. This is a fundamental risk due to their statistical nature. <br> **Analogy:** A confident storyteller who occasionally fills in gaps with made-up details. |
| **Bias** | Systematic errors or unfair prejudices in the model's outputs, often reflecting biases present in its training data. <br> **Analogy:** A person who has only read news from one side of the political spectrum. |
| **Jailbreaking** | The act of crafting clever prompts to bypass a model's built-in safety guidelines and restrictions. <br> **Analogy:** Social engineering to trick a security guard into breaking the rules. |
| **Temperature** | A parameter that controls the randomness of the output. Low temperature = more deterministic and predictable. High temperature = more creative and random. |

## 🚀 Advanced Concepts

| Term | Definition & Analogy |
| :--- | :--- |
| **Token** | The basic unit of text for an LLM. It can be a word, subword, or punctuation mark. |
| **Embedding** | A numerical representation of a token's meaning as a vector (list of numbers) in high-dimensional space. |
| **Transformer** | The dominant neural network architecture for modern LLMs, built on the **attention mechanism**. |
| **RAG (Retrieval-Augmented Generation)** | A technique that combines an LLM with an external knowledge source (like a database) to provide more accurate and up-to-date answers. <br> **Analogy:** Giving the model access to a reference library while it writes its answer. |
| **LLM Agent** | A system that uses an LLM as a "brain" to make decisions, plan, and use tools (like calculators, APIs, or search engines) to complete multi-step tasks. |

---

**Next Up:** ➡️ **[Paper Summaries: Attention is All You Need](../05-paper-summaries/attention-is-all-you-need.md)**
> Now that we have the vocabulary, let's use it to understand the most influential paper in modern NLP.