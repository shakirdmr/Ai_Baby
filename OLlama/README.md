
# Ollama Setup Guide

## What We've Done So Far

### 1. Download Ollama
- Downloaded and installed Ollama from [ollama.ai](https://ollama.ai)
- Completed the installation process for your operating system
- Downloaded Ollama from the official website and installed it
- Ran `ollama pull llama2` in the terminal to download the model locally

### 2. Start Ollama Server
- Started the Ollama server to expose the API on a local PORT (default: 11434)
- Server now listens for requests at `http://localhost:11434`

### 3. Fetch Request Implementation
- Created a fetch request to communicate with the Ollama API
- Sent POST requests to the `/api/generate` endpoint with model name and prompt parameters
- Received streamed responses from the locally running model

### 2. Initial Setup
- Verified the installation by running `ollama --version`
- Started the Ollama service/daemon

### 3. Fetch Models
- Used `ollama pull <model-name>` to download models (e.g., `ollama pull llama2`)
- Models are now cached locally and ready to use

### Next Steps
- Run models with `ollama run <model-name>`
- Integrate with applications via the API

---

## html.html — Browser UI for Ollama

A minimal single-file HTML interface that lets you chat with a locally running Ollama model directly from the browser.

### What's in the file

| Element | Purpose |
|---|---|
| `<input id="input">` | Text field where the user types their prompt |
| `<button onclick="ask()">` | Triggers the AI request when clicked |
| `<pre id="output">` | Displays the model's response |

### How it works

1. **User types a prompt** into the input field and clicks **Ask**.
2. The `ask()` function reads the input value and calls `oLlamaRequest(prompt)`.
3. `oLlamaRequest` sends a **POST** request to the locally running Ollama server:
   ```
   POST http://localhost:11434/api/generate
   ```
   with this JSON body:
   ```json
   { "model": "llama3:latest", "prompt": "<user input>", "stream": false }
   ```
4. The response JSON is parsed and `data.response` (the model's answer) is written into the `<pre>` output element.

### Key details
- **Model used:** `llama3:latest` — Ollama must have this model pulled (`ollama pull llama3`)
- **Streaming:** disabled (`stream: false`) — waits for the full response before displaying
- **No dependencies:** pure HTML + vanilla JavaScript, no libraries or build step needed
- **How to run:** open `html.html` directly in a browser while the Ollama server is running
