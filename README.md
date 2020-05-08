# Simple Blockchain API

A simple JSON API in Python and Flask to mine, create transactions, register and resolve nodes in the blockchain. This was made to learn blockchain better.
![image of the blockchain](/chain-long.png)

## Getting Started
1. Activate and run server in virtual environment
```
$ . ./venv/bin/activate
$(venv) flask run
```
2. The server will run on http://127.0.0.1:5000

## How it works
1. Create a new trasaction
```
curl --header "Content-Type: application/json" \
  --request POST \
  --data '{"sender": "<your-sender-id/name>","recipient": "<your-recipient-id/name>", "amount": "<your-transaction-amount>"}' \
  http://127.0.0.1:5000/transactions/new
```
2. Mine the blockchain
```
curl -X GET http://127.0.0.1:5000/mine
```
3. Fetch the whole blockchain
```
curl -X GET http://127.0.0.1:5000/chain
```

## Register a new node in the app
1. Run the app on a different port simultaneously
```
export FLASK_RUN_PORT=8000
flask run
```
2. Register a new node in the app
```
curl --header "Content-Type: application/json" \
  --request POST \
  --data '{nodes: ['http://127.0.0.1:8000']}' \
  http://127.0.0.1:5000/nodes/register
```

## Resolve a chain node mismatch
```
curl -X GET http://127.0.0.1:5000/nodes/resolve
```
