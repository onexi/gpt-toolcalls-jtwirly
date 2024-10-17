[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/9wDnMTRl)
# FunctionAgents
Call Function from LLM
# AI Memory Assistant

This project demonstrates the power of "tools" and "tool_calling" in AI applications by implementing a system that can store and analyze memories using OpenAI's GPT model.

## Overview

The AI Memory Assistant is capable of:
1. Storing memories in a simple CSV file
2. Retrieving stored memories
3. Analyzing memories for word count, character count, and sentiment

The system uses OpenAI's GPT model to interpret user requests and decide which functions to call.

## Components

1. `server.js`: The main server file that handles API routes and interactions with OpenAI.
2. `functions/scratchpad.js`: A function for storing and retrieving memories.
3. `functions/analyzeMemory.js`: A function for analyzing the content of memories.
4. `public/index.html`: A simple front-end interface for interacting with the AI.

## New Functionality

We've added the following new features:

1. **Memory Analysis**: The `analyzeMemory` function can now provide word count, character count, and sentiment analysis for a given memory.
2. **Multi-step Function Calling**: The system can now chain multiple function calls together, allowing for more complex operations.

## How to Use

1. Start the server by running `node server.js`.
2. Open a web browser and navigate to `http://localhost:3000`.
3. Use the interface to interact with the AI. Here are some example prompts:

   - "Store this memory: I had a great day at the park today."
   - "Retrieve the memory about the park."
   - "Analyze the memory about the park."

4. The AI will interpret your request, call the appropriate functions, and return the results.

## Function Calling Process

1. The user's message is sent to the OpenAI API along with the available functions.
2. The AI model decides which function(s) to call based on the user's request.
3. The server executes the called function(s) and sends the results back to the AI.
4. This process can repeat up to 3 times per request, allowing for multi-step operations.
5. The final result is returned to the user.

## Extending the System

To add new functionality:

1. Create a new JavaScript file in the `functions` directory.
2. Export an `execute` function and a `details` object describing the function.
3. The new function will automatically be available to the AI for use.

## Note

This system is a demonstration and uses a simple CSV file for storage. In a production environment, you would want to use a more robust database system.
