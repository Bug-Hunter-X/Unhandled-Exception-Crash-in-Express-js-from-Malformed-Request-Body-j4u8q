# Unhandled Exception in Express.js from Malformed Request Body

This repository demonstrates a common error in Express.js applications: crashing due to unhandled exceptions when the request body is malformed or missing expected fields.  The bug occurs because there is insufficient error handling when accessing properties of the request body (req.body).

## Bug

The `bug.js` file contains an Express.js application that creates a new user based on data received in a POST request to `/user`.  It directly accesses `req.body.name`, which will throw an exception if `req.body` is undefined, or if `req.body` does not contain a `name` property. This results in the server crashing.

## Solution

The `bugSolution.js` file corrects the error by adding comprehensive error handling. It checks if `req.body` and `req.body.name` are defined before accessing them.  Appropriate error responses are returned to the client if the request is malformed.