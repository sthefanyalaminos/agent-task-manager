# 🤖 AI Agent for Trello Task Management via Chat
 
> n8n automation that turns a simple chat conversation into automatic Trello card updates.
 
---
This project came from wanting to simplify something I do every day: organizing my tasks. Instead of opening the Trello board and dragging cards manually, I built an AI agent that talks to me, understands what I say about my day's progress, and updates the board on its own.
 
When the conversation starts, the agent greets the user and asks what the day's tasks are. From there, the user just reports progress through chat: "I started task X", "I finished Y", and the agent identifies the right stage and automatically moves the card between:
 
- **To Do** - planned tasks
- **In Progress** - tasks being worked on
- **Done** - finished tasks

The integration happens in real time: every update given in chat is reflected immediately on the Trello board.