# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js applications: server unresponsiveness caused by long-running synchronous operations within the request handler.  The `server.js` file shows a server that hangs for 5 seconds, blocking all other requests.  The solution is to refactor the code to use asynchronous operations to prevent blocking the event loop.

## Bug

The server in `server.js` uses a `while` loop to simulate a long-running task.  This blocks the event loop, making the server unresponsive to new requests during this period.  This is a classic example of blocking I/O and should be avoided.

## Solution

The solution, provided in `serverSolution.js`, demonstrates the proper approach.  It uses asynchronous operations (e.g., `setTimeout`) or other asynchronous techniques (like promises or async/await) to avoid blocking the event loop.  This allows the server to continue handling requests even during long-running operations.