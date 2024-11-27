# Myth Buster App with Fetch.ai Agents

This project implements a **Myth Buster App** using [Fetch.ai Agents](https://fetch.ai), designed to identify and debunk myths via sentiment analysis, web search, and content generation. The app leverages multi-agent communication to process requests and create educational social media posts for debunking myths.

## Features

- **Sentiment Analysis**: Classifies input text as `POSITIVE` or `NEGATIVE`.
- **Web Search**: Fetches relevant documents to address myths using a web search agent.
- **Content Generation**: Generates social media posts to educate and debunk myths using OpenAI.
---


## Using Pre-Built Agents

This application utilizes **pre-built agents** available on [Agentverse](https://agentverse.ai/marketplace?item_type=agents&types=hosted%2Clocal%2Cmailbox&dev_categories=fetch-ai%2Ccommunity&sort=relevancy), such as:
- Sentiment Analysis Agent - [Agent Profile](https://agentverse.ai/agents/details/agent1qvzs7zhwdcx6rlnyzs9p9sjjq4zscd44zvx8fnpflrlu2ptvlh5fxlkwzge/profile)
- Web Search Agent - [Agent Profile](https://agentverse.ai/agents/details/agent1qt5uffgp0l3h9mqed8zh8vy5vs374jl2f8y0mjjvqm44axqseejqzmzx9v8/profile)
- OpenAI Agent for text generation - [Agent Profile](https://agentverse.ai/agents/details/agent1q0h70caed8ax769shpemapzkyk65uscw4xwk6dc4t3emvp5jdcvqs9xs32y/profile)

However, you are not limited to these agents! **You can create your own Fetch.ai uAgents** and connect them in a similar manner. The uAgents framework is highly flexible.

If you'd like to learn how to create your own agents, check out the [Fetch.ai documentation](https://fetch.ai/docs).

---

## Architecture

1. **Sentiment Analysis Agent**:
   - Analyzes the input text and determines its sentiment (`POSITIVE` or `NEGATIVE`).
   - If `NEGATIVE`, forwards the text for further processing.

2. **Web Search Agent**:
   - Searches for documents relevant to the myth.
   - Returns a list of results with titles, URLs, and summaries.

3. **OpenAI Agent**:
   - Creates an educational social media post using the retrieved documents and myth context.

4. **Main Agent**:
   - Orchestrates interactions between agents.
   - Handles REST API endpoints and processes responses.
- You can find more agents to build your applications on [Agentverse Marketplace](https://agentverse.ai/marketplace?item_type=agents&types=hosted%2Clocal%2Cmailbox&dev_categories=fetch-ai%2Ccommunity&sort=relevancy)
---

## Setup

### Prerequisites

1. Python 3.11 or higher.
2. Install required Python libraries:
   ```bash
   pip install uagents
   
---
## To test the application

1. Run the Main Agent
    ```bash
    python main-agent.py
   
2. Query the agent directly through your predefined interfaces or Command Line:
    ```bash
   curl -d '{"text": "Covid 19 vaccines cause autism."}' -H "Content-Type: application/json" -X POST http://localhost:8001/rest/post    

3. Sample Response
    ```bash
   {"timestamp": 1732675131, "text": "\ud83e\udda0\ud83d\udc89 Let's set the record straight! A common myth that has caused a lot of fear is the belief that COVID-19 vaccines can cause autism. This is simply NOT true!\n\n\ud83d\udeab The COVID-19 vaccines do NOT contain any components that would lead to autism. Extensive research and studies conducted by scientists and medical professionals have shown that vaccines are safe and effective.\n\n\ud83e\uddec The vaccines work by teaching our immune systems how to recognize and fight the virus that causes COVID-19, without introducing the live virus itself. \n\n\ud83d\udce2 For more accurate information and to help dispel vaccine myths, check out these resources:\n1. Cleveland Clinic: [How to Dispel Myths About the COVID-19 Vaccine](https://consultqd.clevelandclinic.org/how-to-dispel-myths-about-the-covid-19-vaccine)\n2. Mayo Clinic: [Debunking myths about COVID-19](https://www.mayoclinichealthsystem.org/hometown-health/featured-topic/covid-19-vaccine-myths-debunked)\n3. VCU Health: [Vaccine myths Facts vs fiction](https://www.vcuhealth.org/news/covid-19/vaccine-myths-facts-vs-fiction)\n4. CDC: [How to Address COVID-19 Vaccine Misinformation](https://www.cdc.gov/vaccines/covid-19/health-departments/addressing-vaccine-misinformation.html)\n\n\ud83d\udcaa It's important to stay informed with credible sources to protect ourselves and our communities. Let's share the truth and keep each other safe! #VaccinesWork #COVID19 #MythBusting #PublicHealth", "agent_address": "agent1qdex27edvmtux66229kzjmuff0d2clueu9akwlzacsyet80k7wdecrpc8cy"}  
