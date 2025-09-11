# Anthropic API: Getting Started

The Anthropic API provides access to Claude models, known for their strong reasoning capabilities, long context windows, and safety-focused design.

## 🚀 Quick Start

### 1. Installation
```bash
pip install anthropic
```

### 2. Authentication
Get your API key from [console.anthropic.com](https://console.anthropic.com/settings/keys) and set it:
```bash
export ANTHROPIC_API_KEY='your-api-key-here'
```

Or in your code:
```python
import anthropic

client = anthropic.Anthropic(api_key="your-api-key-here")
```

### 3. Your First API Call
```python
import anthropic

client = anthropic.Anthropic()

message = client.messages.create(
    model="claude-3-sonnet-20240229",
    max_tokens=1000,
    temperature=0.0,
    system="You are a helpful assistant.",
    messages=[
        {"role": "user", "content": "Explain the theory of relativity in simple terms."}
    ]
)

print(message.content[0].text)
```

## 📋 Key Parameters

### Essential Parameters:
```python
response = client.messages.create(
    model="claude-3-opus-20240229",   # Model selection
    max_tokens=1024,                  # Maximum response length
    temperature=0.0,                  # Control randomness (0.0-1.0)
    system="You are a helpful AI.",   # System prompt
    messages=[...],                   # Conversation history
    top_p=0.9,                        # Nucleus sampling
    top_k=50,                         # Top-k sampling
)
```

### Claude Model Family:
- **claude-3-opus**: Most capable, highest cost
- **claude-3-sonnet**: Balanced capability and cost
- **claude-3-haiku**: Fastest, most cost-effective

## 💡 Common Patterns

### Multi-turn Conversation
```python
messages = [
    {"role": "user", "content": "What's the capital of France?"},
    {"role": "assistant", "content": "The capital of France is Paris."},
    {"role": "user", "content": "What's its population?"}
]

response = client.messages.create(
    model="claude-3-sonnet-20240229",
    max_tokens=1000,
    messages=messages
)
```

### Structured Data Extraction
```python
response = client.messages.create(
    model="claude-3-sonnet-20240229",
    max_tokens=1000,
    system="Always respond with valid JSON.",
    messages=[{
        "role": "user", 
        "content": "Extract person, organization, and location from: 'John works at Google in Mountain View.'"
    }]
)
```

### Long Document Processing
```python
# Claude supports up to 200K tokens context!
with open("long_document.txt", "r") as f:
    long_text = f.read()

response = client.messages.create(
    model="claude-3-sonnet-20240229",
    max_tokens=4000,
    messages=[{
        "role": "user", 
        "content": f"Summarize the key points from this document:\n\n{long_text}"
    }]
)
```

## 🛠️ Practical Examples

### Document Analysis
```python
def analyze_document(text):
    response = client.messages.create(
        model="claude-3-sonnet-20240229",
        max_tokens=2000,
        messages=[{
            "role": "user",
            "content": f"Analyze this document and identify:\n1. Main themes\n2. Key arguments\n3. Potential biases\n\nDocument:\n{text}"
        }]
    )
    return response.content[0].text
```

### Complex Reasoning
```python
def solve_problem(problem_statement):
    response = client.messages.create(
        model="claude-3-opus-20240229",
        max_tokens=1500,
        messages=[{
            "role": "user",
            "content": f"Solve this problem step by step, showing your reasoning:\n\n{problem_statement}"
        }]
    )
    return response.content[0].text
```

## ⚠️ Error Handling

```python
import anthropic
from anthropic import APIError, APIConnectionError

try:
    response = client.messages.create(
        model="claude-3-sonnet-20240229",
        max_tokens=1000,
        messages=[{"role": "user", "content": "Hello"}]
    )
except APIConnectionError as e:
    print(f"Connection error: {e}")
except APIError as e:
    print(f"API error: {e.status_code} - {e}")
except Exception as e:
    print(f"Unexpected error: {e}")
```

## 💰 Cost Management

### Estimate Token Usage
```python
def estimate_claude_tokens(text):
    # Rough estimation: ~1 token = 4 characters English text
    return len(text) // 4

text = "Hello, how are you?"
estimated_tokens = estimate_claude_tokens(text)
print(f"Estimated tokens: {estimated_tokens}")
```

### Response Metadata
```python
response = client.messages.create(...)
print(f"Input tokens: {response.usage.input_tokens}")
print(f"Output tokens: {response.usage.output_tokens}")
print(f"Total tokens: {response.usage.input_tokens + response.usage.output_tokens}")
```

## 📚 Additional Resources

- [Anthropic API Documentation](https://docs.anthropic.com/claude/docs)
- [Python Library GitHub](https://github.com/anthropics/anthropic-sdk-python)
- [Claude Model Cards](https://www-files.anthropic.com/production/images/model-card-claude-3.pdf)
- [API Status Dashboard](https://status.anthropic.com/)

---

**Next API:** ➡️ **[Cohere API](./cohere-api.md)**