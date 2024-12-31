# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input.  Specifically, the provided code lacks checks for non-numeric user IDs.

## Bug Description
The `/users/:id` route attempts to access a user based on the `id` parameter.  However, it directly parses the `id` as an integer without any validation. If the `id` parameter is not a valid integer (e.g., a string or a non-existent user), the code will throw an error or produce unexpected results.

## How to Reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run `node bug.js`.
4. Send a GET request to `/users/abc` or `/users/12345` (assuming no user with that ID exists). The application will either crash or return an incorrect response. 

## Solution
The solution involves adding input validation and error handling to gracefully handle invalid user IDs. The `bugSolution.js` file demonstrates the correct implementation.