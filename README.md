# AI BOT

Slack Bot with Wolfram Alpha and Wit.ai Integration

## Description

This project is a Slack bot that integrates Wolfram Alpha and Wit.ai to handle natural language queries. The bot listens for commands in a Slack workspace, processes the commands using Wit.ai for natural language understanding, and queries Wolfram Alpha for answers. The results are then returned to the Slack channel.

## Features

- **Natural Language Processing**: Uses Wit.ai to parse and understand user queries.
- **Knowledge Retrieval**: Queries Wolfram Alpha to fetch accurate answers.
- **Slack Integration**: Listens and responds to commands in a Slack workspace.
- **Event Logging**: Logs command events for analytics and debugging.

## Prerequisites

Before running the project, ensure you have the following:

- Go (1.16 or later)
- A Slack workspace with the appropriate bot tokens
- Wit.ai token
- Wolfram Alpha AppID
- Environment variables set up correctly

## Installation

1. **Clone the repository:**
   ```sh
   git clone <repository_url>
   cd <repository_directory>
   ```

2. **Install dependencies:**
   ```sh
   go get -u github.com/joho/godotenv
   go get -u github.com/krognol/go-wolfram
   go get -u github.com/shomali11/slacker
   go get -u github.com/tidwall/gjson
   go get -u github.com/wit-ai/wit-go/v2
   ```

3. **Set up environment variables:**

   Create a `.env` file in the project root and add the following:
   ```env
   SLACK_BOT_TOKEN=your_slack_bot_token
   SLACK_APP_TOKEN=your_slack_app_token
   WIT_AI_TOKEN=your_wit_ai_token
   WOLFRAM_APP_ID=your_wolfram_app_id
   ```

## Usage

1. **Run the bot:**
   ```sh
   go run main.go
   ```

2. **Interact with the bot on Slack:**

   Send a message in the format `q - <your question>` to the Slack channel where the bot is active. For example:
   ```
   q - Who is the president of India?
   ```

## Code Explanation

- **Environment Variable Loading:** Uses `godotenv` to load environment variables from a `.env` file.
- **Slack Client Setup:** Initializes the Slack client using `slacker` with the provided bot tokens.
- **Wit.ai Client Setup:** Initializes the Wit.ai client with the provided token.
- **Wolfram Alpha Client Setup:** Initializes the Wolfram Alpha client with the provided AppID.
- **Event Logging:** The `printCommandEvents` function logs command events for analytics.
- **Command Definition:** The bot listens for the command `q - <message>`, processes the query using Wit.ai, extracts the search query, and fetches the answer from Wolfram Alpha.
- **Bot Execution:** The bot listens for commands in the specified Slack channel and handles them accordingly.

## Contributing

If you would like to contribute to this project, please fork the repository and submit a pull request. Issues and feature requests are also welcome.


## Contact

For questions or feedback, please contact [aayush.makhija@gmail.com].

---
