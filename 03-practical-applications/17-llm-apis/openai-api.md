# OpenAI API: Getting Started

The OpenAI API provides access to GPT models, offering powerful text generation and understanding capabilities. This guide covers the essentials for getting started.

## 🚀 Quick Start

### 1. Installation
```bash
pip install openai
```

### 2. Authentication
Get your API key from [platform.openai.com/api-keys](https://platform.openai.com/api-keys) and set it as an environment variable:
```bash
export OPENAI_API_KEY='your-api-key-here'
```

Or set it in your code:
```python
import openai

openai.api_key = "your-api-key-here"
```

### 3. Your First API Call
```python
import openai

response = openai.chat.completions.create(
    model="gpt-3.5-turbo",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Explain quantum computing in simple terms."}
    ]
)

print(response.choices[0].message.content)
```

## 📋 Key Parameters

### Essential Parameters:
```python
response = openai.chat.completions.create(
    model="gpt-4",                    # Model to use
    messages=[...],                   # Conversation history
    max_tokens=150,                   # Maximum response length
    temperature=0.7,                  # Creativity (0.0-2.0)
    top_p=0.9,                        # Diversity control
    n=1,                              # Number of completions
    stop=["\n", "###"],               # Stop sequences
)
```

### Temperature Guide:
- `0.0`: Deterministic, repetitive
- `0.5`: Balanced creativity
- `1.0`: Creative, varied responses
- `>1.0`: Highly random (use with caution)

## 💡 Common Patterns

### Multi-turn Conversation
```python
messages = [
    {"role": "system", "content": "You are a helpful math tutor."},
    {"role": "user", "content": "What is 15 * 27?"},
    {"role": "assistant", "content": "15 * 27 is 405."},
    {"role": "user", "content": "Now add 95 to that result."}
]

response = openai.chat.completions.create(
    model="gpt-3.5-turbo",
    messages=messages
)
```

### JSON Mode (Structured Output)
```python
response = openai.chat.completions.create(
    model="gpt-3.5-turbo",
    messages=[{"role": "user", "content": "List 3 books with author and year."}],
    response_format={"type": "json_object"}  # Requires system message about JSON
)
```

### Streaming Responses
```python
stream = openai.chat.completions.create(
    model="gpt-3.5-turbo",
    messages=[{"role": "user", "content": "Tell me a long story."}],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content is not None:
        print(chunk.choices[0].delta.content, end="")
```

## 🛠️ Practical Examples

### Text Summarization
```python
def summarize_text(text):
    response = openai.chat.completions.create(
        model="gpt-3.5-turbo",
        messages=[
            {"role": "system", "content": "You are a helpful summarization assistant."},
            {"role": "user", "content": f"Summarize this text in 3 bullet points:\n\n{text}"}
        ],
        max_tokens=200
    )
    return response.choices[0].message.content
```

### Code Generation
```python
def generate_python_function(description):
    response = openai.chat.completions.create(
        model="gpt-3.5-turbo",
        messages=[
            {"role": "system", "content": "You are a expert Python programmer."},
            {"role": "user", "content": f"Write a Python function that {description}. Include docstring and type hints."}
        ]
    )
    return response.choices[0].message.content
```

## ⚠️ Error Handling

```python
import openai
from openai import OpenAIError

try:
    response = openai.chat.completions.create(
        model="gpt-3.5-turbo",
        messages=[{"role": "user", "content": "Hello"}]
    )
except OpenAIError as e:
    print(f"OpenAI API error: {e}")
except Exception as e:
    print(f"Other error: {e}")
```

## 💰 Cost Management

### Estimate Token Usage
```python
import tiktoken

def count_tokens(text, model="gpt-3.5-turbo"):
    encoding = tiktoken.encoding_for_model(model)
    return len(encoding.encode(text))

text = "Hello, how are you?"
token_count = count_tokens(text)
print(f"Token count: {token_count}")
```

### Set Usage Limits
```python
# Client with budget awareness
client = openai.OpenAI(
    api_key="your-api-key",
    max_retries=2,
    timeout=30  # seconds
)
```

## 📚 Additional Resources

- [OpenAI API Documentation](https://platform.openai.com/docs/api-reference)
- [Python Library Documentation](https://github.com/openai/openai-python)
- [API Usage Dashboard](https://platform.openai.com/usage)
- [Model Capabilities](https://platform.openai.com/docs/models)

---

**Next API:** ➡️ **[Anthropic API](./anthropic-api.md)**