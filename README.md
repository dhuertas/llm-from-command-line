# llm-from-command-line
Access Ollama LLMs from the command line.

## How to use it
Copy the python script to any directory in your PATH environment variable, e.g. `~/.local/bin`, and add execution permision `chmod +x ~/.local/bin/llm`. Adjust the script global variables to make it work with the Ollama instance (URL, default model and model parameters, configuration directory, etc.).

The script creates and uses a hidden directory in the user's $HOME path to store conversations and secrets (Google Search API key).

## Requirements
There is no requirements.txt file yet. However, it should be possible to use it by installing python3 packages (i.e. using the distro package manager), given some trial and error is done until all the packages are installed.

## Example

Here's a couple of examples using the tool:

```bash
:~$ llm --help
usage: llm [-h] [-i INPUT_FILE] [-m MODEL] [-s SYSTEM] [-t TOPIC] [-d] [-g] [-w] [-T TEMPERATURE] [-S] input

Ollama command line client

positional arguments:
  input                 input prompt

options:
  -h, --help            show this help message and exit
  -i INPUT_FILE, --input-file INPUT_FILE
                        Input file
  -m MODEL, --model MODEL
                        Model to use
  -s SYSTEM, --system SYSTEM
                        Initial system prompt
  -t TOPIC, --topic TOPIC
                        Chat topic
  -d, --documents       Show retrieved documents
  -g, --google          Search Google for relevant documents
  -w, --wikipedia       Search Wikipedia for relevant documents
  -T TEMPERATURE, --temperature TEMPERATURE
                        LLM temperature (default: 0.4)
  -S, --stream          Whether the LLM should stream the response tokens
```

```bash
:~$ llm "what is the square root of Pi?"
The square root of π (pi) is an irrational number, meaning it cannot be expressed as a simple fraction. However, we can approximate its value to a certain degree of precision. For example:

Square root of pi ≈ 1.77245385091

This approximation has been rounded to 7 decimal places. The actual square root of π is an irrational number and cannot be expressed as a finite decimal or a simple fraction.
```

```bash
:~$ llm --google "what is the stock price of apple?"
Search keywords:  [('stock price', 4.0), ('apple', 1.0)]
The current stock price of Apple is $176.55 as of the time this response was generated. This information was obtained from the Yahoo Finance website, which provides real-time stock prices for AAPL (Apple Inc.). The data is subject to change and should be verified using the provided links.
```
