# Market Mind: Autonomous Competitor Analysis Agent

A powerful, context-aware autonomous research agent designed to perform multi-step competitor analysis and data extraction.

The application leverages **LangGraph** to build a robust cyclic state machine that dynamically identifies data gaps and triggers follow-up web searches to ensure the accuracy of its reports. It pairs this intelligent reasoning engine with a high-performance, concurrent web scraping engine developed in **Golang**. This hybrid approach efficiently transforms unstructured web data into structured, actionable records stored in a **PostgreSQL** database.

By integrating **LangChain tool-calling**, Market Mind effectively automates the complex market research process, significantly optimizing workflows and reducing manual data collection time by 80%.

## Features

- **Autonomous Research Agent**: Performs multi-step competitor analysis and targeted data extraction with minimal human intervention.
- **Cyclic State Machine**: Intelligently identifies missing information and iteratively triggers subsequent web searches to fill data gaps and guarantee report accuracy.
- **Concurrent Web Scraping**: Utilizes a high-speed engine built in Go to gather data concurrently from multiple sources without bottlenecking.
- **Data Structuring Pipeline**: Transforms raw, unstructured web data parsed via BeautifulSoup into highly structured PostgreSQL records.
- **LangChain Tool-Calling**: Automates research tasks and standardizes LLM outputs, reducing manual data collection effort by 80%.

## Technical Stack

- **Agent Framework**: LangGraph
- **LLM Integration**: LangChain Tool-Calling
- **Scraping Engine**: Golang, BeautifulSoup
- **Database**: PostgreSQL

## Prerequisites

```bash
# Python environment for LangGraph and LangChain
python >= 3.10
pip or uv (recommended)

# Go environment for the concurrent scraping engine
go >= 1.21

# Database
PostgreSQL running locally or via a cloud provider
```

## Installation & Setup
- Clone the Repository
```bash
git clone https://github.com/yourusername/Market-Mind.git
cd Market-Mind
```

- Set Up the Python Environment (Agent Framework)
Install the necessary dependencies for LangGraph, LangChain, and other Python utilities.

1. Using UV
```bash
uv sync
```

2. Using pip
```bash
python -m venv .venv

# Activate the virtual environment on Windows:
.venv\Scripts\activate

# Activate the virtual environment on macOS/Linux:
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

- Set Up the Go Environment (Scraping Engine)
Navigate to the Go module directory and install the concurrent scraping dependencies.
```bash
cd scraper
go mod tidy
cd ..
```

- Database Configuration
Ensure your PostgreSQL instance is active. Run the necessary migration scripts to set up the schemas for the structured web data.
```bash
# Execute your initialization script (adjust path if necessary)
psql -U your_postgres_user -d market_mind -f db/migrations/init.sql
```

- Environment Variables
Create a .env file in the root directory to store your LLM API keys and database credentials.
```bash
# Create the .env file
touch .env

# Open .env in your text editor and add the following configurations:
OPENAI_API_KEY=your_openai_api_key_here
POSTGRES_URI=postgresql://user:password@localhost:5432/market_mind
```
