# Simple Blockchain API

A simple JSON API in Python and Flask to mine a new block, create transactions, register and resolve nodes in the blockchain. This was made to help learn blockchain better.
![image of the blockchain](/chain-long.png)

## Prerequisites
- Python 3.6+
- Flask
- venv (Python virtual environment)

## Getting Started
1. Activate and run server in virtual environment
```bash
$ source ./venv/bin/activate
(venv) $ flask run
```
2. The server will run on http://127.0.0.1:5000

## Features
- Create new transaction &rarr; (POST) /transactions/new
- Mine a new block &rarr; (GET) /mine
- Fetch the whole blockchain &rarr; (GET) /chain
- Register a new node in the network &rarr; (POST) /nodes/register
- Resolve chain conflict &rarr; (GET) /nodes/resolve

## Register a new node in the network
1. Run the app on a different port simultaneously
```bash
$ source ./venv/bin/activate
(venv) $ flask run
(venv) $ export FLASK_RUN_PORT=8000
(venv) $ flask run
```
2. Send a POST request to /nodes/register with the following JSON data
```JSON
{
  "nodes": ["http://127.0.0.1:8000"]
}
```
