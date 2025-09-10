# Exercise: Zero-Shot Prompting

**Objective:** Learn to craft prompts that get the desired result **without any examples**, relying solely on the model's pre-existing knowledge and reasoning capabilities.

**Definition: Zero-Shot Prompting**
Asking the model to perform a task without providing any examples of what you want. You are relying entirely on the model's ability to understand the instruction and apply its knowledge.

## 🏋️‍♂️ Warm-up: Direct Questions

Test the model's inherent knowledge with direct, zero-shot prompts.

```
1.  What is the capital of Portugal?
2.  Who wrote the novel '1984'?
3.  Translate the following English word to Spanish: 'apple'.
```
*These work perfectly because they are simple facts the model has seen countless times.*

## 🧠 Level Up: Reasoning and Instruction

The real power of zero-shot is in more complex instructions. The key is **clarity and specificity**.

**Prompt:**
```
Act as a helpful librarian. I have enjoyed books by Brandon Sanderson and Patrick Rothfuss. Suggest three similar fantasy authors I might like. For each suggestion, provide a one-sentence reason why.
```
*This zero-shot prompt works because it provides:*
1.  A **Role** (`librarian`)
2.  **Context** (`enjoyed Sanderson and Rothfuss`)
3.  A clear **Task** (`suggest three similar authors`)
4.  **Formatting Instructions** (`one-sentence reason`)

It doesn't need examples because the concept of "similar authors" is well within the model's training data.

## 🎯 Practice Tasks

Craft a single, self-contained zero-shot prompt for each task. Do not provide examples.

**Task 1: The Categorizer**
Create a prompt that takes a list of items and categorizes them.
*   **Input:** `['broccoli', 'apple', 'carrot', 'cake', 'ice cream', 'spinach']`
*   **Desired Output:** A sorted list under the headings 'Healthy' and 'Treat'.

**Task 2: The Tone Shifter**
Create a prompt that rewrites a sentence with a different tone.
*   **Input:** `"This is a reminder that your report is due tomorrow."`
*   **Desired Output:** The same message rewritten in a formal, urgent, and friendly tone.

**Task 3: The Code Reviewer**
Create a prompt that performs a specific code review task.
*   **Input:** `A function written in Python.`
*   **Desired Output:** An analysis that only identifies potential performance bottlenecks, not style or syntax errors.

## 🔍 Analysis & Reflection

1.  **Success Rate:** For which tasks did zero-shot prompting work perfectly? For which did it struggle?
2.  **Specificity:** Did you find yourself needing to be extremely specific in your instructions to avoid ambiguous outputs?
3.  **Limits:** Based on this exercise, what are the inherent limitations of zero-shot prompting? (e.g., tasks requiring a very specific or unique format might need an example).

The ability to write effective zero-shot prompts is crucial because it's the fastest and most efficient way to interact with an LLM.