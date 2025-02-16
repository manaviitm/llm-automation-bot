# LLM Automation Bot

## Overview
LLM Automation Bot is a project designed to automate common tasks using a Large Language Model (LLM) integrated with a FastAPI server. The application handles both operational and business tasks, such as formatting files, running SQL queries, fetching data from APIs, cloning git repositories, and more. The backend is containerized using Docker and can be easily deployed and tested.

## Features
### Phase A Tasks (Operational Tasks)
1. **A1**: Install `uv` and run a Python script from a specified URL.
2. **A2**: Format the contents of `/data/format.md` using `prettier@3.4.2`.
3. **A3**: Count the number of Wednesdays in a file `/data/dates.txt` and save the result.
4. **A4**: Sort the array of contacts in `/data/contacts.json` and write the sorted result.
5. **A5**: Write the first line of the 10 most recent `.log` files in `/data/logs/` to a file.
6. **A6**: Create an index of Markdown files by extracting the first H1 in each file.
7. **A7**: Extract the sender’s email address from `/data/email.txt` using LLM.
8. **A8**: Extract a credit card number from `/data/credit_card.png` using an LLM and save it.
9. **A9**: Find the most similar comments in `/data/comments.txt` using embeddings.
10. **A10**: Calculate total sales for “Gold” ticket type from `/data/ticket-sales.db`.

### Phase B Tasks (Business Tasks)
1. **B1 & B2**: Security checks to ensure files outside `/data` are not accessed or deleted.
2. **B3**: Fetch data from an API and save it.
3. **B4**: Clone a Git repository and make a commit.
4. **B5**: Run SQL queries on SQLite or DuckDB databases.
5. **B6**: Web scraping to extract and save content from a URL.
6. **B7**: Compress or resize an image.
7. **B8**: Transcribe audio from an MP3 file.
8. **B9**: Convert Markdown to HTML.
9. **B10**: Create an API endpoint to filter CSV files and return JSON data.

## Project Structure
```
/app
  |-- app.py            # FastAPI application
  |-- tasksA.py         # Phase A tasks implementation
  |-- tasksB.py         # Phase B tasks implementation
  |-- datagen.py        # Data generation script
  |-- evaluate.py       # Evaluation script
  |-- Dockerfile        # Docker configuration
  |-- requirements.txt  # Python dependencies
```

## Prerequisites
- Python 3.12
- Docker
- Git
- Docker Hub account

## Installation and Setup
### Step 1: Clone the Repository
```bash
git clone https://github.com/manaviitm/llm-automation-bot.git
cd llm-automation-bot
```

### Step 2: Create a Virtual Environment
```bash
python -m venv env
source env/bin/activate   # Linux/Mac
env\Scripts\activate    # Windows
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Run the FastAPI Server
```bash
uvicorn app:app --host 0.0.0.0 --port 8000
```
Access the API at `http://localhost:8000`.

## Docker Setup
### Build the Docker Image
```bash
docker build -t llm-automation-bot .
```

### Run the Docker Container
```bash
docker run -e AIPROXY_TOKEN=your_token_here -p 8000:8000 llm-automation-bot
```

### Test the API
1. **POST `/run` Example**
   ```bash
   curl -X POST "http://localhost:8000/run?task=Fetch+data+from+https://jsonplaceholder.typicode.com/posts/1+and+save+it+to+/data/example.txt"
   ```
2. **GET `/read` Example**
   ```bash
   curl -X GET "http://localhost:8000/read?path=/data/example.txt"
   ```

## Docker Hub
The Docker image is available at: [https://hub.docker.com/repository/docker/manaviitm/llm-automation-bot](https://hub.docker.com/repository/docker/manaviitm/llm-automation-bot)

### Pull the Docker Image
```bash
docker pull manaviitm/llm-automation-bot:latest
```

## Submitting the Project
### What to Submit
1. **GitHub Repository URL**: `https://github.com/manaviitm/llm-automation-bot`
2. **Docker Image URL**: `https://hub.docker.com/repository/docker/manaviitm/llm-automation-bot`

### Submission Steps
1. Verify that the Docker image runs and the API responds.
2. Ensure the GitHub repository is public and contains all project files.
3. Submit the GitHub and Docker Hub URLs.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributors
- **Manav IITM**

---
Let me know if you want me to modify or expand any section of this README!
