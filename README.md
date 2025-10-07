<h1>🧠 Ivy AI: Agentic Research Assistant</h1>

<h2>✨ Overview</h2>
Ivy AI is an intelligent, agentic web application designed to accelerate academic and technical research. It employs a two-stage workflow to first discover and scrape relevant publications using a powerful commercial LLM, and then synthesize an answer using a local, open-source model (Ollama) through Retrieval-Augmented Generation (RAG).

This approach ensures the research is grounded in high-quality, up-to-date sources while offering privacy and customizability for the final answer generation.

The Agentic Workflow
Phase 1 (Gemini): The user's query is sent to the powerful Gemini 2.5 Pro model, which acts as a specialized research scraper. It finds 3-5 key publications from academic sources (arXiv, IEEE, ACM, etc.) and extracts the Title, Authors, Date, Summary, and a direct URL.

Phase 2 (Ollama RAG): The extracted publications (the context) are sent, along with the original query, to a local Ollama model (e.g., Llama 3). The Ollama model then acts as an expert synthesizer, generating a final answer based ONLY on the provided context.

<h2>🚀 Features</h2>
Two-Stage Agentic Design: Decouples research gathering from synthesis for efficiency and accuracy.

High-Quality Sourcing: Leverages Gemini 2.5 Pro's massive knowledge base to find authoritative academic sources.

Local RAG Synthesis: Uses the Ollama runtime to perform RAG locally, allowing the user to select their preferred open-source model (e.g., Llama 3, Mistral, Gemma).

Structured Data Output: Extracts research details into a clear, parsed format (JSON) before display.

Modern UI: Clean, responsive interface built with Tailwind CSS for a great user experience.

Robust API Handling: Implements exponential backoff and retries for reliable external API communication.

<h2>🛠️ Installation and Setup</h2>
This application is primarily a frontend interface but requires two local services to run the full workflow.

<h2>Prerequisites</h2>
Ollama: Must be installed and running locally. This is the runtime for your local LLM.

Install Ollama version of your choice and change on webpage before running.

Gemini API Key: Required for the research-gathering step.

Get a Gemini API Key

Local LLM: Pull a model using Ollama (e.g., Llama 3 8B, or the default in the code).

<h2>💻 Usage</h2>
Enter Query: Type your research question into the "Your Research Query" text area.

Provide Credentials: Enter your Gemini API Key and the name of the Ollama Model you want to use (default is llama3.2:3b).

Click "Ask Ivy": The application will execute the two-step process:

Phase 1: The loading indicator will show: Step 1/2: Finding research with Gemini...

Phase 2: The loading indicator will show: Step 2/2: Synthesizing answer with Ollama...

View Results: The final synthesized answer and the list of researched sources (with direct links) will appear below the input section.

<h2>⚙️ Configuration (Code Reference)</h2>
All configuration is handled directly within the included JavaScript <script> block.

Variable	Description	Location in Code
model	The Gemini model used for research scraping.	callGeminiApi function
ollama-model	The default local model used for RAG synthesis.	HTML input id="ollama-model"
maxRetries	The number of times the API call will retry on failure.	fetchWithBackoff function
systemInstruction	The core prompt guiding Gemini to act as a research scraper.	callGeminiApi function

Export to Sheets
<h2>🤝 Contributing</h2>
Contributions are welcome! If you have suggestions for improving the RAG prompt, optimizing the Gemini system instruction, or enhancing the UI, feel free to open an issue or submit a pull request.

<h2>📜 License</h2>
This project is licensed under the MIT License. See the LICENSE file for details.
