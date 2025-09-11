# Use Case: Text Summarization

Summarization is one of the most practical and widely-used applications of LLMs. This guide covers strategies for creating effective summaries of various types of content.

## 🎯 When to Use Summarization

- **Long articles** or reports → Key insights
- **Meeting transcripts** → Action items and decisions
- **Research papers** → Methodology and findings
- **Customer feedback** → Common themes and sentiments
- **Legal documents** → Main条款 and obligations

## 📝 Prompt Patterns for Summarization

### Basic Summary
```
Summarize the following text in 3-4 sentences:

[Insert text here]
```

### Bullet Point Summary
```
Provide a bulleted list summary of the key points from this text:

[Insert text here]
```

### TL;DR Summary
```
Create a TL;DR (Too Long; Didn't Read) summary of this content:

[Insert text here]
```

### Targeted Summary
```
Summarize this text focusing specifically on [topic/theme]. Ignore other aspects:

[Insert text here]
```

## 🎨 Advanced Summarization Techniques

### Extract-Then-Summarize (Two-Step)
For very long documents, break the process into two steps:

**Step 1: Extract Key Sections**
```
Identify the 3-5 most important paragraphs from this document for understanding
the main conclusions. Return only those paragraphs:

[Insert long document]
```

**Step 2: Summarize Extracted Content**
```
Now summarize these key paragraphs into a concise overview:

[Paste extracted paragraphs]
```

### Comparative Summary
```
Compare and contrast these two articles about [topic]. Create a summary that
highlights their agreements, disagreements, and unique perspectives:

[Article 1 text]
---
[Article 2 text]
```

### Structured Summary
```
Summarize this meeting transcript with the following structure:
- Key decisions made
- Action items with owners
- Open questions requiring follow-up
- Main discussion topics

[Insert transcript]
```

## ⚠️ Common Challenges & Solutions

**Problem:** Summary includes irrelevant details
**Solution:** Be more specific about what to focus on
```
Summarize only the technical specifications, ignoring marketing language:

[Product description]
```

**Problem:** Summary is too verbose
**Solution:** Specify exact length constraints
```
Summarize in exactly 100 words:

[Text]
```

**Problem:** Loses nuance or important context
**Solution:** Ask for balanced coverage
```
Provide a balanced summary that covers both positive and negative aspects
mentioned in this review:

[Customer feedback]
```

## 🧪 Practice Exercise

**Text to Summarize:**
```
The new Quantum X smartphone features a 6.8-inch OLED display with 120Hz refresh rate, 
Snapdragon 8 Gen 3 processor, 12GB RAM, and 512GB storage. The camera system includes 
a 200MP main sensor, 50MP ultrawide, and 10x telephoto lens. Battery life is rated at 
2 days with moderate use. It runs Android 14 with 5 years of security updates. The 
device is water resistant (IP68) and includes satellite connectivity for emergency 
services. Pricing starts at $1,199 with pre-orders beginning next week.
```

**Try these prompt variations:**
1. Basic 2-sentence summary
2. Bullet point list of specifications
3. Summary focused only on camera features
4. Comparison with a phone you know well

## 📊 Evaluation Criteria for Summaries

- **Accuracy:** Faithful to original content
- **Completeness:** Covers all key points
- **Conciseness:** No unnecessary information
- **Readability:** Clear and well-structured
- **Focus:** Matches the requested emphasis

---

**Next Use Case:** ➡️ **[Brainstorming](./brainstorming.md)**