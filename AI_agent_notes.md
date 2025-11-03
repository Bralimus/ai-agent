# Building an AI Agent in Python

**THIS AI AGENT IS NOT SAFE TO USE FOR ADVANCED TASKS**

* Creating an agent that:
    Accepts a coding task
    Chooses from a set of predefined functions to work on the task
    Repeats until the task is complete - or fails miserably

```Python
> uv run main.py "fix my calculator app, its not starting correctly"
# Calling function: get_files_info
# Calling function: get_file_content
# Calling function: write_file
# Calling function: run_python_file
# Calling function: write_file
# Calling function: run_python_file
# Final response:
# Great! The calculator app now seems to be working correctly. The output shows the expression and the result in a formatted way.
```

## Creating project

uv init your-project-name
cd your-project-name
uv venv
    * add .venv/ to .gitignore
source .venv/bin/activate
uv add google-genai==1.12.1
uv add python-dotenv==1.1.0
* use uv run main.py to run project


## Notes
When using an LLM, they are price per token
Tokens are roughly 4 characters
The price for a prompt is based on the number of tokens in the input and output

LLMs are not "one-shot" Q-A. Past conversation has a "role".

It's important LLM knows that the action it took actually worked - always provide feedback after it executes a function
    Printing or returning something it can quantify

*System Prompt*
This is a special prompt that goes at the beginning of the conversation that carries more weight than a typical user prompt.
It sets the tone for the conversation, can be used to:
    Set the personality of the AI
    Give instructions on how to behave
    Provide context for the conversation
    Set the "rules" for the cconversation

Technically when providing the LLM access to a function it does not call that function, it describes which function it wants to call and what arguments
    Then we call the function and return the result to the LLM
    We are using the LLM as the decision-making engine, but we are still running the code
Using types.FunctionDeclaration we can build a "declaration" or "schema" for a function
    Just tells the LLM how to use the function

## Security
These are basic security - not sufficient for an actual production AI agent
Always make sure LLM is only accessing specific directory
Add a 30s timeout to prevent it from running indefinitely

## Extend Project Options
See if you can get it to:
* Fix harder and more complex bugs
* Refactor sections of code
* Add entirely new features

You can also try:
* Other LLM providers
* Other Gemini models
* Giving it more functions to call
* Other codebases (Commit your changes before running the agent so you can always revert!)
