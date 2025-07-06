---
title: "Amazon Q: Dev Project"
date: "`r Sys.Date()`"
weight: 7
chapter: false
pre: " <b> 4.10.7 </b> "
---

#### Amazon Q: Dev Project

Amazon Q Developer helps you create implementation plans for code changes. Open the panel in your IDE, type "/dev" and press Enter to start a dev project.

##### Example: Web Page Dev Plan
**Prompt:**
I need a web page with a name input box, a submit button, an API call, and a display of the returned result.

**Amazon Q Answer:**
Here are the steps needed to accomplish the task:

1. Create a React app
   - Run `npx create-react-app my-app`
   - `cd my-app`

2. Add an API client
   - `npm install axios`

3. Create the `NameForm.jsx` component
   - `src/components/NameForm.jsx`
   - Define `state` with a `name` property
   - Add `<input>` and `<button>`
   - Add handlers to update `name` on input change and call the API on button click

4. Create an API call function
   - `src/api.js`
   - `async function submitName(name) {...}`
   - Make a POST request to the API with the name
   - Return the response

5. Render the response
   - `NameForm.jsx`
   - Add a `response` property to `state`
   - On a successful response, update `response`
   - Conditionally render the response or the form

6. Add tests
   - `NameForm.test.jsx`
   - Test the initial render
   - Test that input changes update the state
   - Mock the API call
   - Test that submitting calls the API and updates the response

7. Add error handling
   - `NameForm.jsx`
   - Add an error state property
   - Catch errors in the API call
   - Update the error state
   - Conditionally render the error

> **Note:** Amazon Q can generate step-by-step dev plans for your coding projects.