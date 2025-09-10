# 12. Build Your Prompt Library

An effective prompt is a valuable asset. Just like you wouldn't rewrite the same utility function for every project, you shouldn't rebuild prompts from scratch. A **Prompt Library** is your personal collection of tested, reliable prompts that you can use and adapt for future tasks.

This document serves as both a guide and a template for building your own library.

## Why Maintain a Prompt Library?

1.  **Saves Time:** Reuse proven prompts instead of starting from zero.
2.  **Ensures Consistency:** Get reliable, high-quality outputs for repetitive tasks.
3.  **Facilitates Improvement:** Version your prompts and note what works and what doesn't.
4.  **Knowledge Sharing:** Share your best prompts with your team, creating a collective resource.

## How to Organize Your Library

You can use any system you like: a **Notion database**, a **Google Sheet**, a **Markdown folder**, or even a **simple text file**. The key is consistency.

Here is a recommended structure with metadata to capture the most important information about each prompt.

---

## Prompt Library Template

Copy and paste the template below for each new prompt you want to save. The metadata is crucial for finding and using the right prompt later.

### **Metadata Section**

### **Metadata**
- **Prompt ID:** `PE-001` *(A unique identifier, e.g., PE for Prompt Engineering followed by a number)*
- **Title:** One-sentence description of the prompt's purpose.
- **Creation Date:** YYYY-MM-DD
- **Last Updated:** YYYY-MM-DD
- **Author:** Your Name
- **Version:** 1.0 *(Start at 1.0 and increment for significant changes)*
- **Status:** ✅ Production / 🧪 Testing / ❌ Deprecated
- **Primary Use Case:** e.g., Code Debugging, Content Summarization, Email Generation
- **Best For Models:** e.g., GPT-4, Claude-3, Llama-3 *(Some prompts are model-specific)*
- **Tags:** #tag1, #tag2, #e.g., #python, #debugging, #json, #marketing

### **The Prompt Section**

### **The Prompt**
```markdown
*(Your actual, working prompt goes here. Use a code block for clarity.)*

[Paste your complete, tested prompt here. This is the asset itself.]
```

### **Example & Output Section**

### **Example Input**
*(What kind of input do you feed into this prompt? Provide a clear example.)*

```python
# Example input code for a debug prompt
def calculate_average(numbers):
    sum = 0
    for i in range(len(numbers)):
        sum = sum + numbers[i]
    average = sum / len(numbers)
    return average

print(calculate_average([10, 20, 30])) # Output: 20.0
print(calculate_average([])) # This will cause an error!
```

### **Example Output**

```markdown
*(What is the expected output for the example above? This sets the quality standard.)*
```

**Error Analysis:**
The error in the function `calculate_average` occurs when the input list `numbers` is empty. The line `average = sum / len(numbers)` will cause a `ZeroDivisionError` because `len(numbers)` is 0.

**Fixed Code:**
```python
def calculate_average(numbers):
    if not numbers:  # Check if the list is empty
        return 0     # Return 0 or raise a more informative error
    total = sum(numbers)  # Use the built-in sum() function for clarity
    average = total / len(numbers)
    return average
```


**Explanation:**
```markdown
The fix adds a guard clause to handle the empty list case and uses the more Pythonic `sum()` function for better readability and performance.
```

### **Context & Notes Section**

### **Context & Notes**

```markdown
*(This is your "lab notebook." Why does this prompt work? What did you learn?)*
```

- **Frameworks Used:** e.g., RTF, Chain-of-Thought
- **Why it Works:** This prompt works because it assigns a specific role ('Senior Python Developer'), provides clear steps for the task (analyze error, provide fix, explain), and dictates the format. The example input forces the model to recognize the specific error.
- **Iterations:** Version 1.0 didn't include the example and the model sometimes gave a generic answer. Adding the example (few-shot learning) solidified the expected output format.
- **Limitations:** Best used for syntactic and logical errors. May not be as effective for complex architectural issues.


---

## Example Entry: Code Debugger Prompt

### **Metadata**
- **Prompt ID:** `PE-007`
- **Title:** Python Code Debugging and Fix Assistant
- **Creation Date:** 2024-09-09
- **Last Updated:** 2024-09-09
- **Author:** AI Student
- **Version:** 1.1
- **Status:** ✅ Production
- **Primary Use Case:** Code Debugging
- **Best For Models:** GPT-4, Claude-3, CodeLlama
- **Tags:** #python, #debugging, #refactoring, #explanation

### **The Prompt**

Act as a senior Python developer. Your task is to:
1.  Analyze the provided Python code for any errors or bugs.
2.  Identify the specific error and its cause.
3.  Provide a fixed version of the code.
4.  Explain the fix concisely.

Format your response with the following headings:
**Error Analysis:**
**Fixed Code:**
**Explanation:**

Here is an example input and output:
```python
Example Input Code:
def greet(name):
    print("Hello" + name)

greet("Alice") # Missing space, will output "HelloAlice"
```

Example Output:
**Error Analysis:**

```markdown
The code suffers from a string concatenation issue, causing missing whitespace. The expression `"Hello" + name` does not include a space, resulting in output like "HelloAlice".
```

**Fixed Code:**
```python
def greet(name):
    print("Hello " + name)  # Added a space after "Hello"

# Alternatively, use an f-string for modern Python:
# def greet(name):
#     print(f"Hello {name}")
```

**Explanation:**
```markdown
The fix adds a space within the string literal to ensure proper formatting. The alternative using an f-string is more readable and is considered a best practice.

Now, analyze and fix the following code:
{CODE}
```

### **Context & Notes**
- **Frameworks Used:** RTF (Role-Task-Format), Few-Shot Learning.
- **Why it Works:** The role establishes expertise. The task is broken into clear steps. The format ensures structured output. The single, clear example teaches the model the exact depth and style of analysis required without being overly restrictive.
- **Iterations:** v1.0 did not include the example. Adding it (v1.1) improved consistency across different models.
- **Limitations:** May not be deep enough for complex algorithmic problems. For those, a more detailed CoT prompt may be needed.
