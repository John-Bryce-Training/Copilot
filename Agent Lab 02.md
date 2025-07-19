# Copilot Studio Lab: Agent Lab 02

## Objective

Enhance your AI Tech Support Agent from the previous exercise by integrating **Agent Flows**. The goal is to allow your agent to trigger an automated action, such as sending a password reset email, in response to user requests.

---

## Step 1: Create a New Flow

1. Go to the **Flows** tab in Copilot Studio.
2. Click **+ New agent flow**.
3. For the trigger, choose **When an agent calls the flow**. (This allows the agent to invoke the flow from within a conversation.)
4. Click **+** under the trigger and add a **Send an email (V2)** (under Office 365 Outlook) step.
5. Confirm you login with your free trail username and password.
6. Fill the feilds bellow:

   * To: Set your private email address' like "IsraelLevy@gmail.com".
   * Subject: `Have a nice day!`
   * Body: `We wish you a pleasant and productive day at work!`
7. Click **Save draft** and than **Publish**.

Notes: your flow is saved under "Untitled" name by default.
---

## Step 2: Connect the Flow to Your Agent

1. Open the **Agent** you created earlier (e.g., `AI Tech Support Agent`).
2. Go to the **Topcs** tab inside the agent settings.
3. Click **Add a topic**.
4. Select your flow (`Forgot Password`) and click **Add to agent**.

---

## Step 3: Update the “Forgot Password” Topic

1. Go to the **Topics** tab in your agent.
2. Edit the topic called **Forgot Password**.
3. At the **Optionas for user** add a new condition by clicking **+New option** and type **Send an email**.
4. From the new condition select for **(+)** and at the new menu select for **Add a tool** and than choose your **Untitled** tool from **Tool** tab.

<img width="297" height="408" alt="image" src="https://github.com/user-attachments/assets/e76e7d79-6482-4faa-8b59-cfe01f4421fc" />

   
5. In the branch for the condition “Send an email” click on the **(+)** and choose for **Sand a message**.
6. At the **Sena a message** box type:

      `The email was sent successfully.`
   
8. Click **Save** to update the topic.

---

## Step 4: Test the Full Flow

1. Click the **Test** button (top-right corner).
2. Enter: `Send an email`.
3. Confirm that the flow is triggered and you receive the appropriate response.

---

## Lab Complete ✅

**You have now:**

* Created a reusable Flow
* Integrated it with your Agent
* Upgraded a conversation to trigger real automation
* Tested the end-to-end experience

---

