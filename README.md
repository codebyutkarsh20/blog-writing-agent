# Blog Writing Agent

A fully agentic blog writing system powered by LangGraph, OpenAI, and Gemini.

## Features

- **Agentic Workflow**: Uses a defined graph (Router -> Research -> Orchestrator -> Workers -> Reducer) to generate high-quality blog content.
- **Web Research**: Integrates with Tavily to fetch up-to-date information.
- **Image Generation**: Automatically plans and generates relevant diagrams or images using Gemini (with fallback to placeholders).
- **Streamlit UI**: Clean interface to input topics, view the drafting progress, and download the final markdown bundle.

## Prerequisites

- Python 3.9+
- API Keys:
    - OpenAI (for text generation)
    - Tavily (for research)
    - Google Gemini (for image generation)

## Setup

1. **Clone the repository** (if you haven't already):
   ```bash
   git clone <repository_url>
   cd blog-writing-agent
   ```

2. **Install Dependencies**:
   It is recommended to use a virtual environment.
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. **Configure Environment**:
   Copy the example environment file and add your keys.
   ```bash
   cp .env.example .env
   ```
   Open `.env` in your editor and fill in your API keys.

## Usage

1. **Start the Interface**:
   ```bash
   streamlit run bwa_frontend.py
   ```

2. **Generate a Blog**:
   - Enter a topic in the sidebar.
   - Select an "As-of date" (useful for news roundups).
   - Click "Generate Blog".
   - Watch the agent plan, research, write, and create images in real-time.

3. **Download**:
   - Once complete, you can download the raw Markdown or a Zip bundle containing the Markdown and generated images.

## Project Structure

- `bwa_backend.py`: Core logic containing the LangGraph definition, nodes, and LLM interactions.
- `bwa_frontend.py`: Streamlit application file handling the UI and graph streaming.
- `requirements.txt`: Python dependencies.
