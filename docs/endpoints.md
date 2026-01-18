# GET /v4/quote

Fetch the best swap quote for tokens on Solana.

Base URL: https://quote-api.jup.ag/v4/quote

Query Parameters:

Parameter     | Type   | Required | Description
------------- | ------ | -------- | -----------------------------------
inputMint     | string | yes      | Token to swap from (mint address)
outputMint    | string | yes      | Token to swap to (mint address)
amount        | int    | yes      | Amount in smallest unit
slippageBps   | int    | no       | Allowed slippage in basis points

Example Request (Python):

import requests

url = "https://quote-api.jup.ag/v4/quote"
params = {
    "inputMint": "So11111111111111111111111111111111111111112",
    "outputMint": "Es9vMFrziS4hK5PB5cMfd6yfQZrN7kRznh8L5TGMDrkQ",
    "amount": 1000000
}
response = requests.get(url, params=params)
print(response.json())

Example Response:

{
  "data": [
    {
      "inAmount": 1000000,
      "outAmount": 950000,
      "route": [...]
    }
  ]
}

