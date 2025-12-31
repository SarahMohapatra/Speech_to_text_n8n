# Speech to text (n8n + Whisper)
Speech to text using n8n and OpenAI's whisper locally and completely free (only for running locally)

## Tech Stack
n8n: Workflow automation (self-hosted via npm).
OpenAI Whisper: Local Speech-to-Text model.
Python: Managed within a dedicated venv (Virtual Environment).

## Setup Instructions

1. Python Environment
Create a virtual environment and install Whisper:
Bash
python -m venv venv
source venv/bin/activate 
pip install openai-whisper

3. Start n8n
Because this workflow uses the Execute Command node, in my local, n8n had certain restrictions. so I had to unhide Execute command node
Mac/Linux: NODES_EXCLUDE="[]" npx n8n start

## How it Works
Manual Trigger: Initiates the workflow.
Read Files: Scans the input/ folder for audio files.
Execute Command (Whisper): Triggers the local Python model to transcribe each file and stores the output in output/ folder. The audio is coverted to all forms such as txt, srt, json, etc
Execute Command: Transfers the completed audio files to the processed/ folder to keep the workspace clean.


