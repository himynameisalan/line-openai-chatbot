# LINE Chatbot with OpenAI API

This tutorial shows you how to create a LINE chatbot using the LINE Messaging API and OpenAI API. We'll be using Python and Flask to build the chatbot and deploy it on Heroku.

## Prerequisites

- LINE Official Account with Messaging API enabled
- OpenAI API key
- Heroku account

## Setup

1. Clone this repository or create a new folder for your project.

2. Install the required Python libraries using pip:

  ```
  pip install Flask gunicorn line-bot-sdk openai
  ```

3. Create `requirements.txt`

  ```
  pip freeze > requirements.txt
  ```

4. Create a `Procfile` in the project folder with the following content:

  ```
  web: gunicorn line_openai_chatbot:app
  ```

5. Set up the webhook on Heroku:

- Sign up for a [Heroku account](https://signup.heroku.com/) if you haven't already.
- Install the [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli).
- Log in to Heroku using the Heroku CLI: `heroku login`
- Create a new Heroku app: `heroku create your-app-name`
- Deploy your chatbot to Heroku: `git push heroku master`
- Set the required environment variables on Heroku:

  ```
  heroku config:set LINE_CHANNEL_ACCESS_TOKEN=your_line_channel_access_token
  heroku config:set LINE_CHANNEL_SECRET=your_line_channel_secret
  heroku config:set OPENAI_API_KEY=your_openai_api_key
  ```

- Update the webhook URL in the LINE Developer Console to `https://your-app-name.herokuapp.com/webhook`

6. Test your chatbot by adding your LINE Official Account to your LINE contacts using the QR code or the LINE ID provided in the LINE Developer Console.

## Configuration

Make sure to replace the placeholders in the environment variables with your actual access tokens and secrets:

- `LINE_CHANNEL_ACCESS_TOKEN`: Your LINE Channel Access Token
- `LINE_CHANNEL_SECRET`: Your LINE Channel Secret
- `OPENAI_API_KEY`: Your OpenAI API Key

## Usage

After following the setup steps, your LINE chatbot should be up and running. You can now send messages to your LINE Official Account, and the chatbot will respond using the OpenAI API.

## License

This tutorial is provided under the [MIT License](https://opensource.org/licenses/MIT).
