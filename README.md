# youtube-summary-alfred
This Alfred workflow takes in a URL to a YouTube video and uses ChatGPT 3.5 to summarize it. This is very much an alpha version with basic features and lots of room for improvement
<img width="1450" alt="Screenshot of the youtube-summary Alfred workflow displaying an AI generated summary of a YouTube video" src="https://github.com/user-attachments/assets/7acb1689-6dec-4474-bff8-55255a3c214c">

## How does it work?
First, the workflow parses the URL with a regex to extract the video ID. Next, it leverages [the youtube-transcript-api Python package](https://pypi.org/project/youtube-transcript-api/) to fetch the transcript for the video. Finally, it calls the ChatGPT API with the transcript and requests a summary of the video. This summary is displayed to the user. The only required parameter aside from the video URL, is a ChatGPT API key.

## Setup
Copy your OpenAI API key and add it to the [Workflow’s Configuration](https://www.alfredapp.com/help/workflows/user-configuration/).

## Usage
Trigger the workflow with the `ytsum` keyword, and then paste the URL to a YouTube video. Wait a moment while the model generates a summary


## Features I'd like to add
* Caching ChatGPT responses - AI models are expensive, it would be nice to have an option to cache responses as a text file and periodically clean them up after 30 days
* Integrate with other models such as Google's Gemini, or GPT 4o, and let the user pick in the configuration or at runtime
* Use Alfred's script input on the Text View to allow the user to ask followup questions to the model
