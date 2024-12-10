# Express.js JSON Body Parsing Error

This repository demonstrates a common error encountered when working with JSON request bodies in Express.js applications. The bug arises from incorrect usage of body-parser middleware, leading to the application failing to parse incoming JSON data.

## Bug Description:
The application fails to parse the JSON request body, resulting in `req.body` being empty or undefined. This typically manifests as an unexpected behavior when processing the request.

## Bug Solution:
The solution involves ensuring the correct usage of the `express.json()` middleware before defining routes that expect JSON data.  This middleware parses the incoming request body as JSON and makes it available in `req.body`.  If other body types are expected, use `express.urlencoded()` as well.

## How to Reproduce the Bug:
1. Clone this repository.
2. Run `npm install`.
3. Run `node bug.js`.
4. Send a POST request to `http://localhost:3000/data` with a JSON payload (e.g., using curl or Postman).
5. Observe that the server receives the request but `req.body` is empty, causing the application to fail.

## How to Fix the Bug:
1. Examine the file `bugSolution.js` to understand the correct usage of `express.json()` middleware.
2. Note how the middleware is placed before the route handler in the corrected code.
3. Run `node bugSolution.js` to observe the successful parsing of the JSON request body. 