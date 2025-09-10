# 9. Prompting Basics: The Art of Instruction

Prompting is how we program LLMs. Unlike traditional programming with exact syntax, we use natural language to guide the model's behavior. This lesson covers the fundamental building blocks of any good prompt.

## The Core Structure of a Prompt

A powerful prompt often contains these four elements:

1.  **Instruction:** The specific task you want the model to perform.
2.  **Context:** External information or additional context that steers the model to better responses.
3.  **Input Data:** The question or content we want the model to process.
4.  **Output Indicator:** The desired type or format of the output.

**Example:**
```
### INSTRUCTION ###
Translate the following text from English to French.

### CONTEXT ###
The text is a technical documentation for software engineers.

### INPUT DATA ###
"The singleton pattern restricts the instantiation of a class to one single object."

### OUTPUT INDICATOR ###
Provide only the translated text, nothing else.
```

## 1. Start Simple: The Instruction

The most basic prompt is a direct instruction or question.

*   **Simple Instruction:** `Explain the concept of recursion in programming.`
*   **Simple Question:** `What is the capital of France?`

**Try it yourself:** Use a simple instruction to ask the model to define a term from your field of work.

## 2. The Power of Role-Playing

One of the most effective ways to improve output quality is to assign the model a **role**. This provides built-in context about the expertise and style you expect.

*   **Basic:** `Explain quantum computing.`
*   **With Role:** `Act as a university professor who is an expert in physics. Explain quantum computing to a freshman student.`

**Common Roles:**
*   `Act as a senior software engineer...`
*   `You are a helpful and creative assistant...`
*   `You are a strict, concise technical writer...`

**Try it yourself:** Ask the model to explain a concept first as a expert, and then as a explainer to a 10-year-old. Notice the difference in language and detail.

## 3. Provide Context and Examples

LLMs are fantastic pattern matchers. Providing examples in your prompt is called **few-shot prompting** and is incredibly powerful for teaching the model the exact format and style you want.

**Zero-Shot Prompt (No examples):**
```
Classify the sentiment of this text: "This product is absolutely amazing!"
Sentiment:
```

**Few-Shot Prompt (With examples):**
```
Classify the sentiment of the text as positive, negative, or neutral.

Text: "I love this place, the food is great!"
Sentiment: positive

Text: "The service was terribly slow and rude."
Sentiment: negative

Text: "They delivered my package at 3 PM."
Sentiment: neutral

Text: "This product is absolutely amazing!"
Sentiment:
```

**Try it yourself:** Use a few-shot prompt to classify movie genres or to convert questions into a specific JSON format.

## 4. Control the Format

Be explicit about how you want the answer structured. The model can generate plain text, JSON, XML, lists, tables, and more.

*   `...Present the answer in a bulleted list.`
*   `...Format the output as a JSON object with keys 'name', 'email', and 'phone'.`
*   `...Summarize the following text in exactly three sentences.`

**Try it yourself:** Ask the model to generate a list of 5 book recommendations and output them in a Markdown table with columns for Title, Author, and Year.

## 5. Iterate and Refine

Your first prompt is a starting point. If the output isn't quite right, refine your instructions.
*   **Too verbose?** Add: `Be concise.` or `Answer in one sentence.`
*   **Not formal enough?** Add: `Use a professional tone.`
*   **Missing key points?** Add: `Be sure to cover [KEY TOPIC].`

## 🧪 Exercise: The Prompt Evolution

1.  **Start Simple:** `Tell me about Docker.`
2.  **Add a Role:** `Act as a DevOps engineer. Tell me about Docker.`
3.  **Define Audience:** `Act as a DevOps engineer. Explain Docker to a front-end developer.`
4.  **Specify Format:** `Act as a DevOps engineer. Explain Docker to a front-end developer. Use a analogy and provide three key benefits in a bulleted list.`

Copy each prompt into your LLM of choice and observe how the output improves with each iteration.

---

**Next Up:** ➡️ **[Prompting Frameworks: Structured Approaches for Complex Tasks](./10-prompting-frameworks.md)**
> Now that you know the basics, let's learn structured frameworks used by experts to solve complex problems.