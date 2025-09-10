# 10. Prompting Frameworks: Structured Design

For simple tasks, basic instructions work. For complex, mission-critical, or reliable tasks, we use **prompting frameworks**. These are structured templates that ensure we provide the model with all the necessary information to succeed consistently.

## 1. Chain-of-Thought (CoT)

**Purpose:** To force the model to reason step-by-step, dramatically improving its performance on complex logic, math, or reasoning problems.

**The Problem:**
*   **Direct Prompt:** `If a store has 10 apples and sells 4, how many are left?`
*   **Model Output:** `6` (This is correct, but for harder problems, the model might guess wrong).

**The Solution (CoT Prompting):**
*   **Prompt:** `If a store has 10 apples and sells 4, how many are left? Let's think step by step.`
*   **Model Output:** `The store started with 10 apples. It sold 4 apples. So, the number of apples left is 10 - 4 = 6. The answer is 6.`

By adding "Let's think step by step," we encourage the model to show its work, which leads to more accurate final answers.

## 2. RTF (Role-Task-Format)

**Purpose:** A simple, all-purpose framework to remember the key components of a good prompt.

*   **R - Role:** Who is the model acting as?
*   **T - Task:** What is the model supposed to do?
*   **F - Format:** How should the output be structured?

**Example Prompt using RTF:**
```
### ROLE ###
You are a seasoned product manager at a tech company.

### TASK ###
Based on the user's feedback below, extract the main pain points and suggest two potential product features to address them.

### FORMAT ###
Present your answer in two clear sections:
1.  **Pain Points:** A bulleted list.
2.  **Feature Ideas:** A numbered list with a brief description for each.

### USER FEEDBACK ###
"[...insert user feedback text here...]"
```

## 3. CRISPE (Context, Role, Instructions, Steps, Parameters, Examples)

**Purpose:** A comprehensive framework for designing complex, production-level prompts. It ensures no detail is missed.

**CRISPE Framework:**

*   **C - Context:** The background information and scenario.
*   **R - Role:** The persona the AI should adopt.
*   **I - Instructions:** The core task to be accomplished.
*   **S - Steps:** The step-by-step process to follow.
*   **P - Parameters:** Constraints, rules, and output format.
*   **E - Examples:** Input-output pairs to demonstrate the task.

**Example Skeleton for a CRISPE Prompt:**
```
### CONTEXT ###
[Provide the background information here]

### ROLE ###
[Assign the role here, e.g., "You are an expert data scientist"]

### INSTRUCTIONS ###
[State the primary task clearly]

### STEPS ###
1.  [Step 1 the model should follow]
2.  [Step 2 the model should follow]
3.  [Step 3 the model should follow]

### PARAMETERS ###
-   Output Format: [e.g., JSON, Markdown table]
-   Length: [e.g., Under 500 words]
-   Tone: [e.g., Professional and concise]

### EXAMPLES ###
[Provide 1-2 examples of input and desired output]

### ACTUAL INPUT ###
[The actual data you want the model to process]
```

## 4. The Ask -> Refine -> Confirm Loop

This is a meta-framework for interaction, not a single prompt. It's useful for complex, multi-turn tasks where you need to refine the output.

1.  **Ask:** Provide your initial detailed prompt (using RTF or CRISPE).
2.  **Refine:** Ask the model to improve its own output.
    *   *"That's good. Now, make the tone more persuasive."*
    *   *"Now, convert that summary into a JSON object."*
3.  **Confirm:** Use the model to check for errors or missing elements.
    *   *"Review the previous response for any factual inaccuracies."*

## 🧠 Framework Cheat Sheet

| Framework | Best For | Key Takeaway |
| :--- | :--- | :--- |
| **Chain-of-Thought** | Reasoning, Math, Logic | Add "Think step-by-step" to complex problems. |
| **RTF (Role-Task-Format)** | Everyday, quick prompts | An easy checklist to improve basic prompts. |
| **CRISPE** | Complex, production prompts | The most thorough framework for critical tasks. |
| **Ask -> Refine -> Confirm** | Interactive dialogue | Treat the model as a junior assistant to collaborate with. |

## 🧪 Exercise: Apply a Framework

**Task:** Get help debugging a Python function.

1.  **Write a Basic Prompt:** `Why is this function giving me an error? [paste code]`
2.  **Now, apply the RTF Framework:**
    *   **Role:** `Act as a senior Python developer.`
    *   **Task:** `Explain the error in this code and provide a fixed version.`
    *   **Format:** `First, state the error name and cause. Then, show the fixed code in a code block.`
3.  **Compare the outputs.** The framed prompt will be infinitely more useful.

---

**Next Up:** ➡️ **[Explore Prompt Tools](../11-prompt-tools/)**
> Now that you can structure prompts, let's use specialized tools to analyze and perfect them.