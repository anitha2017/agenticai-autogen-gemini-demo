# Demo Instructions
This lab practice demonstrates how to get started with [Autogen](https://github.com/microsoft/autogen) framework. 

# Create and Navigate to Demo folder
Clone autogen experiments from Developer advocate.

	$ cd <parent directory>
	$ git clone https://github.com/anitha2017/agenticai-autogen-gemini-demo.git

# Create and activate the virtual environment
	$ python3 -m venv .venv
	$ .\.venv\Scripts\activate

# Install requirements.txt
	autogen-agentchat[llm,gemini]~=0.2
	autogen
	google-generativeai 
	vertexai
	ag2[gemini]
	agentops

	$ pip install -r requirements.txt
	
# Get the API keys and populate the keys in model_config.json
https://aistudio.google.com/app/apikey

# Download and Install ollama using https://ollama.com/ , then run gemma model.

	## list and run ollama model
	
	PS C:\Users\Anitha> ollama ls
	NAME            ID              SIZE      MODIFIED
	gemma:latest    a72c7f4d0a15    5.0 GB    5 days ago
	PS C:\Users\Anitha> ollama run gemma
	>>> Give me a famous quote from Aristotle?
	"To understand something, one must first comprehend its essence."

	>>> height of eiffel tower
	The height of the Eiffel Tower is 1,063 feet (324 meters).

	>>> /bye
	PS C:\Users\Anitha>

	## Test model response
	Invoke-WebRequest -Uri "http://localhost:11434/api/generate" `
    -Method Post `
    -Headers @{"Content-Type"="application/json"} `
    -Body '{
        "model": "gemma",
        "prompt": "height of eiffel tower?",
        "stream": false,
        "options": {
            "temperature": 0.2
        }
    }'
	
# Run the Multi-Agent lab program.
	
	$ python cfp1-multi-agent-interaction.py
	$ python cfp2-multi-agent-interaction.py
	$ python human-autoagent-interaction-using-gemini.py
	$ python human-autoagent-interaction-using-local_llm_gemma.py

# References:

[Autogen] with [Gemini] 
https://github.com/rominirani/autogen-experiments.git