# Node.js Server Hang on Long Requests

This repository demonstrates a common issue in Node.js servers: hanging on long-running requests.  The `server.js` file contains a server that simulates a long-running operation (5-second delay) within the request handler.  This blocks the event loop, preventing the server from responding to other requests, potentially leading to a denial-of-service situation. The solution is provided in `serverSolution.js`.

## How to Reproduce

1. Clone the repository.
2. Run `node server.js`.
3. Open multiple browser tabs and send requests to `http://localhost:3000`. You'll observe that after a certain number of requests, the server becomes unresponsive to new connections.

## Solution

The solution involves using techniques to handle long-running operations asynchronously, preventing them from blocking the event loop.  Check out `serverSolution.js` for a corrected version of the server that uses asynchronous programming techniques such as promises or async/await to handle long-running tasks without blocking the event loop.