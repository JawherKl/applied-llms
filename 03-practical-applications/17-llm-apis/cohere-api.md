# Cohere API: Getting Started

Cohere provides powerful language models focused on enterprise applications, with strong capabilities in classification, generation, and embedding.

## 🚀 Quick Start

### 1. Installation
```bash
pip install cohere
```

### 2. Authentication
Get your API key from [dashboard.cohere.com](https://dashboard.cohere.com/api-keys) and set it:
```bash
export COHERE_API_KEY='your-api-key-here'
```

Or in your code:
```python
import cohere

co = cohere.Client("your-api-key-here")
```

### 3. Your First API Call
```python
import cohere

co = cohere.Client("your-api-key")

response = co.generate(
    model='command-xlarge',
    prompt='Explain quantum computing in simple terms:',
    max_tokens=300
)

print(response.generations[0].text)
```

## 📋 Key Parameters

### Generation Parameters:
```python
response = co.generate(
    model='command-xlarge',           # Model selection
    prompt='Your prompt here',        # Input text
    max_tokens=300,                   # Maximum response length
    temperature=0.7,                  # Creativity control
    k=0,                              # Top-k sampling
    p=0.75,                           # Top-p sampling
    stop_sequences=[],                # Stop generation sequences
    return_likelihoods='NONE'         # Get token probabilities
)
```

### Cohere Model Family:
- **command**: Best for instruction following
- **command-light**: Faster, cheaper version of command
- **command-r**: Advanced reasoning and tool use
- **embed**: For text embeddings

## 💡 Common Patterns

### Chat Interface
```python
response = co.chat(
    model="command-r",
    message="What's the weather like today?",
    temperature=0.3
)

print(response.text)
```

### Multi-turn Conversation
```python
chat_history = [
    {"role": "USER", "message": "What's the capital of France?"},
    {"role": "CHATBOT", "message": "The capital of France is Paris."}
]

response = co.chat(
    model="command-r",
    message="What's its population?",
    chat_history=chat_history
)
```

### Text Embeddings
```python
response = co.embed(
    texts=["Hello world", "How are you?"],
    model="embed-english-v3.0",
    input_type="classification"
)

print(response.embeddings[0][:5])  # First 5 dimensions of first embedding
```

## 🛠️ Practical Examples

### Text Classification
```python
def classify_text(text, classes):
    response = co.classify(
        model='large',
        inputs=[text],
        examples=[{"text": ex["text"], "label": ex["label"]} for ex in classes]
    )
    return response.classifications[0].prediction

# Example usage
classes = [
    {"text": "The product is amazing!", "label": "positive"},
    {"text": "Terrible service, would not recommend", "label": "negative"}
]

result = classify_text("I really enjoyed using this software", classes)
print(f"Classification: {result}")
```

### Document Summarization
```python
def summarize_text(text):
    response = co.summarize(
        text=text,
        length='medium',
        format='paragraph',
        model='command',
        temperature=0.3
    )
    return response.summary

long_text = "..."  # Your long document here
summary = summarize_text(long_text)
```

### Semantic Search
```python
def semantic_search(query, documents):
    # Generate embeddings for documents
    doc_embeds = co.embed(
        texts=documents,
        model="embed-english-v3.0"
    ).embeddings
    
    # Generate embedding for query
    query_embed = co.embed(
        texts=[query],
        model="embed-english-v3.0"
    ).embeddings[0]
    
    # Calculate similarities (simplified)
    similarities = [cosine_similarity(query_embed, doc_embed) 
                   for doc_embed in doc_embeds]
    
    # Return most similar document
    return documents[similarities.index(max(similarities))]

# Helper function for cosine similarity
def cosine_similarity(a, b):
    import numpy as np
    return np.dot(a, b) / (np.linalg.norm(a) * np.linalg.norm(b))
```

## ⚠️ Error Handling

```python
import cohere
from cohere.core import ApiError

try:
    response = co.generate(
        model='command-xlarge',
        prompt='Hello',
        max_tokens=100
    )
except ApiError as e:
    print(f"Cohere API error: {e.status_code} - {e.message}")
except Exception as e:
    print(f"Unexpected error: {e}")
```

## 💰 Cost Management

### Token Counting
```python
def count_cohere_tokens(text):
    response = co.tokenize(text=text)
    return response.length

text = "Hello, how are you?"
token_count = count_cohere_tokens(text)
print(f"Token count: {token_count}")
```

### Usage Monitoring
```python
response = co.generate(...)
print(f"Token usage: {response.meta.tokens}")
```

## 📚 Additional Resources

- [Cohere API Documentation](https://docs.cohere.com/docs)
- [Python SDK GitHub](https://github.com/cohere-ai/cohere-python)
- [API Playground](https://dashboard.cohere.com/playground)
- [Cohere University](https://docs.cohere.com/docs/cohere-university)

---

**Next Step:** ➡️ **[Build Simple Apps](../18-simple-apps/)**