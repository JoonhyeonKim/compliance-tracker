
# Korean ESG Compliance Tracker

This project aims to build a compliance tracker focused on the green industry in South Korea, specifically targeting ESG (Environmental, Social, and Governance) regulations. The tool automates data retrieval from key government sources and regulatory bodies, providing actionable insights for companies seeking to stay compliant with evolving regulations in the ESG sector.

## Table of Contents
- [Features](#features)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Technologies Used](#technologies-used)
- [Usage](#usage)
- [Future Work](#future-work)
- [Contributing](#contributing)

## Features
- **Automated Data Retrieval**: Scrapes legislative notices from `입법예고` and environmental PDFs from the Ministry of Environment.
- **Text Summarization and Categorization**: Uses LangChain to generate summaries and categorize compliance information.
- **Real-Time Alerts**: Sends notifications about new regulations or updates that may affect ESG compliance.
- **User Interaction via Chatbot**: Enables users to ask compliance-related questions and receive AI-generated responses.

## Project Structure

```plaintext
compliance-tracker/
│
├── data_ingestion/          # Data Collection Layer
│   ├── pdfs/                # Raw PDFs
│   ├── scripts/             # PDF and web scraping scripts
│   └── extracted_text/      # Extracted text from PDFs
│
├── processing_pipeline/      # NLP Processing Layer
│   ├── summarization/       # LangChain workflows for summarization
│   ├── categorization/      # Scripts for categorizing regulatory text
│   └── ocr/                 # OCR-related scripts for image-based PDFs
│
├── business_logic/           # Business Logic Layer
│   ├── notifications/       # Scripts for sending alerts
│   ├── compliance_roadmap/  # Code for creating compliance action plans
│   └── preferences/         # User preference handling scripts
│
├── user_interface/           # User Interaction and Response Layer
│   ├── dashboard/           # Frontend code (e.g., Streamlit/Gradio)
│   └── chatbot/             # Chatbot for handling user queries
│
├── notifications/            # Notification and Integration Layer
│   ├── email/               # Email notification scripts
│   ├── sms/                 # SMS notification scripts
│   └── slack/               # Slack integration scripts
│
├── backend/                  # Backend and Hosting Layer
│   ├── server/              # Backend server code
│   └── storage/             # Database or storage setup
│
├── utils/                    # Utility Functions
│   ├── config.py            # Configuration settings (API keys, paths, etc.)
│   └── helpers.py           # Helper functions
│
└── README.md                 # Project description and setup instructions
```

## Getting Started

### Prerequisites
- Python 3.8 or higher
- Basic familiarity with Git and GitHub
- Recommended: `virtualenv` for environment management

### Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/compliance-tracker.git
   cd compliance-tracker
   ```

2. **Set Up a Virtual Environment**
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure .gitignore**
   - Add sensitive files (e.g., `config.py`) and temporary folders (e.g., `pdfs/`) to `.gitignore`.

5. **Add API Keys and Configurations**
   - Update `utils/config.py` with relevant API keys (e.g., LangChain, email/SMS APIs) and paths.

### Setting Up Git and GitHub

1. **Initialize Git**
   ```bash
   git init
   ```

2. **Link to GitHub**
   ```bash
   git remote add origin https://github.com/yourusername/compliance-tracker.git
   git push -u origin main
   ```

## Technologies Used
- **LangChain**: For processing and categorizing regulatory text.
- **BeautifulSoup/Selenium**: For web scraping legislative notices.
- **Tesseract OCR**: For handling scanned PDF documents.
- **OpenAI API**: For summarization and response generation.
- **Streamlit/Gradio**: To build an interactive dashboard and chatbot.

## Usage

1. **Run Data Ingestion Scripts**
   - Download PDF files and extract text with:
     ```bash
     python data_ingestion/scripts/download_pdfs.py
     python data_ingestion/scripts/extract_text.py
     ```

2. **Process and Categorize Data**
   - Summarize and categorize extracted text:
     ```bash
     python processing_pipeline/summarization/run_summarization.py
     ```

3. **Run the User Interface**
   - Launch the dashboard or chatbot:
     ```bash
     streamlit run user_interface/dashboard/app.py
     ```

4. **Receive Notifications**
   - Configure notification preferences and receive alerts via email, SMS, or Slack.

## Future Work
- **Expand to Additional ESG Topics**: Include other sectors as ESG policies evolve.
- **Multi-Language Support**: Add support for English summaries for international audiences.
- **Integration with External APIs**: Incorporate real-time data from additional government and environmental databases.

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request for any improvements or new features.
