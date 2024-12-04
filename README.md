# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input parameters.  Specifically, this example shows a route that fetches a user by ID, but lacks proper validation and error handling if the ID is not a valid number.

## Bug

The `bug.js` file contains the erroneous code. The route handler attempts to parse the `userId` as an integer using `parseInt()`.  However, if the `userId` is not a number (e.g., a string or undefined), `parseInt()` will return `NaN`, leading to unexpected behavior or crashes when accessing the `user` array.

## Solution

The `bugSolution.js` file provides a corrected version of the code. It includes error handling to check if `userId` can be parsed as an integer and handles the case where the user is not found.  This robust error handling prevents unexpected issues and provides a better user experience.

## How to reproduce the bug

1. Clone the repository.
2. Run `npm install` to install Express.js.
3. Run `node bug.js`.
4. Access the route with an invalid ID (e.g., `/users/abc`).  Observe the error.