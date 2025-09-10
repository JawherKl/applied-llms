# Exercise: Mastering Basic Prompts

**Objective:** Practice the fundamental building blocks of a good prompt: **Instruction, Role, and Format.**

## 🏋️‍♂️ Warm-up: The Instruction

Start with a simple instruction and watch it evolve.

**Step 1: The Basic Ask**
```
Explain what a REST API is.
```
*Copy this into your LLM and note the output. It's probably a good, but generic, explanation.*

**Step 2: Add a Role**
Now, give the model an identity. This provides context and shapes the style of the answer.
```
Act as a senior software architect with 20 years of experience. Explain what a REST API is.
```
*How did the tone and depth change? It likely became more authoritative and used more professional jargon.*

**Step 3: Define the Audience**
The same expert explains things differently to different people.
```
Act as a senior software architect. Explain what a REST API is to a beginner front-end developer who knows HTML and JavaScript but has never worked with APIs before.
```
*The explanation should now use analogies related to front-end work and avoid overly complex backend terminology.*

**Step 4: Control the Format**
Finally, dictate how you want the information presented.
```
Act as a senior software architect. Explain what a REST API is to a beginner front-end developer. Your explanation must include a simple analogy and present the key principles in a bulleted list.
```
*This should give you a structured, easy-to-digest output that meets very specific criteria.*

## 🎯 Practice Tasks

Try to craft a single prompt that fulfills all the requirements for each task below. Use the Role + Instruction + Format structure.

**Task 1: The Cooking Helper**
*   **Role:** A Michelin-star chef
*   **Instruction:** Explain how to perfectly sear a scallop
*   **Format:** Provide a numbered step-by-step guide. Include one pro tip.

**Task 2: The Financial Advisor**
*   **Role:** A conservative financial planner
*   **Instruction:** Explain what an index fund is
*   **Format:** Use a simple analogy. Keep the explanation under 100 words.

**Task 3: The Debugging Partner**
*   **Role:** A patient senior developer
*   **Instruction:** [Paste the code below] - Explain why this Python function might be failing.
*   **Format:** First state the error, then explain the cause in simple terms, then provide the corrected code.

```python
# Paste this code for Task 3
def calculate_average(numbers):
    total = sum(numbers)
    average = total / len(number)  # Error on this line
    return average

print(calculate_average([10, 20, 30]))
```

## 🔍 Analysis & Reflection

After completing the tasks, ask yourself:
1.  For which task was adding a **role** the most impactful? Why?
2.  How did specifying a **format** change the usefulness of the output?
3.  Was there a case where the model ignored part of your instruction? How could you rewrite the prompt to make it more explicit?

**Tip:** Try each task twice: once with a poorly written prompt and once with your refined prompt. Compare the results to truly internalize the difference.