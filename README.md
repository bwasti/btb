# btb

locally run blue text bot.  1 python file.  this is a super early work in progress!

![btb](https://github.com/bwasti/btb/assets/4842908/3bcf624e-697e-4e8f-bbf7-2ab58256646e)


the code is built on ollama and does two things:

1. uses imessage for communication (you'll need a mac and a separate apple account)
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
