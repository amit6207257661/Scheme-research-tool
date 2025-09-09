# 📘 Scheme Research Tool

An intelligent research assistant that summarizes government scheme articles and allows you to ask questions based on their content — powered by Google Gemini API and LangChain.

Demo Video Link: https://drive.google.com/file/d/1sN02eM5iCupNTLTtQgMiK3oIq6jRUaDi/view?usp=sharing
🔧 Features
✅ Load scheme content via URL or PDF
✅ Automatically split, embed, and index content using FAISS
✅ Ask questions about:
Scheme benefits
Eligibility criteria
Application process
Required documents
Interest rates and subsidies
✅ Uses Google Gemini for intelligent Q&A
✅ Fast and interactive UI with Streamlit
✅ Local vector storage with FAISS for quick retrieval
📁 Project Structure
scheme-research-tool/
│
├── main.py                 # Main Streamlit web application
├── .config                 # Configuration file (stores Gemini API key)
├── requirements.txt        # Python dependencies
├── faiss_index_gemini/     # FAISS index files (auto-created after processing)
├── README.md              # This file
└── .gitignore             # Git ignore file
🚀 Quick Start
1. Clone the Repository
git clone https://github.com/yourusername/scheme-research-tool.git
cd scheme-research-tool
2. Get Your Gemini API Key
Visit Google AI Studio
Create a new API key
Copy the key for the next step
3. Create Configuration File
Create a .config file in the root directory:

GEMINI_API_KEY=your_gemini_api_key_here
Important: Never commit your API key to version control!

Set Up Python Environment
# Create virtual environment (recommended)
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

### 4. Install Dependencies

```bash
pip install -r requirements.txt
5. Run the Application
streamlit run main.py
The app will open in your browser at http://localhost:8501

🧠 How It Works
Input Sources: Paste URLs or upload PDF files of government scheme documents
Content Processing: Documents are automatically split into chunks and converted into embeddings
Vector Storage: A FAISS vector store is created and saved locally for fast retrieval
Question Answering: Ask natural language questions and get AI-powered answers
Intelligent Responses: Google Gemini analyzes the content and provides accurate, contextual answers
💡 Usage Examples
Adding Content
URL Input: Paste links to government scheme pages
PDF Upload: Upload scheme documents, guidelines, or brochures
Sample Questions
"What are the main benefits of this scheme?"
"Who is eligible to apply for this program?"
"What documents do I need to submit?"
"What is the maximum loan amount available?"
"Is there any interest subsidy or cashback?"
"How does this scheme benefit street vendors?"
"What is the application deadline?"
"Are there any age restrictions?"
📦 Dependencies
The tool uses the following key libraries:

streamlit - Web application framework
langchain - LLM application framework
langchain-community - Community integrations
langchain-google-genai - Google Gemini integration
faiss-cpu - Vector similarity search
unstructured - Document processing
PyPDF2 - PDF reading capability
python-dotenv - Environment variable management
🔧 Configuration
Environment Variables
Create a .config file with:

# Required
GEMINI_API_KEY=your_api_key_here

# Optional configurations
CHUNK_SIZE=1000
CHUNK_OVERLAP=200
MAX_RESULTS=5
FAISS Index Storage
Index files are stored in faiss_index_gemini/ directory
Automatically created after first document processing
Can be reused across sessions for faster startup
🛡️ Security & Privacy
API Keys: Store securely in .config file, never in code
Local Processing: All embeddings and indexes stored locally
FAISS Deserialization: Only load indexes you've created yourself
Data Privacy: No data sent to external services except for Gemini API calls
🚀 Deployment Options
Local Development
streamlit run main.py
Streamlit Cloud
Push code to GitHub (without .config file)
Deploy on Streamlit Cloud
Add GEMINI_API_KEY as a secret in Streamlit Cloud settings
Docker Deployment
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
EXPOSE 8501
CMD ["streamlit", "run", "main.py", "--server.port=8501", "--server.address=0.0.0.0"]
🐛 Troubleshooting
Common Issues
API Key Error

Ensure .config file exists and contains valid Gemini API key
Check API key has necessary permissions
FAISS Index Error

Delete faiss_index_gemini/ folder and reprocess documents
Ensure sufficient disk space for index storage
PDF Processing Error

Verify PDF is not password-protected
Try converting PDF to text format first
Memory Issues

Reduce chunk size in configuration
Process smaller documents or fewer URLs at once
🤝 Contributing
Fork the repository
Create a feature branch (git checkout -b feature/amazing-feature)
Commit changes (git commit -m 'Add amazing feature')
Push to branch (git push origin feature/amazing-feature)
Open a Pull Request
🙏 Acknowledgments
Google Gemini for powerful language model capabilities
LangChain for LLM application framework
Streamlit for the amazing web app framework
FAISS for efficient similarity search
📞 Support
If you encounter any issues or have questions:

Open an issue on GitHub
Check existing issues for solutions
Contact: [amitgamer80@gmail.com]
Made with ❤️ for better access to government scheme information
