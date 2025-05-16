# MarketingTracker – AI-Powered Document & Email Insights

**MarketingTracker** is an AI-powered document assistant designed to extract key information from Outlook email chains, PDFs, and Word documents. Its core function is to intelligently parse these sources and automatically populate a structured Microsoft Word template with the extracted content — enabling seamless information tracking and reporting from scattered communication and files.

---

## 🚀 Features

- 📧 Access and analyze Outlook email chains via Microsoft Graph API
- 🔍 Parse and embed Emails, PDFs and Word documents
- 🤖 Use OpenAI models for embeddings and context-aware extraction
- 🔗 Vector search using FAISS or Pinecone
- ⚙️ LangChain-based chunking and retrieval
- 📝 Auto-fill Microsoft Word templates with parsed insights

---

## 🧰 Tech Stack

- Python 3.12+
- OpenAI API
- LangChain
- PyMuPDF / pdfminer.six / python-docx
- Microsoft Graph API (via MSAL or O365)
- FAISS or Pinecone (vector database)
- FastAPI (optional backend)

---

## 📁 Folder Structure

```
MarketingTracker/
├── .venv/                    # Virtual environment
├── app/
│   ├── main.py               # App entry point
│   ├── email_loader.py       # Outlook access
│   ├── pdf_parser.py         # PDF parsing
│   ├── docx_updater.py       # Word document template updater
│   └── rag_pipeline.py       # Vector search + RAG
├── requirements.txt
├── .env
└── README.md
```

---

## ⚙️ Setup Instructions

### 📥 1. Clone the Repository

Use SSH (recommended):

```bash
git clone git@github.com:ab1ndal/MarketingTracker.git
cd MarketingTracker
```

Or, if you don’t have SSH set up:

```bash
git clone https://github.com/ab1ndal/MarketingTracker.git
```

---

### 🔐 2. [Optional] Set Up SSH Access

If you're cloning via SSH for the first time:

1. Open **Git Bash** or **PowerShell**
2. Generate an SSH key:

    ```bash
    ssh-keygen -t ed25519 -C "your_email@example.com"
    ```

3. Add your SSH key to GitHub:
    - Copy it: `clip < ~/.ssh/id_ed25519.pub`
    - Paste it at: https://github.com/settings/keys → **New SSH Key**

4. Test connection:

    ```bash
    ssh -T git@github.com
    ```

---

### 🧪 3. Install `uv` (Fast Python Environment Manager)

Install `uv` using `pipx` (recommended):

```bash
pip install pipx
pipx ensurepath
pipx install uv
```

---

### 🧱 4. Set Up Your Python Environment

```bash
uv venv
uv pip install -r requirements.txt --link-mode=copy
```

> If you’re not using `uv`, you can use standard Python:

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```

---

### 🔑 5. Configure `.env` File

Create a file named `.env` in the root of your project with:

```dotenv
# OpenAI API
OPENAI_API_KEY=your_openai_key_here

# Outlook / Microsoft Graph
AZURE_CLIENT_ID=your_client_id
AZURE_TENANT_ID=your_tenant_id
AZURE_CLIENT_SECRET=your_secret
EMAIL_USER=your-email@example.com

# Pinecone
PINECONE_API_KEY=your_pinecone_key
PINECONE_ENVIRONMENT=us-west1-gcp

```

Never commit this file. Add `.env` to your `.gitignore`.

---

### ▶️ 6. Run the Project

```bash
python app/main.py
```

Or, if using FastAPI backend:

```bash
uvicorn app.main:app --reload
```

---

## 🛠️ Requirements

These are defined in `requirements.txt`. Core packages include:

- `pandas`
- `python-dotenv`
- `openai`
- `PyMuPDF`
- `langchain`
- `python-docx`
- `msal`

---

## 📝 License

GNU AFFERO GENERAL PUBLIC LICENSE

---

## 👤 Maintainer

Abhinav Bindal  
[LinkedIn](https://www.linkedin.com/in/abhinav-bindal/)
[Email](mailto:abindal@nyase.com)

---

## 👤 Additional Developers

Reza Moharrami  
[LinkedIn](https://www.linkedin.com/in/mohammadreza-moharrami-99803136//)
[Email](mailto:rmoharrami@nyase.com)
