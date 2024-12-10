# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input parameters. Specifically, the code lacks validation for the user ID, which can lead to unexpected behavior or crashes if a non-numeric ID is provided.

## Bug

The `bug.js` file contains an Express.js route handler that retrieves a user based on their ID.  However, it doesn't handle cases where the `id` parameter is not a valid integer.  Attempting to parse a non-numeric string with `parseInt()` will lead to `NaN`, resulting in the `find()` method not finding the user. While the code includes a check for the user not being found (returning 404), it doesn't address this initial invalid input issue.

## Solution

The `bugSolution.js` file demonstrates the corrected route handler. It includes input validation to check if the `userId` is a valid integer.  If not, it returns an appropriate error response to the client (e.g., 400 Bad Request). This prevents unexpected behavior and provides better error handling for the application.