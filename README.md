# Iteoluwakiishi (Kiishi) Aberuagba

AI Engineer and Python Developer in Lagos, Nigeria.

I started in chemical engineering and now build AI systems in Python. Most of my recent work covers real-time voice agents on AWS, financial research pipelines for the Nigerian stock market, and automated machine learning tools.

Contact: [davidaberuagba@gmail.com](mailto:davidaberuagba@gmail.com) | [LinkedIn](https://www.linkedin.com/in/iteoluwakiishi-aberuagba-9bb7a1239)

## Featured projects

### Kiishi.AI Front Desk: AI voice receptionist (Private repository)
Python, FastAPI, Pipecat, Speechmatics, ElevenLabs, Claude Haiku, GPT-5-nano, Telnyx, PostgreSQL, Google Calendar API, n8n, Docker, AWS (EC2, SSM, IAM, OIDC)

A missed call costs a small business a customer, and round-the-clock phone staff is expensive. I built a voice agent named Daniel that answers inbound phone calls, qualifies leads, and books appointments on Google Calendar.

- Detects caller country codes across 245 regions to select a matching local accent (such as Nigerian or Egyptian English) and switches between new-caller onboarding and returning-caller check-ins.
- Uses the phone-ringing phase to load caller history from PostgreSQL, warm up Google Calendar OAuth, and prepare the voice model. This keeps first-turn voice latency under one second.
- Passes a 1,000-entry custom dictionary with phonetic pronunciation rules to Speechmatics STT so it recognizes Yoruba, Igbo, and other African caller names.
- Gives the LLM 10 mid-call tools to check availability, book or reschedule meetings, read past call context, and hang up. All calendar math runs through a deterministic date-resolver tool.
- Runs a post-hangup pass with GPT-5-nano to extract structured caller summaries and sends webhooks to an n8n pipeline for SMS, calendar entries, email, and Telegram alerts.
- Tracks the USD cost of each call across five services (telephony minutes, STT audio time, TTS characters, cached and uncached Claude Haiku tokens, and post-call extraction) and writes itemized totals to PostgreSQL.
- Stores encrypted credentials in AWS SSM Parameter Store with an EC2 sync watcher that reloads containers without manual SSH. Deploys through GitHub Actions, OIDC, and SSM Run Command with Port 22 closed, and logs application errors to Amazon CloudWatch.

Live test number: call **+1 (773) 337-2440** to speak with Daniel.

### [Nairacle: AI research assistant for the Nigerian stock market](https://github.com/Kiishi615/The_Nairacle) ([Ingester](https://github.com/Kiishi615/Nairacle_Ingester) | [Stock DB Updater](https://github.com/Kiishi615/Stock_DB_Updater))
Python, LangChain, LangGraph, Pinecone, Gemini, Tavily, Neon PostgreSQL, LangSmith, HTML/JS

Standard web search mixes old articles with top-ranked general pages when you ask about Nigerian equities. Nairacle answers plain-English questions about companies on the Nigerian Exchange (NGX) using a curated news and price database.

- Scraped about 14,000 NGX news articles and used an LLM pipeline to filter out noise and compress the 4,900 relevant articles into dense summaries.
- Checks for new articles every day on a schedule, then filters, summarizes, embeds, and stores them without manual intervention.
- Searches by meaning, weights each source by age with a 6-month default window, and reranks results so current articles come first.
- Combines live stock prices from TradingView Screener with daily historical equity prices stored in Neon PostgreSQL.
- Logs every agent step to LangSmith and serves results through a web interface and REST API.

### [ML Intern: Conversational machine learning pipeline](https://github.com/Kiishi615/ML_Intern_Deployed)
Python, LangChain, OpenAI, SQLite, FastAPI, HTML/CSS/JS

ML Intern lets a user upload a CSV file, state a prediction goal in plain English, and get a trained model with an evaluation report.

- Chains more than 60 tools to clean data, engineer features, select and tune models, evaluate metrics, and plot charts.
- Tracks dataframes, trained models, and prior decisions across the session so the user can ask follow-up questions in the same chat.
- Logs every user request and tool call to SQLite for debugging.
- Connects a custom web frontend to a FastAPI backend.

## Other repositories

- [Job Scraper Pipeline](https://github.com/Kiishi615/job-scraper-pipeline): Scrapes job listings from LinkedIn, Indeed, and Jobberman on a GitHub Actions schedule with Docker and sends alerts to Telegram.
- [DocAssist](https://github.com/Kiishi615/day14-doc-assistant) ([Live app](https://day14-doc-assistant.vercel.app/)): Document Q&A app with multi-conversation support, token tracking, and chat export, deployed on Vercel.
- [ASL to Words](https://github.com/Kiishi615/ASL_to_Words): Translates American Sign Language hand signs into words using MediaPipe hand landmarks and a Random Forest classifier.

## Technical skills

- Languages: Python, HTML, CSS, JavaScript
- Voice AI: Pipecat, Speechmatics (custom vocabulary STT), Deepgram, ElevenLabs (dialogue TTS), Telnyx
- AI and ML: RAG systems, LangChain, LangGraph, vector search, AutoML, scikit-learn
- LLM providers: Anthropic (Claude Haiku), OpenAI (GPT-5-nano), Google (Gemini)
- Infrastructure: FastAPI, Streamlit, Pinecone, ChromaDB, SQLite, PostgreSQL, Neon, Vercel, Hugging Face, Docker, AWS (EC2, SSM, IAM, OIDC), GitHub Actions, n8n
- Observability: Amazon CloudWatch, LangSmith, multi-provider cost tracking, audio call recording pipelines
