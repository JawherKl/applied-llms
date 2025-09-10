# Exercise: Few-Shot Prompting

**Objective:** Learn to teach the model by providing examples. This is essential for tasks requiring a specific format, style, or complex reasoning that is difficult to describe with instructions alone.

**Definition: Few-Shot Prompting**
Providing the model with a few examples of input-output pairs (the "shots") before presenting it with the actual task. This demonstrates the exact pattern you want it to follow.

## 🏋️‍♂️ Warm-up: Teaching a Format

The most common use of few-shot is to teach a specific output structure.

**Prompt:**
```
Convert the following questions into a JSON object with keys 'topic' and 'question'.

Example 1:
Input: "What is the speed of light?"
Output: { "topic": "physics", "question": "What is the speed of light?" }

Example 2:
Input: "Who painted the Mona Lisa?"
Output: { "topic": "art", "question": "Who painted the Mona Lisa?" }

Now, convert this:
Input: "What is the capital of Japan?"
Output:
```
*The model will reliably generate: `{ "topic": "geography", "question": "What is the capital of Japan?" }`*

The examples taught it the exact JSON format and the logic for inferring the 'topic'.

## 🧠 Level Up: Complex Pattern Recognition

Use few-shot to teach nuanced tasks, like classifying sentiment or tone, where the boundaries are fuzzy.

**Prompt:**
```
Classify the sentiment of these customer reviews as 'Positive', 'Neutral', or 'Critical':

Review: "The product is amazing! It worked perfectly right out of the box."
Sentiment: Positive

Review: "The package arrived on Tuesday."
Sentiment: Neutral

Review: "It's okay. Does the job but nothing special."
Sentiment: Neutral

Review: "I'm disappointed. It broke after two days of use and customer service was unhelpful."
Sentiment: Critical

Now, classify this review:
Review: "The design is beautiful, but it's much slower than advertised."
Sentiment:
```
*The examples teach the model that "Neutral" isn't just devoid of emotion—it can include faint praise or mixed feelings. This is hard to convey with instructions alone.*

## 🎯 Practice Tasks

Create a few-shot prompt for each task. Provide 2-3 clear examples.

**Task 1: The Email Extractor**
Teach the model to extract specific information from a messy text.
*   **Final Input:** `"Hey Sarah, just confirming our meeting tomorrow at 3:00 PM at Café Luna. Bring the quarterly reports! - Tom"`
*   **Desired Output:** `{ "action": "bring reports", "time": "3:00 PM", "location": "Café Luna" }`
*   **Your Job:** Create 2-3 examples of different messy inputs and the desired JSON output to teach the model this pattern.

**Task 2: The Style Mimic**
Teach the model to write in a very specific style.
*   **Final Input:** `Write a short weather forecast for Seattle.`
*   **Desired Output:** A forecast written in the style of a pirate.
*   **Your Job:** Provide 2-3 examples of other topics written in a pirate's style (e.g., a traffic report, a cooking recipe).

**Task 3: The Concept Explainer**
Teach the model a specific framework for explaining concepts.
*   **Final Input:** `Explain 'blockchain' using this framework.`
*   **Desired Framework:** 1. Explain it in one sentence. 2. Use a simple analogy. 3. List one pro and one con.
*   **Your Job:** Provide examples for other concepts (e.g., 'cloud computing', 'AI') explained using this exact 3-step framework.

## 🔍 Analysis & Reflection

1.  **Quality vs. Quantity:** How many examples were needed to get consistent results? Was 2 enough, or did you need 3?
2.  **Example Choice:** How did the choice of examples impact the output? What would happen if you provided a bad example?
3.  **Comparison:** Try one task first with zero-shot (just instructions) and then with few-shot. How drastic was the improvement?

Few-shot prompting is your tool for achieving high reliability and specific formatting. It's like giving your assistant a template to follow.