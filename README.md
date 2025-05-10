# College-Brochure-using-HuggingFace
Generate AI-powered summaries for college brochures using Hugging Face models to help students make informed decisions faster.

## 📌 Project Overview

This project leverages NLP models from [Hugging Face Transformers](https://huggingface.co/) to extract and summarize key information from college brochures.
Whether it's academic programs, placement statistics, or campus life—this tool helps distill dense brochures into concise insights.

## 📁 Repository Structure

```bash
├── College_Brochure_using_HF.ipynb        
└── README.md                              
```

## 🔧 Getting Started

### Dependencies
Make sure to install the following Python libraries:
```bash
!pip install transformers torch sentencepiece accelerate
```

### Running the Notebook
1. Upload or extract brochure content as text.
2. Use a summarization pipeline with Hugging Face models like `t5`, `bart`, or `distilbart`.
3. Execute the summarization pipeline.
4. View or download summarized content for review.

## 🧠 Features
- 📚 Automatically extracts key content from brochures
- ✨ Summarizes using state-of-the-art transformer models
- 🧾 Outputs structured, readable summaries
- 🔍 Ideal for comparing multiple colleges quickly

## 💡 Example Use Cases
- College comparison platforms
- Admission counselors
- Educational research & guidance tools

## 🔬 Technology Stack
- Python
- Hugging Face Transformers
- Torch / Accelerate

## 📃 License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

## 🙏 Acknowledgements
- Hugging Face for their incredible NLP models
- Academic institutions that publish public brochures
