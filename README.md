# AI-Interview-Agent
#Project Overview

This project is an MVP (Minimum Viable Prototype) of a conversational AI agent designed to conduct real-time, human-like interviews. The agent is built to simulate an admissions or HR team member, capable of interviewing candidates, collecting structured data, answering common questions, and providing a summary for human review. This system serves as a foundational prototype for a voice-based application.

The project is designed to be run in a Google Colaboratory notebook, making it easy to set up and use without a local development environment.

#Architecture

The agent's architecture is a multi-step workflow orchestrated by a central LLM.

1. Voice Interface: The system utilizes a Text-to-Speech (TTS) engine to convert the agent's LLM-generated responses into spoken words and a Speech-to-Text (STT) engine to transcribe the candidate's spoken answers back into text.

2. LLM-Powered Conversational Flow: The core of the agent is an LLM that is prompted to act as an interviewer. The prompt design ensures the agent asks a series of specific questions in a logical sequence, handles conversational turns, and waits for a response before proceeding.

3. Data Collection: As the conversation progresses, the agent collects and stores the candidate's responses in a structured format. This is handled by parsing the transcribed text and mapping it to predefined data fields.

4. Summary Generation: Upon completion of the interview, the agent uses the collected structured data and the full transcript of the conversation to generate a concise summary. This summary is designed to highlight key points, making it easy for a human reviewer to quickly assess the candidate.

#Tools and Libraries

This project was developed using the following tools and libraries:
1. Python: The core programming language for the agent's logic.
2. Google Colab: The cloud-based notebook environment used for development and execution.
3. LangChain (or similar framework): Used for prompt orchestration, managing the conversational chain, and integrating various components (optional, depending on implementation).
4. Google's Generative AI API: A powerful LLM service used to power the conversational and summarization tasks.
5. Speech-to-Text (STT) and Text-to-Speech (TTS) Libraries: Used for handling the voice interface. This can be integrated via services like Google Cloud Speech-to-Text and Text-to-Speech.

#API Keys Setup

This project requires access to an LLM service. Follow these steps to set up your API key:
1. Obtain a Google API Key from the Google AI Studio.
2. Create a .env file in the project's root directory.
3. Add your API key to the file in the following format:   GOOGLE_API_KEY="your_api_key_here"
4. Ensure your code loads this environment variable securely to authenticate API calls.

#Known Limitations and Future Work
As an MVP, this prototype has several known limitations that can be addressed in future development.
Current Limitations:
1. Basic Voice Integration: The current voice integration may have noticeable latency and is built with basic speech control.
2. Simple State Management: The agent’s conversational state is handled in-memory, meaning it will not persist across different sessions.
3. No Database Integration: Candidate data is not stored in a persistent database, so information is lost when the application is closed.

#Future Work:
1. Enhanced Voice Experience: Integrate a more advanced voice provider for reduced latency and more natural-sounding voice. Implement better turn-taking logic and barge-in functionality for a seamless conversational flow.
2. Database Integration: Connect the agent to a database (e.g., Firestore) to persistently store candidate data and interview transcripts.
3. Advanced Features: Implement bonus features like a scheduler integration (e.g., Calendly) and a simple dashboard to view interview summaries and analytics.
4. Improved Error Handling: Add more robust error handling for API call failures and transcription errors to make the agent more resilient.
