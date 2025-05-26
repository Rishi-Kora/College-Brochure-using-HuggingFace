# College Brochure Summarizer using Hugging Face & OpenAI

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)  \[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)]

Generate AI-powered listings and summaries of academic programs directly from college and university websites. This tool extracts course catalogs (undergraduate, postgraduate, and other programs) and presents them in a clear, structured format—helpful for students, admission counselors, and educational researchers.

## Table of Contents

* [Features](#features)
* [Demo](#demo)
* [Getting Started](#getting-started)

  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
  * [Configuration](#configuration)
  * [Running the Notebook](#running-the-notebook)
  * [Launching the Gradio App](#launching-the-gradio-app)
* [Usage](#usage)
* [Notebook Structure](#notebook-structure)
* [Model Selection](#model-selection)
* [Troubleshooting](#troubleshooting)
* [Contributing](#contributing)
* [License](#license)
* [Contact](#contact)

## Features

* **Automated Web Extraction**: Scrapes course listings and program details from any college or university website.
* **NLP Summarization**: Leverages state-of-the-art transformer models (GPT-4o-mini, Claude) to parse and organize content.
* **Interactive UI**: Provides a Gradio interface for on-the-fly queries—enter an institution name and URL, choose a model, and view extracted programs.
* **Structured Output**: Separates listings into **Undergraduate**, **Postgraduate**, and **Other Programs** (diplomas, certificates, etc.).

## Demo

![Gradio Interface Screenshot](./demo_screenshot.png)

Access a live demo (expires after one week) when you launch the notebook locally:

```
Running on local URL: http://127.0.0.1:7887
Running on public URL: https://<your-gradio>.gradio.app
```

## Getting Started

### Prerequisites

* **Python 3.8+**
* An **OpenAI API key** (start with `sk-...`) or **Anthropic Claude** credentials.
* Virtual environment (recommended) e.g., `venv` or `conda`.

### Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/Rishi-Kora/College-Brochure-using-HuggingFace.git
   cd College-Brochure-using-HuggingFace
   ```
2. Create and activate a virtual environment:

   ```bash
   python3 -m venv env
   source env/bin/activate     # Linux/Mac
   .\env\\Scripts\\activate  # Windows
   ```
3. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

### Configuration

1. Copy the example environment file:

   ```bash
   cp .env.example .env
   ```
2. Open `.env` and set your API key(s):

   ```ini
   OPENAI_API_KEY=sk-your_openai_key_here
   # (optional) ANTHROPIC_API_KEY=your_claude_key_here
   ```

### Running the Notebook

1. Launch Jupyter or JupyterLab in this directory:

   ```bash
   jupyter notebook
   # or
   jupyter lab
   ```
2. Open `College_Brochure_using_HF.ipynb`.
3. Execute cells sequentially to load libraries, set up prompts, and define helper functions.

### Launching the Gradio App

At the end of the notebook, run the Gradio interface to interactively extract courses:

```python
view.launch(share=True)
```

* Visit the provided local or public URL.
* Enter an institution name and its website URL.
* Select **GPT** or **Claude** as the model.
* Click **Submit** to retrieve the formatted course listings.

## Usage

```python
# Example: Extract courses from Kora AI Tech
for chunk in stream_courses('Kora AI Tech', 'https://www.koraaitech.com/', model='GPT'):
    print(chunk)
```

This will stream and display structured program listings.

## Notebook Structure

* **Imports & Setup**: Loads necessary libraries (`requests`, `BeautifulSoup`, `openai`, `gradio`, etc.).
* **Environment & API Initialization**: Reads `.env`, verifies API key format, and configures the OpenAI/Anthropic clients.
* **Prompt Templates**: Defines `system_prompt` and `get_brochure_courses_user_prompt` for consistent extraction requests.
* **Extraction Functions**:

  * `get_website_text(url)`: Scrapes and cleans raw HTML text.
  * `create_brochure` / `stream_gpt` / `stream_claude`: Call the respective models for synchronous or streaming output.
  * `stream_courses`: High-level function that ties scraping and model streaming.
* **Gradio Interface**: Interactive web UI for live extraction.

## Model Selection

* **GPT-4o-mini** (via OpenAI) for highly coherent outputs.
* **Claude 3 Haiku** (via Anthropic) as an alternative LLM.

Use the dropdown in the Gradio UI to switch models based on preference or API availability.

## Troubleshooting

* **Invalid API Key**: If you see `There might be a problem with your API key`, check your `.env` and ensure the key begins with `sk-` and has no extra spaces.
* **Missing Dependencies**: Run `pip install -r requirements.txt` and verify versions.
* **Gradio Errors**: Upgrade with `pip install --upgrade gradio`.

## Contributing

Contributions are welcome! Please:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -m 'Add feature'`).
4. Push to your branch (`git push origin feature/YourFeature`).
5. Open a Pull Request.

Please follow the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/).

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Contact

Maintained by **Rishi Kora**. Open an issue or reach out via [GitHub](https://github.com/Rishi-Kora).
