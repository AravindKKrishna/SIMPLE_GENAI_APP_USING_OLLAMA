# Langpro

A simple Streamlit app that demonstrates a LangChain-based chat interface using the Ollama `gemma:2b` model.

## Features

- Uses `langchain` and `langchain_community` to build a prompt chain
- Loads environment variables with `python-dotenv`
- Runs in Streamlit for an interactive web UI
- Sends user questions to the Ollama model and displays the response

## Requirements

- Python 3.11+ recommended
- Ollama installed and running, with the `gemma:2b` model available
- A `.env` file containing LangChain environment variables

## Installation

1. Clone the repository or copy the project files.
2. Create and activate a virtual environment:

```bash
python -m venv venv
venv\Scripts\activate
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

## Configuration

Create a `.env` file in the project root with the following values:

```env
LANGCHAIN_API_KEY=your_langchain_api_key
LANGCHAIN_PROJECT=your_langchain_project_name
```

If you are only using local Ollama and do not need LangChain tracing, you can still set these variables to valid values or leave them empty.

## Running the App

Start the Streamlit app with:

```bash
streamlit run app.py
```

Then open the local URL shown in the terminal to use the chat interface.

## App Behavior

- The app loads `LANGCHAIN_API_KEY` and `LANGCHAIN_PROJECT` from `.env`
- It creates a system/user chat prompt using `ChatPromptTemplate`
- It sends the prompt to `Ollama(model="gemma:2b")`
- The response is shown on the Streamlit page when a question is entered

## Dependencies

The project uses these Python packages:

- `langchain`
- `python-dotenv`
- `ipykernel`
- `langchain-openai`
- `beautifulsoup4`
- `langchain_community`
- `faiss-cpu`
- `streamlit`

## Notes

- Ensure the Ollama daemon is running and the `gemma:2b` model is installed before launching the app.
- If you want to use a different model, update the `model` parameter in `app.py`.
