# AI Code Assistant (Agent with Tool Calling)
A command-line AI agent built in Python that uses Google's Gamini API to process user prompts, call external tools, and iteratively refine responses.

## Features
  - CLI-based interaction with natural language prompts
  - Integration with Gemini API
  - Function/tool calling system
  - Iterative reasoning loop with controlled execution (MAX_ITERS)

## How It Works
  - User provides a prompt via CLI
  - Model analyzes the prompt and decides whether to call a function
  - If needed, a tool is executed via call_function
  - The result is passed back to the model
  - The loop continues until a final response is generated
