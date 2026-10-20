# 🔬 Multi-Agent Research System

### An AI-Powered Research Assistant Using LangChain

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![LangChain](https://img.shields.io/badge/LangChain-Framework-green)](https://www.langchain.com/)
[![Streamlit](https://img.shields.io/badge/Streamlit-Web%20App-FF4B4B?logo=streamlit&logoColor=white)](https://streamlit.io/)
[![OpenAI](https://img.shields.io/badge/OpenAI-LLM-black?logo=openai)](https://platform.openai.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 📌 Overview

The **Multi-Agent Research System** is an AI-powered application that automates the research and report-generation process using multiple specialized AI agents.

Instead of relying on a single large language model (LLM) call, the system divides research into distinct stages: web searching, content extraction, report writing, and quality evaluation. Each component has a specific responsibility, helping produce structured and informative research reports.

The application combines **LangChain, OpenAI, Tavily Search API, and Streamlit** to provide an interactive research experience.

## ✨ Key Features

- 🤖 **Multi-Agent Architecture:** Specialized agents handle different stages of the research workflow.
- 🔎 **Web Search Integration:** Retrieves relevant information from the web using the Tavily Search API.
- 📄 **Content Extraction:** Extracts readable text from relevant web pages for further analysis.
- ✍️ **Automated Report Generation:** Converts collected information into structured research reports.
- 🧐 **AI-Powered Critique:** Evaluates generated reports and provides feedback on their quality.
- 🖥️ **Interactive Web Interface:** Explore the research workflow through a Streamlit application.
- 📥 **Report Export:** Download generated research reports in Markdown format.
- 🔐 **Environment-Based Configuration:** Keep API credentials outside the application source code.

## 🏗️ System Architecture

The research workflow consists of four major stages:

```text
            Research Topic
                  |
                  v
          +----------------+
          |  Search Agent  |
          +----------------+
                  |
                  v
          +----------------+
          |  Reader Agent  |
          +----------------+
                  |
                  v
          +----------------+
          |  Writer Chain  |
          +----------------+
                  |
                  v
          +----------------+
          |  Critic Chain  |
          +----------------+
                  |
                  v
          +----------------+
          | Final Research |
          |     Report     |
          +----------------+
```

### 🔄 How It Works

**1. Search Agent**

- Searches the web for relevant information.
- Collects useful search results, including titles, URLs, and snippets.

**2. Reader Agent**

- Identifies relevant web pages.
- Extracts readable content from the selected sources.
- Provides additional context for report generation.

**3. Writer Chain**

- Processes the retrieved information.
- Uses an LLM to synthesize the research findings.
- Generates a structured report in Markdown format.

**4. Critic Chain**

- Reviews the generated report.
- Identifies potential weaknesses and areas for improvement.
- Provides a quality score and feedback.

**5. Final Output**

The application presents the generated report and critique through the Streamlit interface, with an option to download the report.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| LangChain | Agent orchestration and LLM integration |
| OpenAI | Language model for research and report generation |
| Tavily Search API | Web search and information retrieval |
| Requests | HTTP requests for web content |
| BeautifulSoup4 | HTML parsing and text extraction |
| Streamlit | Interactive web application |
| python-dotenv | Environment variable management |

## 📁 Project Structure

```text
Multi-agent-research-system/
│
├── app.py              # Streamlit web application
├── agents.py           # Agent and LLM chain definitions
├── tools.py            # Web search and scraping utilities
├── pipeline.py         # Research pipeline execution
├── requirements.txt    # Python dependencies
├── .env                # API credentials (create locally)
├── .gitignore          # Files excluded from Git
└── README.md           # Project documentation
```

## 🚀 Getting Started

### Prerequisites

Before running the project, ensure you have:

- Python 3.10 or later
- Git
- An OpenAI API key
- A Tavily API key

### 1. Clone the Repository

```bash
git clone https://github.com/Rohitomar19/Multi-agent-research-system.git
cd Multi-agent-research-system
```

### 2. Create a Virtual Environment

**Windows (PowerShell):**

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

**macOS / Linux:**

```bash
python -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file in the root directory and add your API credentials:

```env
OPENAI_API_KEY=your_openai_api_key
TAVILY_API_KEY=your_tavily_api_key
```

Replace the placeholder values with your own API keys.

**Security note:** Never commit your `.env` file or expose your API keys in public repositories. Add `.env` to `.gitignore`.

### 5. Run the Application

Start the Streamlit web application:

```bash
streamlit run app.py
```

Once the application starts, open the local URL displayed in your terminal, typically:

```text
http://localhost:8501
```

## 💡 How to Use

1. Launch the Streamlit application.
2. Enter a research topic, such as *"Recent advancements in Generative AI."*
3. Start the research pipeline.
4. Allow the agents to retrieve information, analyze content, and generate a report.
5. Review the final research report and the critic's feedback.
6. Download the report in Markdown format if the export option is available.

## 🧪 Example Research Topics

Try researching topics such as:

- Generative AI and Large Language Models
- Applications of machine learning in healthcare
- Retrieval-Augmented Generation (RAG)
- Multi-agent AI systems
- Recent developments in natural language processing
- AI applications in finance and business analytics

## 🧠 Concepts Demonstrated

This project demonstrates practical applications of:

- **Agentic AI:** Dividing a complex task among specialized components.
- **LLM Orchestration:** Connecting language models with tools and processing chains.
- **Retrieval-Augmented Research:** Grounding generated reports in retrieved information.
- **Web Scraping:** Extracting useful content from web pages.
- **Prompt Engineering:** Guiding LLMs to generate structured research reports.
- **AI Evaluation:** Reviewing generated content and identifying possible improvements.
- **Workflow Automation:** Combining multiple stages into a repeatable pipeline.

## 🔮 Future Improvements

Potential enhancements include:

- Adding support for multiple LLM providers.
- Introducing parallel research agents for faster information gathering.
- Improving citation verification and factual consistency checks.
- Adding persistent research history and caching.
- Supporting PDF uploads and research on academic papers.
- Adding configurable research depth and source limits.
- Implementing automated evaluation metrics for report quality.
- Supporting additional export formats such as PDF.

## ⚠️ Limitations

- Report quality depends on the language model and retrieved sources.
- Web search and model generation require valid API credentials and may incur usage costs.
- Web pages may contain incomplete, outdated, or unreliable information.
- Critic feedback does not guarantee that every claim is factually correct.
- Generated reports should be checked against their original sources before being used for academic or professional decisions.

## 🤝 Contributing

Contributions, suggestions, and bug reports are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Make your changes and test them.
4. Commit your changes with a descriptive message.
5. Open a pull request.


- GitHub: [@Rohitomar19](https://github.com/Rohitomar19)

---

⭐ If you find this project useful, consider giving the repository a star!

*Built to explore the possibilities of Agentic AI, LLM orchestration, and automated research.*
