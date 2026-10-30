🎙️ AI Voice Pharmacy Assistant

An AI-powered voice-based pharmacy assistant that enables customers to interact with a virtual pharmacy agent through natural conversations. It can provide medication information, place orders, and retrieve existing order details using real-time voice interaction.

✨ Features
Real-Time Voice Interaction: Communicate naturally with an AI-powered pharmacy assistant.
Medication Information: Retrieve medication descriptions, pricing, and available quantities.
Place Orders: Place medication orders through voice commands.
Order Tracking: Check existing orders using an order ID.
AI-Powered Conversations: Uses OpenAI GPT-4o-mini to understand customer requests.
Speech Recognition: Uses Deepgram Nova-3 for speech-to-text.
AI Voice Responses: Uses Deepgram Aura-2 for text-to-speech.
Real-Time Audio Streaming: Integrates Twilio WebSockets for audio communication.
Function Calling: Allows the AI agent to execute pharmacy operations.
🛠️ Tech Stack
Technology	Purpose
Python 3.12+	Backend development
Deepgram	Speech recognition and voice generation
OpenAI GPT-4o-mini	Conversational AI
WebSockets	Real-time communication
Twilio	Voice call audio streaming
python-dotenv	Environment variable management
JSON	AI agent configuration
📁 Project Structure
text
voice-agent/
│
├── main.py
├── pharmacy_functions.py
├── config.json
├── pyproject.toml
├── uv.lock
├── .gitignore
├── .env
└── README.md

⚙️ Getting Started
1. Clone the Repository
bash
git clone https://github.com/sidharth0909/voice-agent.git
cd voice-agent

2. Install Dependencies

Make sure Python 3.12 or higher is installed.

Using pip:

bash
pip install websockets python-dotenv


Alternatively, if you have UV installed:

bash
uv sync

3. Configure Environment Variables

Create a .env file in the root directory:

env
DEEPGRAM_API_KEY=your_deepgram_api_key


Get your API key from Deepgram.

Important: Never upload your .env file or API keys to GitHub.

4. Run the Application

Start the voice agent server:

bash
python main.py


Or using UV:

bash
uv run python main.py


The WebSocket server starts on:

text
ws://localhost:5000

🧠 How It Works
The application establishes a WebSocket connection with Deepgram's Voice Agent API.
Twilio streams incoming audio to the Python backend.
Deepgram processes the customer's speech.
OpenAI GPT-4o-mini understands the request and determines the appropriate action.
The AI agent calls the relevant pharmacy function.
The backend executes the requested operation.
Deepgram generates a voice response.
The response is streamed back to the customer through Twilio.
💊 Available Pharmacy Functions
1. Get Drug Information

Retrieves medication details, including:

Drug name
Description
Price
Available quantity
2. Place an Order

Allows customers to place medication orders by providing:

Customer's full name
Medication name

The AI assistant confirms the order details before processing.

3. Lookup an Order

Retrieves existing order information using an order ID.

🔐 Security
API keys are stored in environment variables.
.env files should never be committed to version control.
Use .gitignore to prevent accidental exposure of credentials.
⚠️ Important Notes
The current implementation uses in-memory storage for orders, so order records are not persistent across application restarts.
The WebSocket server runs locally on port 5000.
A complete telephony setup requires configuring Twilio to connect to an appropriately accessible WebSocket endpoint.
This project is a demonstration and should not be used for actual medical advice or prescription fulfillment without appropriate clinical, regulatory, and security safeguards.
🚀 Future Improvements
Integrate a persistent database for order management.
Add customer authentication.
Implement prescription verification.
Improve error handling and logging.
Deploy the application to a cloud server.
Add multilingual voice support.
👨‍💻 Author

Sidharth

GitHub: @sidharth0909

⭐ If you find this project interesting, consider giving it a star!
