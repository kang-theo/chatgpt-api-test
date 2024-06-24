# ChatGPT API Test

[ChatGPT API documentation](https://platform.openai.com/docs/overview)

## Run

```bash
npm i ts-node-dev -g

.env.example --> .env

npm install

tsnd server.ts
```

## Multiple Output

Stream and Server-sent events

### Server-side `server.ts`

1. Start an HTTP server, listening on port 3001
2. When accessing the root directory `/`, return the `index.html` file.
3. When accessing `/chat`:
   - Set the response header `'Content-Type': 'text/event-stream'` (this is a marker for Server-Sent Events).
   - Request the ChatGPT API using the stream mode.
   - Write the response in batches and return it to the frontend.

### Frontend `index.html`

1. Define a new `EventSource(url)` instance.
2. Listen for `onmessage` events and display the messages on the frontend.
3. Send requests to the `/chat` route.
