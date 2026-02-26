
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
