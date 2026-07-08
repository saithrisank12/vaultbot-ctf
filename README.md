# VaultBot CTF — The Whispering Vault

A Flask-based AI Security CTF challenge chatbot powered by Claude.

## Local Development

```bash
# 1. Create & activate virtualenv
python -m venv venv
.\venv\Scripts\Activate.ps1     # Windows PowerShell
# source venv/bin/activate       # macOS/Linux

# 2. Install deps
pip install -r requirements.txt

# 3. Set your API key
$env:ANTHROPIC_API_KEY = "sk-ant-..."

# 4. Run
python app.py
# → http://localhost:5000
```

## Deployment (Render.com)

1. Push this repo to GitHub.
2. Go to https://dashboard.render.com → **New → Blueprint**.
3. Connect your repo — Render reads `render.yaml` automatically.
4. Set `ANTHROPIC_API_KEY` in **Environment → Secret Files** when prompted.
5. Click **Apply** — Render builds and deploys.

## Project Structure

```
project/
├── app.py               # Flask app + Claude API + output filter
├── requirements.txt     # flask, requests, gunicorn
├── render.yaml          # Render deployment blueprint
├── .gitignore
└── templates/
    └── index.html       # Premium dark-themed chat UI
```

## Challenge

Flag format: `CYBERSTRIKE{...}`  
Two defences stand between you and the flag:  
1. A system prompt telling the model never to reveal it.  
2. An output filter blocking obvious leaks.

Find a creative way around **both**.
