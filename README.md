# Hi, I'm Iteoluwakiishi (Kiishi) Aberuagba 👋

**AI Engineer & Python Developer** · 📍 Lagos, Nigeria

I build AI systems in Python. Most of my recent work covers **real-time voice agents** on AWS, **financial research pipelines** for the Nigerian stock market, and **conversational AutoML tools**.

📫 [davidaberuagba@gmail.com](mailto:davidaberuagba@gmail.com) · [LinkedIn](https://www.linkedin.com/in/iteoluwakiishi-aberuagba-9bb7a1239)

---

## 🛠 Tech Stack

**Languages & Web**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white)

**Voice AI & Telephony**

![Pipecat](https://img.shields.io/badge/Pipecat-Voice_Pipeline-000000?style=flat)
![Speechmatics](https://img.shields.io/badge/Speechmatics-Custom_STT-1D4ED8?style=flat)
![ElevenLabs](https://img.shields.io/badge/ElevenLabs-Dialogue_TTS-000000?style=flat&logo=elevenlabs&logoColor=white)
![Deepgram](https://img.shields.io/badge/Deepgram-13EF93?style=flat&logo=deepgram&logoColor=black)
![Telnyx](https://img.shields.io/badge/Telnyx-Telephony-00C08B?style=flat)

**AI, ML & LLMs**

![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat&logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat)
![Anthropic](https://img.shields.io/badge/Claude_Haiku-191919?style=flat&logo=anthropic&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat&logo=openai&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Gemini-4285F4?style=flat&logo=google&logoColor=white)
![Pinecone](https://img.shields.io/badge/Pinecone-000000?style=flat&logo=pinecone&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)

**Infrastructure, Databases & Observability**

![AWS](https://img.shields.io/badge/AWS-EC2_%7C_SSM_%7C_IAM_%7C_OIDC-232F3E?style=flat&logo=amazonwebservices&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Neon](https://img.shields.io/badge/Neon-00E599?style=flat&logo=postgresql&logoColor=black)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=githubactions&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-EA4B71?style=flat&logo=n8n&logoColor=white)
![LangSmith](https://img.shields.io/badge/LangSmith-1C3C3C?style=flat)
![CloudWatch](https://img.shields.io/badge/Amazon_CloudWatch-FF4F8B?style=flat&logo=amazoncloudwatch&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel&logoColor=white)
![HuggingFace](https://img.shields.io/badge/Hugging_Face-FFD21E?style=flat&logo=huggingface&logoColor=black)

---

## 🚀 Featured Projects

### 📞 Kiishi.AI Front Desk: AI Voice Receptionist *(🔒 Private Repository)*
*Python, FastAPI, Pipecat, Speechmatics, ElevenLabs, Claude Haiku, GPT-5-nano, Telnyx, PostgreSQL, Google Calendar API, n8n, Docker, AWS (EC2, SSM, IAM, OIDC)*

A missed call costs a small business a customer, and round-the-clock phone staff is expensive. I built a real-time voice agent named **Daniel** that answers inbound phone calls, qualifies leads, and books appointments on **Google Calendar**.

- Detects caller country codes across **245 regions** to select a matching local accent *(such as Nigerian or Egyptian English)* and switches between new-caller onboarding and returning-caller check-ins.
- Uses the phone-ringing phase to load caller history from **PostgreSQL**, warm up Google Calendar OAuth, and prepare the voice model, keeping **first-turn voice latency under one second**.
- Passes a **1,000-entry custom dictionary** with phonetic pronunciation rules to **Speechmatics STT** so it recognizes *Yoruba*, *Igbo*, and other African caller names.
- Gives the LLM **10 mid-call tools** to check availability, book or reschedule meetings, read past call context, and hang up. All calendar math runs through a **deterministic date-resolver tool**.
- Runs a post-hangup pass with **GPT-5-nano** to extract structured caller summaries and sends webhooks to an **n8n** pipeline for SMS, calendar entries, email, and Telegram alerts.
- Tracks the **USD cost of each call** across five services *(telephony minutes, STT audio time, TTS characters, Claude Haiku prompt-cached tokens, and post-call extraction)* and writes itemized totals to PostgreSQL.
- Stores encrypted credentials in **AWS SSM Parameter Store** with an EC2 sync watcher that reloads containers without manual SSH. Deploys through **GitHub Actions, OIDC, and SSM Run Command** with Port 22 closed, and logs application errors to **Amazon CloudWatch**.

👉 *Try it live:* Call **+1 (773) 337-2440** to speak with Daniel.

---

### 📈 [Nairacle: AI Research Assistant for the Nigerian Stock Market](https://github.com/Kiishi615/The_Nairacle) · [Ingester](https://github.com/Kiishi615/Nairacle_Ingester) · [Stock DB Updater](https://github.com/Kiishi615/Stock_DB_Updater)
*Python, LangChain, LangGraph, Pinecone, Gemini, Tavily, Neon PostgreSQL, LangSmith, HTML/JS*

Standard web search mixes old articles with top-ranked general pages when you ask about Nigerian equities. **Nairacle** answers plain-English questions about companies on the **Nigerian Exchange (NGX)** using a curated news and price database.

- Scraped **~14,000 NGX news articles** and used an LLM pipeline to filter out noise and compress the **4,900 relevant articles** into dense summaries.
- Checks for new articles every day on a schedule, then filters, summarizes, embeds, and stores them without manual intervention.
- Searches by meaning, weights each source by age with a **6-month default recency window**, and reranks results so current articles come first.
- Combines live stock prices from **TradingView Screener** with daily historical equity prices stored in **Neon PostgreSQL**.
- Logs every agent step to **LangSmith** and serves results through a responsive web interface and REST API.

---

### 🤖 [ML Intern: Conversational Machine Learning Pipeline](https://github.com/Kiishi615/ML_Intern_Deployed)
*Python, LangChain, OpenAI, SQLite, FastAPI, HTML/CSS/JS*

**ML Intern** lets a user upload a CSV file, state a prediction goal in plain English *(for example, "predict which customers will cancel")*, and get a trained model with an evaluation report.

- Chains **60+ tools** to clean data, engineer features, select and tune models, evaluate metrics, and plot charts.
- Tracks dataframes, trained models, and prior decisions across the session so the user can ask follow-up questions in the same chat.
- Logs every user request and tool call to **SQLite** for debugging and run reviews.
- Connects a custom web frontend to a private **FastAPI** backend.

---

## 📂 Other Repositories

- **[Job Scraper Pipeline](https://github.com/Kiishi615/job-scraper-pipeline):** Scrapes job listings from *LinkedIn, Indeed, and Jobberman* on a **GitHub Actions** schedule with **Docker** and sends alerts to Telegram.
- **[DocAssist](https://github.com/Kiishi615/day14-doc-assistant) ([Live App](https://day14-doc-assistant.vercel.app/)):** RAG document Q&A app with multi-conversation support, token tracking, and chat export, deployed on **Vercel**.
- **[ASL to Words](https://github.com/Kiishi615/ASL_to_Words):** Translates American Sign Language hand signs into words in real time using **MediaPipe** hand landmarks and a **Random Forest** classifier.

---

## 🤝 Connect

<p align="left">
<a href="https://www.linkedin.com/in/iteoluwakiishi-aberuagba-9bb7a1239" target="_blank">
  <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
</a>
<a href="mailto:davidaberuagba@gmail.com">
  <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
</a>
</p>
