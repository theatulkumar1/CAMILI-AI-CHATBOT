# CAMILI AI CHATBOT

## Overview
CAMILI is an intelligent voice-activated AI assistant built with Python that combines speech recognition, text-to-speech, and OpenAI's GPT-3.5 Turbo to create a hands-free virtual assistant experience. This project represents my first interaction with AI technology, creating a Jarvis-like assistant capable of performing various tasks through voice commands.

## Features

### 🎤 Voice Recognition
- Wake word activation ("jarvis")
- Continuous listening for user commands
- Google Speech Recognition integration
- Timeout and phrase limit controls for efficient processing

### 🔊 Text-to-Speech
- Multiple TTS engines:
  - Google Text-to-Speech (gTTS) for natural-sounding speech
  - pyttsx3 as fallback option
- Audio playback using pygame mixer
- Temporary file management for audio output

### 🤖 AI-Powered Responses
- Integration with OpenAI's GPT-3.5 Turbo
- Context-aware responses
- Virtual assistant persona named "Jarvis"
- Handles general queries similar to Alexa or Google Assistant

### 🌐 Web Automation
- Quick access to popular websites:
  - Google
  - Facebook
  - YouTube
  - LinkedIn
- Browser automation using webbrowser module

### 🎵 Music Playback
- Custom music library integration
- Voice-activated song playback
- YouTube link support
- Simple "play [song name]" command interface

### 📰 News Integration
- Real-time news headlines from NewsAPI
- Voice-based news reading
- Country-specific news filtering (India)
- Audio narration of top headlines

## Project Structure

```
CAMILI-AI-CHATBOT/
│
├── main.py              # Main application file with core logic
├── client.py            # OpenAI client test/example file
├── musicLibrary.py      # Music links database
└── README.md            # Project documentation
```

## Prerequisites

### Required Python Packages
```bash
pip install speech_recognition
pip install pyttsx3
pip install gtts
pip install pygame
pip install openai
pip install requests
pip install pocketsphinx
```

### API Keys Required
1. **OpenAI API Key**: For GPT-3.5 Turbo integration
   - Sign up at [OpenAI Platform](https://platform.openai.com/)
   - Generate an API key from your account dashboard

2. **NewsAPI Key**: For news headlines feature
   - Register at [NewsAPI](https://newsapi.org/)
   - Get your free API key

### Hardware Requirements
- Working microphone for voice input
- Audio output device (speakers/headphones)

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/theatulkumar1/CAMILI-AI-CHATBOT.git
cd CAMILI-AI-CHATBOT
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

Or install packages individually:
```bash
pip install speech_recognition pyttsx3 gtts pygame openai requests pocketsphinx
```

### 3. Configure API Keys

Open `main.py` and add your API keys:

```python
# Line 13: Add your NewsAPI key
newsapi = "YOUR_NEWSAPI_KEY_HERE"

# Line 34: Add your OpenAI API key
client = OpenAI(api_key="YOUR_OPENAI_API_KEY_HERE")
```

### 4. Customize Music Library (Optional)

Edit `musicLibrary.py` to add your favorite songs:
```python
music = {
    "song_name": "youtube_link",
    # Add more songs here
}
```

## Usage

### Starting the Assistant
```bash
python main.py
```

### Activating the Assistant
1. Wait for "Initializing camili...." message
2. Say the wake word: **"jarvis"**
3. Wait for the "Ya" response
4. Speak your command

### Available Commands

#### Website Navigation
- "Open Google" - Opens Google.com
- "Open Facebook" - Opens Facebook.com
- "Open YouTube" - Opens YouTube.com
- "Open LinkedIn" - Opens LinkedIn.com

#### Music Playback
- "Play [song name]" - Plays the specified song from music library
  - Example: "Play stealth", "Play march", "Play skyfall", "Play wolf"

#### News
- "News" - Reads out the latest news headlines from India

#### General Queries
- Ask any question, and the AI will provide an intelligent response
  - Examples:
    - "What is the weather like?"
    - "Tell me a joke"
    - "What is coding?"
    - "Explain artificial intelligence"

## Code Architecture

### main.py
- **speak_old()**: Legacy TTS function using pyttsx3
- **speak()**: Current TTS function using gTTS and pygame
- **aiProcess()**: Handles OpenAI API requests
- **processCommand()**: Command routing and execution logic
- **Main loop**: Continuous listening and wake word detection

### client.py
- Standalone OpenAI client example
- Demonstrates basic API usage
- Useful for testing API connectivity

### musicLibrary.py
- Dictionary-based music database
- Maps song names to YouTube URLs
- Easily extensible for more songs

## Technical Details

### Speech Recognition
- Uses Google's Speech Recognition API
- Timeout: 5 seconds
- Phrase time limit: 1 second (for wake word)
- No timeout for commands (continuous listening)

### AI Model
- Model: GPT-3.5 Turbo
- System prompt: Virtual assistant persona (Jarvis)
- Short response optimization
- Context-aware conversation handling

### Audio Processing
- Text-to-speech: Google TTS (gTTS)
- Audio format: MP3
- Playback: Pygame mixer
- Automatic cleanup of temporary files

## Troubleshooting

### Common Issues

**Microphone not detected:**
```bash
# Test microphone
import speech_recognition as sr
r = sr.Recognizer()
with sr.Microphone() as source:
    print(sr.Microphone.list_microphone_names())
```

**API Key errors:**
- Ensure API keys are correctly added to `main.py`
- Verify API keys are active and have sufficient credits
- Check for typos in key strings

**Audio playback issues:**
- Ensure pygame is properly installed
- Check system audio settings
- Verify speakers/headphones are connected

**Recognition errors:**
- Speak clearly and at moderate pace
- Reduce background noise
- Ensure microphone permissions are granted

## Future Enhancements

- [ ] Add weather API integration
- [ ] Implement reminder/alarm functionality
- [ ] Add email sending capability
- [ ] Create a GUI interface
- [ ] Add support for multiple languages
- [ ] Implement conversation history
- [ ] Add calendar integration
- [ ] Create mobile app version
- [ ] Add custom wake word training
- [ ] Implement offline mode with local models

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is open source and available for educational purposes.

## Acknowledgments

- OpenAI for GPT-3.5 Turbo API
- Google for Speech Recognition API
- NewsAPI for news headlines
- Python community for excellent libraries

## Author

**theatulkumar1**
- GitHub: [@theatulkumar1](https://github.com/theatulkumar1)

## Project Status

This is my first AI interaction project and is actively being developed. Feel free to star ⭐ the repository if you find it helpful!

---

**Note**: Remember to keep your API keys secure and never commit them to public repositories. Consider using environment variables for production deployments.
