# AI Task Management Agent with Trello

[Traduzir para Português](https://github.com/sthefanyalaminos/agent-task-manager/blob/main/readme.md)

> Project developed as part of the CI&T Bootcamp – From Prompt to Agent, hosted by DIO. The goal is to build a conversational AI agent that automates task management in Trello, integrating Python with the Trello API and Google ADK.

---

## About the Project

This project creates an **artificial intelligence agent** capable of managing day-to-day work through a simple terminal conversation. When started, the agent greets the user with the current date and asks what the tasks for the day are. From there, the user can report the progress of each activity through the chat, and the agent automatically updates the cards on the Trello board, moving them between the following stages:

- **To Do** - planned tasks
- **In Progress** - tasks being worked on
- **Done** - completed tasks

The integration happens in real time: every update reported in the chat is immediately reflected on the Trello board.

---

## Technologies Used

- **Python** - main language of the project
- **Google ADK** - framework for building the AI agent
- **py-trello** - Python library for Trello API integration
- **python-dotenv** - environment variable management

---

## Prerequisites

Before running the project, you will need:

- Python 3.7 or higher installed
- An active [Trello](https://trello.com/) account
- pip (Python package manager)
- A Trello board created with the following lists: **To Do**, **In Progress**, and **Done**

---

## Environment Setup

### 1. Clone the repository

```bash
git clone https://github.com/sthefanyalaminos/agent-task-manager.git
cd agent-task-manager
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

The `requirements.txt` file includes:

```
google-adk
py-trello
datetime
python-dotenv
```

### 3. Configure Trello credentials

Create a `.env` file in the project root with the following variables:

```env
TRELLO_API_KEY=your_api_key_here
TRELLO_TOKEN=your_token_here
TRELLO_BOARD_ID=your_board_id_here
```

> ⚠️ Never push the `.env` file to GitHub. Make sure it is listed in `.gitignore`.

---

## How to Get Trello Credentials

### Step 1 - Create a Power-Up (Application)

1. Go to the [Trello Power-Ups admin portal](https://trello.com/power-ups/admin/)
2. Click **"New"** to create a new application
3. Fill in the name, workspace, and contact email
4. Click **"Create"**

### Step 2 - Get the API Key

On your Power-Up page, copy the **API Key** shown in the "API Key" section.

### Step 3 - Generate the Authorization Token

Build the URL below, replacing `YOUR_API_KEY`:

```
https://trello.com/1/authorize?expiration=never&name=AppDio&scope=read,write&response_type=token&key=YOUR_API_KEY
```

Open that URL in your browser, review the permissions, and click **"Allow"**. The token will be displayed on the screen — copy and store it securely.

> 📖 Full setup guide: [agents/agent04/readme.md](./agents/agent04/readme.md)

---

## How to Run

```bash
python agents/agent04/agent.py
```

Once started, the agent will:

1. Greet you with the current date
2. Ask what your tasks for the day are
3. Automatically create the cards on Trello
4. Wait for status updates via chat and move the cards in real time

---

## What I Learned from This Project

- How to integrate Python with external APIs using third-party libraries (`py-trello`)
- How to set up and use **Google ADK** to build conversational AI agents
- The importance of secure credential management with environment variables (`.env`)
- How to structure a Python project with multiple agents and separation of concerns
- In practice: with just a few lines of Python, it is already possible to have a functional assistant integrated with everyday tools

---

## Authorship

Developed by Sthefany Alaminos, during the CI&T Bootcamp – From Prompt to Agent, hosted by DIO.
