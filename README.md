# React setInterval Memory Leak
This repository demonstrates a common memory leak in React components that use `setInterval` without proper cleanup in the `useEffect` hook.  The bug is in the `bug.js` file.  The solution, which includes a cleanup function to stop the interval when the component unmounts is in `bugSolution.js`.

## How to reproduce

1. Clone this repository.
2. Navigate to the repository's directory in your terminal.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe that the counter continuously increments even after the component is unmounted in the browser developer tools.

## Solution

The solution involves adding a cleanup function to the `useEffect` hook. This function will stop the interval using `clearInterval` when the component unmounts.