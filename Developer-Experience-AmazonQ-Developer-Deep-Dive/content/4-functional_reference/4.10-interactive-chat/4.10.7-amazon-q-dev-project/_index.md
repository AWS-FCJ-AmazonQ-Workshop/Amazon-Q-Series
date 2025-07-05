---
title: "Amazon Q: Dev Project"
date: "`r Sys.Date()`"
weight: 7
chapter: false
pre: " <b> 4.10.7. </b> "
---


#### Amazon Q: Dev Project

Amazon Q Developer helps you create implementation plans for code changes. Open the panel in your IDE, type "/dev" and press Enter to start a dev project.

#### Example: Web Page Dev Plan
**Prompt:**
Tôi cần một trang web có ô nhập tên, nút gửi, gọi API và hiển thị kết quả trả về.

**Amazon Q Answer:**
Amazon Q sẽ tạo kế hoạch triển khai chi tiết cho yêu cầu phát triển này.

> **Note:** Amazon Q can generate step-by-step dev plans for your coding projects.
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
Here are the steps needed to accomplish the task:

Create a React app
Run `npx create-react-app my-app`
`cd my-app`
Add API client
`npm install axios`
Create `NameForm.jsx` component
`src/components/NameForm.jsx`
Define `state` with `name` property
Add `<input>` and `<button>`
Add handlers to update `name` on input change and call API on button click
Create API call function
`src/api.js`
`async function submitName(name) {...}`
Make POST request to API with name
Return response
Render response
`NameForm.jsx`
Add `state` property `response`
On success response, update `response`
Conditionally render response or form
Add tests
`NameForm.test.jsx`
Test initial render
Test input change updates state
Mock API call
Test submit calls API and updates response
Add error handling
`NameForm.jsx`
Add error state property
Catch errors in API call
Update error state
Conditionally render error