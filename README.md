# Week 4: Math Agent (ReAct)

## Overview
This project implements a math agent using a ReAct loop that solves questions step by step using external tools.

The agent reads questions from a markdown file and uses tool calls to compute answers and retrieve product pricing.

---

## Demo Video
https://your-youtube-link-here

---

## Tools Used

### Calculator Tool
Evaluates mathematical expressions such as multiplication, exponentiation, and division using a helper function.

### Product Lookup Tool
Reads from `products.json` and returns product prices. If a product is not found, it returns a list of available products.

---

## How It Works
The agent follows a ReAct pattern:
- Reasons about the problem
- Decides which tool to use
- Executes the tool
- Continues reasoning until a final answer is produced

Each step is shown in the trace output:
- Reason
- Act (tool call)
- Result

---

## Reflection
During this assignment, I implemented a tool-based agent using a ReAct loop.

Initially, the agent failed product-related questions because the product lookup tool was not implemented. After implementing this tool, the agent was able to correctly retrieve product prices and complete all questions.

I also encountered challenges with API limits and environment setup. I initially used Google AI but hit quota limits, and later switched to OpenAI to complete execution.

Through this process, I learned how agents use tools for reasoning, how to structure step-by-step problem solving, and the importance of validating outputs using trace logs.

---

## Process and Key Decisions
- Selected an API provider and configured environment variables
- Implemented the `product_lookup` tool using `json.load`
- Updated the system prompt to ensure consistent tool usage
- Added a delay between requests to manage rate limits
- Verified outputs using trace logs

These decisions ensured the agent ran successfully and produced correct results.

---

## Git Workflow Summary
- Forked the starter repository from GitHub
- Cloned the repository locally using VS Code
- Created and configured the `.env` file
- Implemented the `product_lookup` tool in `agent.py`
- Tested the agent using terminal execution
- Committed changes incrementally during setup and debugging
- Pushed final working version to GitHub

### Key Commits
- Initial repository setup
- Environment configuration
- Product lookup implementation
- Bug fixes and dependency resolution
- Final working version

---

## Setup
1. Install dependencies  
2. Add your API key to `.env`  
3. Run:

```bash
python3 agent.py