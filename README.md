# ChatApp with Voice and OpenAI

## Introduction

This project is a chat application that integrates OpenAI's GPT model with IBM Watson's Text-to-Speech (TTS) and Speech-to-Text (STT) services. The application allows users to interact with a personal assistant through text and voice commands.

## Features

- **Text-to-Speech**: Converts text responses from the assistant into spoken words.
- **Speech-to-Text**: Converts spoken words from the user into text for processing.
- **OpenAI Integration**: Uses OpenAI's GPT model to generate responses to user queries.
- **Light/Dark Mode**: Toggle between light and dark themes.
- **Voice Options**: Choose from multiple voice options for the assistant's responses.

## Technologies Used

- **Frontend**: HTML5, CSS3, JavaScript, jQuery, Bootstrap
- **Backend**: Flask (Python web framework)
- **AI Services**:
    - OpenAI GPT-3.5 Turbo for natural language processing
    - IBM Watson Speech-to-Text for voice recognition
    - IBM Watson Text-to-Speech for voice synthesis
- **Containerization**: Docker
- **APIs**: RESTful API architecture for service communication

## Demo

![ChatApp Interface]("demo pics and videos"/va1.png)

![ChatApp Interface]("demo pics and videos"/va2.png)

Watch our application in action:
- [Voice Command Demo]("demo pics and videos".mp4)

## Setup

1. **Clone the repository**:
        ```sh
        git clone <repository-url>
        cd chatapp-with-voice-and-openai
        ```

2. **Build the Docker images**:
        - For Speech-to-Text:
                ```sh
                cd models/stt
                docker build . -t stt-standalone
                ```
        - For Text-to-Speech:
                ```sh
                cd ../tts
                docker build . -t tts-standalone
                ```

3. **Run the Docker containers**:
        - For Speech-to-Text:
                ```sh
                docker run --rm -it --env ACCEPT_LICENSE=true --publish 1080:1080 stt-standalone
                ```
        - For Text-to-Speech:
                ```sh
                docker run --rm -it --env ACCEPT_LICENSE=true --publish 1081:1080 tts-standalone
                ```

4. **Install Python dependencies**:
        ```sh
        pip install -r requirements.txt
        ```

5. **Run the Flask server**:
        ```sh
        python server.py
        ```

## Usage

- Open your browser and navigate to `http://localhost:8000`.
- Type your message or click the microphone icon to record your voice.
- Choose a voice option from the dropdown menu if desired.
- Interact with the assistant and receive responses in both text and audio formats.

## Acknowledgements

This project is based on the [IBM Build Lab Watson Speech repository](https://github.com/ibm-build-lab/Watson-Speech).
