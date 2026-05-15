1. Why Testing Matters
Testing is like a safety net. In Salesforce, you write code that handles important data (like money or customer names). Testing ensures that when you add something new, you don’t accidentally break what was already working. It gives you confidence that your app is reliable.

2. What is Asynchronous Apex?
Normally, code runs "synchronously" (one line after another, and you have to wait for it to finish). Asynchronous Apex runs in the background. It’s like placing an order at a restaurant and getting a buzzer; you can go do other things, and the work happens whenever the resources are ready. This is used for long tasks so the user doesn't see a "loading" screen forever.

3. What is Salesforce DX?
Salesforce DX (Developer Experience) is a set of tools that lets you develop apps using a computer-first approach rather than just clicking buttons in a browser. It allows you to use tools like VS Code, GitHub, and Command Lines (CLI) to manage your code more professionally.

4. Complete System Workflow
This is the "End-to-End" process you just did:

Setup: Create a project folder on your computer using VS Code.

Connect: Log into your main Salesforce account (the Dev Hub) using the terminal.

Build: Create a temporary "Scratch Org" (like your Dreamhouse org) to do your work.

Code: Write your code or change settings on your computer.

Verify: Check your work against Trailhead or push it to a permanent account.

5. Important Test Cases
Positive Test: Checking if the code works correctly when the user enters the right information (e.g., a phone number has 10 digits).

Negative Test: Checking if the code correctly shows an error when the user enters wrong information (e.g., entering letters in a price field).

Bulk Test: Checking if the code can handle 200 records at once without crashing.

6. Reflection
Enterprise software (big companies) needs structured workflows because many people work on the same code at once. Without a system like DX and GitHub, people would overwrite each other's work. A structured workflow ensures everything is organized, tested, and tracked so the business never stops running.
