# btb

locally run blue text bot with editable memory.  this is a super early work in progress!

![btb](https://github.com/bwasti/btb/assets/4842908/3bcf624e-697e-4e8f-bbf7-2ab58256646e)


the code is built on ollama and does two things:

1. uses messages for communication (you'll need a mac and a separate apple account)
2. uses json for "memory" and lets you edit that directly in the browser

## Usage

install Ollama https://ollama.com

```
ollama pull llama3
pip install -r requirements.txt
```

then run the service

```
python service.py
```

## How it works

Messages

1. Parse `~/Library/Messages/chat.db` to get the most recent text (every 1 second)
2. Use applescript (`send.applescript`) to send a response message

JSON

1. Inject the most recent "memory" as JSON into the ollama chat history
2. Ask a separate model (prompted for JSON output, using `format=json`) to summarize any new information and update the JSON
3. Run a server (flask with websockets) to make the JSON live editable by the user in the browser
