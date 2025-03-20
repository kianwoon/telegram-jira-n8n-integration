# Telegram-Jira AI Integration

This repository contains an n8n workflow that integrates Telegram with Jira, using AI to determine the appropriate action based on user messages.

## Workflow Overview

### 📌 Step-by-Step Workflow Execution
1. **Telegram Trigger**: Captures user input from Telegram
2. **Set Prompt**: Stores the user's message in a structured format
3. **AI Agent GPT-4o**: Analyzes the user's message and determines the correct Jira action
4. **Parse AI Output**: Converts the AI-generated JSON string into a structured object
5. **Switch Operation**: Routes the workflow based on the AI agent's decision
6. **Jira Create Issue**: Creates a Jira issue using the provided details
7. **Jira List Projects**: Fetches all Jira projects
8. **Count Projects**: Counts the number of Jira projects
9. **Set Create Outcome**: Formats the final response for Telegram
10. **Set Chat ID**: Ensures the Telegram reply is sent to the correct user
11. **Telegram Reply**: Sends the final outcome back to the user in Telegram

## Features

- **Natural Language Understanding**: AI-powered understanding of user requests
- **Smart Priority Detection**: Extracts priority information from context
- **AI-Powered Task Formatting**: Generates well-structured summaries and descriptions
- **Command Handling**: Supports commands like `/create`, `/list`, `/help`
- **Natural Queries**: Understands queries like "show me open issues"
- **Priority-Aware Issue Listing**: Lists issues with priority information
- **Detailed Success Messages**: Provides task information in success messages
- **Friendly Help System**: Includes examples in help responses
- **Error Handling**: Comprehensive error handling with user notifications

## Setup Instructions

### Prerequisites
- n8n installed and running
- Telegram bot token
- Jira Server/Cloud credentials
- OpenAI API key

### Configuration Steps

1. **Import the Workflow**
   - Import the `telegram_jira_workflow.json` file into your n8n instance

2. **Configure Credentials**
   - Set up Telegram Bot credentials
   - Configure Jira API credentials
   - Add your OpenAI API key

3. **Customize the AI Prompt**
   - Modify the prompt in the "AI Agent GPT-4o" node to match your specific use cases
   - Adjust the project keys and issue types to match your Jira configuration

## Example User Scenarios

| User Message | AI Decides | Action Taken |
|--------------|------------|---------------|
| "Create a bug report" | "create" | Creates a Jira issue |
| "How many projects exist?" | "listProjects" | Lists Jira projects and counts them |
| "Create a new task for project ABC" | "create" | Creates an issue in project ABC |
| "Show all available projects" | "listProjects" | Lists Jira projects |

## Extending the Workflow

To add more functionality:
1. Add new action types in the AI prompt
2. Extend the Switch Operation node to handle new actions
3. Add corresponding Jira nodes for new operations