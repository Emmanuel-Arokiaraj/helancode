# helancode
An Open Source light weight, memory Safe LLM Harness Made for Coding and Automation Task Implementations. Made with Rust

## System Design

#### Functional Requirements:

- Should be able to support Autonomous Coding Tasks With Large Codebases.
- Should be able to Run Automation Workflows defined by the users inside the workspace as a very lightweight non-blocking process.
- Should have support on maintaining sessions and their chat history
- Should be able to Support a Sophiticated Terminal UI for Coding Purposes.
- Should have a Support to Plug into MCP Servers.
- Should be a sophisticated platform in which user can add their own skills, tools and subagents.
- Should support Abilities to Connect to Vector Databases - Rag as a Service (Does not Come under OpenSource)

#### Non-Functional Requirements:
- Should support Atleast 4 Most Commonly Used LLM Providers - (OpenAI - Classic, Anthropic, Azure OpenAI, Claude, Gemini, Ollama Providers)
- Should have extensibility to allocate different models and different reasoning types on different tasks of the pipeline - for example compacting/summarizing responses, code generation/response generation, verification engine. context engine model etc.,
- Should have extensibility on choosing different models based on the agent mode - Ask, Plan, Implement/Agentic.
- Should have a Robust Traffic Shaping and Model Routing System.
- Should have Observability on Cost, Tokens and Request and Other Important Metrics of the system.
