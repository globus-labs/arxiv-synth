# ArXiv Synth: Summarizing arXiv Papers with Large Language Models

![Alt text](./arxiv-synth.png)

ArXiv Synth is a project that utilizes large language models to summarize and analyze content from arXiv based on a given query. It fetches papers from arXiv, processes them, and generates summaries using OpenAI's and Anthropic's language models. In its current form, the project is meant as an educational demonstration of the capabilities, not as a research tool.

## Features

- Fetches papers from arXiv based on a user-defined query
- Caches fetched papers in a JSONL file for future reference
- Generates summaries of the fetched papers using OpenAI's and Anthropic's language models
- Provides a streaming summary using Anthropic's Python SDK

## Setup

1. Install the required dependencies:
   ```
   pip install arxiv openai anthropic
   ```

2. Set up API keys:
   - Obtain an API key from OpenAI and assign it to the `openai_api_key` variable.
   - Obtain an API key from Anthropic and assign it to the `claude_api_key` variable.

## Usage

1. Define your search query and other parameters in the "Collect Data from ArXiv" section of the code.

2. Run the code to fetch papers from arXiv based on the specified query. The fetched papers will be cached in a JSONL file.

3. The code will generate summaries of the fetched papers using OpenAI's and Anthropic's language models. The summaries will be displayed using Markdown formatting.

4. To get a streaming summary using Anthropic's model, run the "Get Anthropic Streaming Summary++" section of the code. The summary will be updated in real-time as the model generates the output.

## Functions

- `fetch_papers(query, category=None, n_papers=20)`: Fetches papers from arXiv based on the provided query and other optional parameters.
- `write_papers(papers, filename="./arxiv_papers.jsonl")`: Writes the fetched papers to a JSONL file for caching.
- `get_openai(prompt, model="gpt-3.5-turbo-0125", api_key=None, system_prompt="You are a helpful assistant.", max_tokens=2000, temperature=0.8)`: Generates a summary using OpenAI's language model.
- `get_anthropic(prompt, model="claude-3-haiku-20240307", api_key=None, system_prompt="You are a helpful assistant.", max_tokens=2000, temperature=0)`: Generates a summary using Anthropic's language model.
- `generate_streaming_markdown(input_for_summary, model="claude-3-haiku-20240307", system_prompt="You are a helpful assitant", max_tokens=2000, temperature=0)`: Generates a streaming summary using Anthropic's model.

## Customization

You can customize the search query, number of papers to fetch, and other parameters in the "Collect Data from ArXiv" section of the code. Additionally, you can modify the system prompts and model parameters for OpenAI and Anthropic in the respective function calls.

## License

This project is open-source and available under the [MIT License](LICENSE).