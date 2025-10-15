# The Fundamentals of Working with LLM API

A hands-on workshop for learning how to work with Large Language Model APIs. This notebook-based tutorial teaches you how to interact with OpenAI's GPT models through direct HTTP API calls, covering everything from basic prompts to production-ready implementations.

## What You'll Learn

This workshop provides practical experience with:

- Making direct API calls using Python's `requests` library (no SDK dependencies)
- Understanding tokens, costs, and reasoning models (GPT-5 vs GPT-4o)
- Crafting effective prompts and managing multi-turn conversations
- Implementing tool calling and function execution
- Handling structured outputs, streaming responses, and multimodal inputs
- Production best practices: error handling, rate limits, and monitoring

## Target Audience

- Developers new to LLM APIs
- Engineers wanting to understand API mechanics without SDK abstractions
- Teams building LLM-powered applications

## Prerequisites

- Python 3.8 or higher
- Basic Python knowledge
- API access credentials (DIAL/Azure OpenAI)

## Installation

### Option 1: Using uv (Recommended)

```bash
# Install uv package manager
curl -LsSf https://astral.sh/uv/install.sh | sh

# Install all dependencies
uv sync

# Start Jupyter notebook
uv run jupyter notebook foundations.ipynb
```

### Option 2: Using pip

```bash
# Create virtual environment
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate

# Install dependencies
pip install requests jupyter ipykernel

# Start Jupyter notebook
jupyter notebook foundations.ipynb
```

## Configuration

Set these environment variables before running the notebook:

```bash
export DIAL_API_KEY="your-api-key"
export DIAL_API_ENDPOINT="https://ai-proxy.lab.epam.com"
export DIAL_API_VERSION="2024-10-21"
export DIAL_DEPLOYMENT="gpt-5-mini-2025-08-07"
export DIAL_GPT4O_DEPLOYMENT="gpt-4o-mini-2024-07-18"
```

Alternatively, you can set these in the notebook's first code cell.

## Workshop Content

### Part 0: Introduction

Understanding LLM APIs, the input-process-output paradigm, and the difference between reasoning (prompts) and actions (tool calling).

### Part 1: Setup & First API Call

Learn the Chat Completions API structure and make your first API call using Python's requests library.

### Part 2: Understanding Tokens & Costs

Explore token types (input, output, reasoning), pricing models, and how to detect truncation.

### Part 3: Prompts & Model Parameters

Master prompt engineering techniques: few-shot learning, chain-of-thought reasoning, and parameter tuning.

### Part 4: Multi-Turn Conversations

Manage conversation history manually and understand stateless API mechanics.

### Part 5: Tool Calling & Function Calling

Implement the 5-step tool calling workflow with single and multiple tools.

### Part 6: Context Engineering & Limitations

Handle context window limits, implement summarization, and use progressive disclosure patterns.

### Part 7: Structured Outputs

Extract structured data using JSON mode and strict JSON schemas.

### Part 8: Streaming Responses

Implement real-time token streaming using Server-Sent Events.

### Part 9: Vision & Multimodality

Analyze images with GPT-4o and understand detail level trade-offs.

### Part 10: Production Readiness

Implement error handling, exponential backoff for rate limits, usage monitoring, and model selection strategies.

## Models Used

**GPT-5 Series (Reasoning Models):**

- gpt-5-mini-2025-08-07 (primary workshop model)
- gpt-5-2025-08-07 (full reasoning, 272K context)
- gpt-5-nano-2025-08-07 (edge/mobile deployments)

**GPT-4o Series (Standard Models):**

- gpt-4o-mini-2024-07-18 (comparison model)
- gpt-4o-2024-11-20 (latest multimodal)

## Workshop Duration

Approximately 90 minutes (10 parts, ~9 minutes each)

## Dependencies

This workshop uses minimal dependencies:

- **requests** - HTTP library for API calls
- **jupyter** - Notebook interface
- **ipykernel** - Jupyter kernel support

All other imports (os, json, time, base64, pathlib) are Python standard library modules.

## Key Features

- No SDK dependencies - learn the API directly
- Self-contained demos - each can run independently
- Production-ready patterns - not just toy examples
- Cost-conscious - includes token counting and pricing examples
- Error handling - demonstrates real-world failure scenarios

## Notes

- All code uses direct HTTP requests via the `requests` library
- Examples use DIAL API (wrapper for Azure OpenAI)
- Token limits are set appropriately for live demonstrations
- All demos include cost estimation based on current pricing

## License

Educational use only.
