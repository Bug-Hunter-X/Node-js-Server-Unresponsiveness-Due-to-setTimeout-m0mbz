# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a server becomes unresponsive due to long-running operations within request handlers.  The example uses `setTimeout` to simulate a delay, but this could represent any blocking operation.  The solution shows how to avoid this by using asynchronous operations or offloading work to other processes.

## Bug
The `bug.js` file contains a simple Express.js server with a 5-second delay in its response handling.  During this delay, the server will not respond to any new requests, leading to apparent unresponsiveness.

## Solution
The `bugSolution.js` file demonstrates using asynchronous operation (`Promise.resolve`) to resolve the issue.  This allows the server to remain responsive while the time-consuming operation runs in the background.  For more complex situations, consider using task queues or worker processes to handle long-running tasks without blocking the main thread.