# How to use the API for InstructLab


## Using an --api-key

When using the llama.cpp backend, if you are using a `--api-key` (made possible with https://github.com/instructlab/instructlab/pull/2597) you can force tokens for your API requests, here is an example with the token set to `token-1234 `

```
curl -X 'POST' \
  'http://98.80.168.118:8000/v1/completions' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer token-1234' \
  -H 'Content-Type: application/json' \
  -d '{
  "prompt": "\n\n### Instructions:\nWhat is the capital of France?\n\n### Response:\n",
  "stop": [
    "\n",
    "###"
  ]
}'
```



Another example:
```
curl -X 'POST' \
  'http://98.80.168.118:8000/v1/chat/completions' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer ansible123!' \
  -d '{
  "model": "gpt-3.5-turbo",
  "messages": [
    {
      "role": "system",
      "content": "You are a helpful assistant."
    },
    {
      "role": "user",
      "content": "What is the capital of France?"
    }
  ]
}'
```

curl -X 'POST' \
  'http://98.80.168.118:8000/v1/chat/completions' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer ansible123!' \
  -d '{
  "messages": [
    {
      "role": "system",
      "content": "you use the word uh and huh in your responses to sound more human"
    },
    {
      "role": "user",
      "content": "What is the capital of France?"
    }
  ]
}'
