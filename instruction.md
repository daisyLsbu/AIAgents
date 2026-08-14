# Phase 1 (for terminal chat)
1. agent.py  works independently, requirements file 
2. install Ollama

cd $HOME\dAIsy\local-agent
# create + activate a virtual environment
python -m venv .venv
.\.venv\Scripts\Activate.ps1
# install the ollama python client
pip install -r requirements.txt
python.exe -m pip install --upgrade pip
# make sure a model is pulled (skip if you already have one)
ollama pull llama3.1:8b
# run the agent 
python agent_standalone.py
# further Agent command
python agent.py --reset : clear memory 
--model <tag> to use a different pulled model.

# Phase 2: api chat instead of terminal
agent_core, agent, server.py, requirements.txt updated
# start the local API server and chat with API 
2 terminal with venv : pip install -r requirements.txt
uvicorn server:app --host 127.0.0.1 --port 8000
curl -Method Post http://127.0.0.1:8000/chat -Body '{"message":"hello"}' -ContentType "application/json"