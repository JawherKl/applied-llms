# 3. LLM Architectures: GPT, BERT, and T5

Not all LLMs are created equal. While most modern LLMs are based on the Transformer architecture, they are designed with different objectives, leading to distinct strengths and use cases. Understanding these differences is crucial for choosing the right tool for the job.

The main split is between **Autoencoding**, **Autoregressive**, and **Sequence-to-Sequence** models.

## 🤐 Autoencoding Models (e.g., BERT, ROBERTa)

**Objective:** Understand and represent the input text. They are excellent for analysis tasks.

*   **How they work:** These models use the Transformer's **encoder**. During training, they are given sentences with random words masked (hidden) and are trained to predict those missing words. This is called **Masked Language Modeling (MLM)**.
*   **Key Characteristic:** They are **bidirectional**. When processing a token, they can attend to all surrounding tokens—both to the left and the right. This gives them a deep, contextual understanding of the entire input.
*   **Best For:** Tasks where you need a deep understanding of the input text.
    *   Text classification (e.g., sentiment analysis, spam detection)
    *   Named Entity Recognition (NER)
    *   Word-level analysis
*   **Not ideal for:** Text generation, as they are not designed to predict the next token sequentially.

## 🗣️ Autoregressive Models (e.g., GPT, Llama, Mistral)

**Objective:** Generate text, one token at a time. They are the classic "LLMs" we interact with.

*   **How they work:** These models use the Transformer's **decoder**. During training, they are trained to predict the *next* token in a sequence. This is called **Causal Language Modeling (CLM)**. The "auto" (self) "regressive" (predictive) name comes from the fact that they use their own generated output as input for the next step.
*   **Key Characteristic:** They are **unidirectional**. To ensure they only learn from past context and don't "cheat" by seeing the future, they use a masked attention mechanism. This causal mask prevents a token from attending to tokens that come after it.
*   **Best For:** Any task that involves generating text.
    *   Chatbots and conversational AI
    *   Creative writing, story generation
    *   Code generation
    *   Summarization (though T5 is often stronger)

## 🔄 Sequence-to-Sequence (Seq2Seq) Models (e.g., T5, BART)

**Objective:** Transform one sequence of text into another. They are the true "translators."

*   **How they work:** These models use the **full Transformer architecture—both an encoder and a decoder**. The encoder processes the input text and creates a rich contextual representation. The decoder then uses this representation to autoregressively generate the output sequence.
*   **Key Characteristic:** They are designed for transformation. The entire input is understood first (via the encoder), and then the output is generated (via the decoder).
*   **Best For:** Tasks where the output is a direct transformation of the input.
    *   Translation (e.g., English to French)
    *   Text summarization
    *   Text simplification
    *   Question Answering (given a context)

## 📊 Architecture Comparison at a Glance

| Feature | **Autoencoding (BERT)** | **Autoregressive (GPT)** | **Sequence-to-Sequence (T5)** |
| :--- | :--- | :--- | :--- |
| **Transformer Part** | Encoder | Decoder | Encoder + Decoder |
| **Attention** | Bidirectional (Full) | Unidirectional (Causal) | Bidirectional Encoder + Causal Decoder |
| **Training Objective** | Masked Language Modeling | Causal Language Modeling | Denoising / Span Corruption |
| **Primary Use** | Analysis & Understanding | Text Generation | Text Transformation |
| **Example** | "Is this review positive?" | "Write a poem about code." | "Translate this to Spanish." |

---

**Next Up:** ➡️ **[Key Terminologies: Fine-tuning, Hallucination, and More](./04-key-terminologies.md)**
> To talk about these models effectively, we need to master the common vocabulary of the LLM world.