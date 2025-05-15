
# Advanced Text Summarization Using LangChain and LLMs

## Project Overview

This project demonstrates a robust and flexible pipeline for summarizing speeches and documents using LangChain and Groq's Gemma language model. It supports summarization of plain text, PDF files, and is adaptable for large documents through multiple summarization techniques including Stuff, Map-Reduce, and Refine. The system is capable of translating summaries into multiple languages, making it useful for multilingual and scalable summarization applications.

## What I Built

I developed a multi-method text summarization system using Groq's Gemma-2 9B model and LangChain. The system processes input in different formats like typed speeches and uploaded PDFs, splits and summarizes content, and can translate the result into other languages like French or Telugu. It explores various summarization strategies to compare performance and structure.

## Tools and Technologies Used

- LangChain  
- Groq API with Gemma-2 9B model  
- PromptTemplate and LLMChain  
- LangChain summarize chains: Stuff, Map-Reduce, Refine  
- PyPDFLoader for PDF parsing  
- RecursiveCharacterTextSplitter for chunking large documents  
- Python dotenv for API key management  
- Python, Jupyter Notebook

## Process Explanation

### 1. Model and Environment Setup
- Loaded the Groq API key from environment using `dotenv`.
- Initialized the `ChatGroq` object with the Gemma-2 9B model.

### 2. Basic Summarization (Direct Prompt)
- A speech string was defined in plain text.
- Created system and human messages instructing the LLM to generate a summary.
- Used token counting to verify input size.

### 3. Multilingual Prompt Template
- Built a `PromptTemplate` to summarize a speech and translate the summary into another language.
- Connected it to an `LLMChain` to generate multilingual summaries (French, Telugu).

### 4. Summarizing a PDF Document
- Loaded the "I Have a Dream" speech in PDF format using `PyPDFLoader`.
- Used the `stuff` summarization method to condense the content as a single unit.

### 5. Map-Reduce Summarization
- Split the document using `RecursiveCharacterTextSplitter`.
- Defined separate prompts for the mapping and combining phases.
- Combined partial summaries into a final cohesive and structured output.

### 6. Refine Summarization
- Used `load_summarize_chain` with the refine strategy to iteratively improve the summary as new chunks were introduced.

### 7. Exploration for YouTube Integration
- Tested basic `pytube` functionality to retrieve video data as a future step toward summarizing YouTube video content.

## Final Outcome

The project successfully produced accurate, concise, and multilingual summaries using various LangChain summarization techniques. It supports document-based inputs and sets up a solid foundation for expanding into other content formats like videos or web pages.

## Use Cases

- Summarizing speeches, reports, and articles  
- Educational tools for language learners  
- Summarization in multiple languages  
- Document preprocessing for downstream NLP tasks  
- Political speech summarization and analysis  

## Installation

1. Clone the repository:

```bash
git clone https://github.com/DevaPriya5102/text-summarization-langchain.git
cd text-summarization-langchain
```

2. Set up a virtual environment:

```bash
python -m venv env
source env/bin/activate  # On Windows use `env\Scripts\activate`
```

4. Create a `.env` file:

```
GROQ_API_KEY=your_groq_api_key
```

## Usage

Open the Jupyter notebook and run each cell sequentially. You can modify the speech input, PDF file, or the language to see results in different formats.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more information.
