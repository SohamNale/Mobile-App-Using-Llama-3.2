# Mobile-App-Using-Llama-3.2

A mobile chat application built with Flutter that interfaces with LLaMA 3.2, a powerful language model, through a Flask API backend. The app provides a simple and intuitive chat interface for users to interact with the AI model.

## Architecture

The project consists of three main components:

1. **Frontend**: Flutter mobile application
2. **Backend**: Flask API server running LLaMA 3.2 model
3. **API Gateway**: ngrok for exposing the local API endpoint

## Features

- Clean and intuitive chat interface
- Real-time message exchange with LLaMA 3.2
- Loading indicators for API responses
- Error handling for failed requests
- Auto-scrolling chat view
- Cross-platform support (Android/iOS)

## Prerequisites

- Flutter SDK
- Python 3.7+
- HuggingFace account and API token
- ngrok account and authtoken
- CUDA-capable GPU (recommended)

## Installation

### Backend Setup

1. Install Python dependencies:
```bash
pip install transformers huggingface-hub torch flask flask-cors pyngrok
```
2. Configure the Flask server (llama3_2_API.ipynb):

* Add your HuggingFace token
* Add your ngrok authtoken
* Run the notebook to start the server
3. Test the API endpoint (test.ipynb):

* Update the ngrok URL
* Run the test to verify the API is working

### Frontend Setup
1. Clone the repository
2. Install Flutter dependencies:
```bash
flutter pub get
```
3. Update the API URL in main.dart:
```bash
final String apiUrl = 'YOUR_NGROK_URL/generate';
```
4. Run the app:
```bash
flutter run
```

## Project Structure
```bash
chat_app/
├── lib/
│   └── main.dart          # Main Flutter application code
├── backend/
│   ├── llama3_2_API.ipynb # Flask API with LLaMA 3.2 model
│   └── test.ipynb         # API testing script
└── [Flutter project files]
```
## How It Works
1. The Flask server loads the LLaMA 3.2 model and creates an API endpoint
2. ngrok creates a public URL for the local Flask server
3. The Flutter app sends user messages to the API endpoint
4. The LLaMA model generates responses which are sent back to the app
5. The chat interface updates with the model's response

## Technical Details
### Backend
* Uses HuggingFace's transformers library for LLaMA 3.2
* Flask server with CORS support
* Message format: {"message": "user input"}
* Response format: {"response": "model output"}
### Frontend
* Material Design UI components
* Asynchronous HTTP requests
* State management using setState
* Scrollable chat interface
* Input validation and error handling

## Limitations
* Requires active internet connection
* ngrok URL needs to be updated periodically (free tier)
* Response time depends on server hardware
* Limited by LLaMA 3.2 model capabilities

## Future Improvements
* Implement user authentication
* Add message persistence
* Support for multiple chat sessions
* Enhanced error handling and retry logic
* UI/UX improvements
* Message formatting support

## Acknowledgments
* Meta's LLaMA model
* Flutter framework
* HuggingFace's transformers library
* Flask framework
* ngrok

