AIE314 Tutorial 1: Preprocessing Unstructured Data for LLM Applications

Project Description
This project focuses on preprocessing unstructured data from diverse document formats (PDF, Word, Excel, PowerPoint, HTML, EPUB) and constructing a Retrieval-Augmented Generation (RAG) bot that can handle mixed media (text + images). The goal is to enable large language models (LLMs) to reason effectively over structured, semistructured, and unstructured data sources.
Key Components
Data Preprocessing
Extract text from various file types (PDF, DOCX, PPTX, XLSX, HTML).
Convert extracted text into a structured JSON format with metadata (file type, path, extraction date).
Text-to-Image Integration
Embed image captions from PowerPoint slides or PDFs into the context feed for LLMs.
Question-Answering System
A simplified RAG bot using Hugging Face transformers for question answering over extracted data.
How to Run the Code
Prerequisites
Python 3.8+
Required libraries (install via pip):
bashCopy
pip install python-docx python-pptx pandas PyMuPDF beautifulsoup4 transformers
Quick Start
Clone the Repository
bashCopy
git clone https://github.com/AmRo1011/AIE314-Tutorial1  
cd AIE314-Tutorial-1  
Run the Preprocessing Script
Place your documents (PDF, DOCX, etc.) in the ./data folder.
Execute the preprocessing functions:
PythonCopy
# Example: Extract text from a PDF and save to JSON  
file_path = "./data/sample.pdf"  
extracted_text = extract_text_from_file(file_path)  
convert_to_json(file_path, extracted_text, output_path="./data/output.json")  
Run the QA Demo
Test the RAG bot with a sample question:
PythonCopy
question = "What were the key factors leading to King John's excommunication?"  
answer = answer_question(question, extracted_text)  
print(f"Answer: {answer}")  
Architecture
Copy
/project-root  
├── data/                # Input documents and outputs  
│   ├── raw/             # Original PDF/DOCX etc. files  
│   └── processed/       # JSON files with extracted text  
├── src/                 # Source code  
│   ├── preprocessing.py  # Text extraction functions  
│   ├── qa_system.py      # Question-answering pipeline  
│   └── utils.py          # Utility functions (file detection, JSON handling)  
├── README.md  
└── requirements.txt  
Tips for Optimization
Error Handling: Add try-except blocks to handle malformed files.
Performance: Use multiprocessing for simultaneous file extraction.
Scalability: Connect to vector databases like Pinecone for large-scale RAG deployment.
Contribution Guidelines
Fork the repository and create a feature branch.
Add your name to CONTRIBUTORS.md.
Submit a pull request with clear commit messages.
