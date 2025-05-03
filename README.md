# 🧠 YouTube Blog Writer – AI-Powered Multi-Agent Blog Generator

This project automates the transformation of YouTube video content into well-structured blog articles using Large Language Models (LLMs) and multi-agent collaboration. Built with [CrewAI](https://github.com/joaomdmoura/crewAI), the system simulates a team of intelligent agents (researcher + writer) working together in a sequential pipeline.
![image](https://github.com/user-attachments/assets/085814f2-6f36-4545-8b4d-9521d2e06fda)

## 🚀 Project Motivation

Manually summarizing YouTube videos into blogs is time-consuming — especially for channels with 1000+ videos. This project was created to solve that problem using autonomous AI agents that mimic the workflow of a human researcher and writer.

## 🛠️ Features

- 🔍 **Video Research Agent**: Extracts transcripts from a specified YouTube channel using a query topic.
- ✍️ **Blog Writer Agent**: Converts extracted data into a clear, concise blog post using GPT-4.
- 🔗 **Tool Integration**: YouTubeChannelSearchTool is used for content extraction from `@`.
- 🧩 **Sequential Agent Execution**: Ensures contextual task handover between agents.
- 📦 **Modular Design**: Easy to extend with more agents or tools (e.g., PDF reader, Google search).
- 📄 **Auto Blog Generation**: Outputs results to a Markdown file (`new-blog-post.md`).

## 📂 Project Structure

```

.
├── agents.py            # Defines blog researcher and writer agents
├── crew\.py              # Orchestrates task execution using CrewAI
├── tasks.py             # Defines the tasks each agent performs
├── tools.py             # Contains YouTube search tool setup
├── requirements.txt     # Project dependencies
├── .env                 # Stores API keys securely
└── new-blog-post.md     # Auto-generated blog output

````

## ⚙️ How It Works

1. **Blog Researcher Agent**:  
   - Uses `YoutubeChannelSearchTool` to search a video from `@` based on a query topic  
   - Extracts and summarizes video transcript using GPT-4

2. **Blog Writer Agent**:  
   - Takes summarized research and writes a 3-paragraph blog in Markdown format

3. **Crew Execution**:  
   - The `crew.py` file initializes agents and tasks, and executes them in sequence using `crew.kickoff(inputs={'topic': 'Your Topic Here'})`

## 🧠 Example

```python
result = crew.kickoff(inputs={'topic''})
print(result)
````

The output will be stored in `new-blog-post.md`.

## 📦 Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/your-username/youtube-blog-writer.git
cd youtube-blog-writer
```

### 2. Create and activate virtual environment

```bash
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Set up environment variables

Create a `.env` file with the following:

```
OPENAI_API_KEY=your_openai_key
OPENAI_MODEL_NAME=gpt-4-0125-preview
```

### 5. Run the pipeline

```bash
python crew.py
```

## 📘 Sample Output

Check out the auto-generated blog: [new-blog-post.md](./new-blog-post.md)

## 🧠 Skills Demonstrated

* Multi-agent system architecture
* LangChain + CrewAI tool orchestration
* OpenAI GPT-4 integration
* Markdown generation and content structuring
* Autonomous LLM pipelines

## 📌 Future Enhancements

* Add more agents (e.g., SEO optimizer, proofreader)
* Support other LLM providers (HuggingFace, Ollama)
* Add GUI with Streamlit for user-friendly querying
* Auto-publish to CMS (e.g., WordPress API)

## 📄 License

This project is open-sourced under the MIT License.

---

> Developed by [Arun Kumar Reddy Katika](https://linkedin.com/in/arunkatika) – AI Engineer passionate about automation and content generation with LLMs.

```
