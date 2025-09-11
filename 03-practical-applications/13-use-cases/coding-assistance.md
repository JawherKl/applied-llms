# Use Case: Coding Assistance

LLMs have revolutionized developer productivity by serving as AI pair programmers. This guide covers effective patterns for coding assistance.

## 🎯 When to Use Coding Assistance

- **Code generation** from natural language descriptions
- **Debugging** and error explanation
- **Code review** and optimization suggestions
- **Documentation** generation
- **Test writing** and test case generation
- **Learning** new languages or frameworks

## 📝 Prompt Patterns for Coding

### Code Generation
```
Write a [language] function that [requirements]. Include comments and example usage:
```

### Code Explanation
```
Explain what this code does in simple terms:

[Code snippet]
```

### Debugging Help
```
I'm getting this error: [error message]. Here's my code: [code]. 
What's wrong and how do I fix it?
```

### Code Review
```
Review this code for best practices, potential bugs, and improvements:

[Code snippet]
```

## 🎨 Advanced Coding Techniques

### Step-by-Step Implementation
```
Help me implement [feature] step by step. I'll tell you when I'm ready for the next step.
Start with the architecture planning.
```

### Test-Driven Development
```
Write pytest tests for this function first, then I'll implement the function to pass them:

[Function signature and requirements]
```

### Refactoring Assistance
```
Refactor this code to be more Pythonic/maintainable/efficient:

[Code to refactor]
```

### Multi-file Projects
```
I'm building a [type of application] with this structure:
- main.py: entry point
- utils.py: helper functions  
- models.py: data models

Help me implement the authentication module across these files.
```

## ⚠️ Common Challenges & Solutions

**Problem:** Outdated or incorrect code examples
**Solution:** Specify versions and constraints
```
Write Python code using pandas 2.0+ syntax for this data processing task:
[Task description]
```

**Problem:** Overly complex or inefficient solutions
**Solution:** Request specific optimization
```
Write the most efficient version of this algorithm in Rust:
[Algorithm description]
```

**Problem:** Missing context or dependencies
**Solution:** Provide full context
```
Here's my current React component structure: [code]. 
I need to add state management using Redux Toolkit.
```

**Problem:** Security vulnerabilities
**Solution:** Request security review
```
Review this authentication code for security vulnerabilities: [code]
```

## 🧪 Practice Exercise

**Try these coding prompts:**

1. **Code Generation:** "Write a Python function that takes a list of numbers and returns a dictionary with mean, median, and mode"
2. **Debugging:** "Why does this JavaScript code throw 'Cannot read properties of undefined'? [provide code]"
3. **Explanation:** "Explain this regular expression: /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/"
4. **Refactoring:** "Refactor this React component to use hooks instead of class components: [provide code]"

## 📊 Evaluation Criteria for Coding Assistance

- **Correctness:** Code works as intended
- **Best practices:** Follows language conventions
- **Readability:** Clear and well-commented
- **Efficiency:** Optimal algorithms and patterns
- **Security:** No obvious vulnerabilities
- **Completeness:** Handles edge cases appropriately

## 🔒 Security Considerations

- **Never paste sensitive code** (credentials, proprietary algorithms)
- **Validate all generated code** before using in production
- **Be cautious with dependencies** and package recommendations
- **Use code scanning tools** on generated code

## 💡 Pro Tips

- **Provide context** about your existing codebase
- **Specify your experience level** ("Explain like I'm a beginner")
- **Ask for multiple approaches** when unsure of best solution
- **Use iterative refinement** - generate, then ask for improvements
- **Always test generated code** thoroughly

---

**Next Section:** ➡️ **[Prompt Refinement](../14-prompt-refinement.md)**