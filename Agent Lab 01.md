# Copilot Studio Lab: Password Support Agent

This lab will guide you through the step-by-step process of building a simple support agent in Microsoft Copilot Studio. The agent will assist users in resetting passwords or unlocking their accounts.

## Objective

Create a Tech Support Agent that responds to common requests:

* Reset my password
* Unlock my account

## Step-by-Step Instructions

### Step 1: Create a New Tool (Custom Prompt)

1. Go to the **Tools** tab.
2. Click on **+ New tool** (blue button).
3. Select **Prompt** as the tool type.
4. In the text field that says *Describe what you want your prompt to do…*, paste:

   ```
   Answer the user's technical question with a simple explanation. Use friendly tone and, when relevant, include an example or short code snippet.
   ```

   This tells the AI how to behave: simplify, explain, and optionally use examples.   
5. Press **Enter** or click the arrow button to generate the preview.
6. When a variable appears at the bottom (usually called Technical Question), click it.
7. Change the **Name** to `question`.
8. Set **Sample data** to:

   ```
   What is the difference between Azure Blob Storage and Azure Files?
   ```
9. Click **Close**.

<img width="919" height="333" alt="image" src="https://github.com/user-attachments/assets/96797bd1-dba7-45c6-9098-61b1983d93d5" />

10. Click **Test** (top-right), select the sample data, and ensure the output makes sense. This step confirms the prompt logic works as intended.
    
11. Click **Save**.
    
12. In the required **Description** for the agent to know when to use this tool, enter:

    ```
    This tool helps answer technical questions in a clear and friendly way, with simple examples when needed.
    ```
13. Click **Add**.
14. Click **Save** to save it.

The tool is now ready for use by an agent.

---

### Step 2: Create a New Agent


1. Navigate to the **Agents** section.
2. Click on **+ New agent**.
3. Click **Skip to configure** (top-right corner) to bypass the wizard and set up manually.
4. Name your agent: `AI Tech Support Agent`.
5. Description:

   ```
   This agent helps users get clear answers to technical questions in simple language. It is intended for employees or customers who need quick, understandable support for IT and cloud-related topics.
   ```
6. Instructions:

   ```
   This agent answers users’ technical questions in a clear, simple, and friendly manner. It reads each question carefully, provides a straightforward explanation, and avoids unnecessary technical jargon. When relevant, it uses examples or code snippets to clarify the answer.
   ```

   <img width="551" height="857" alt="image" src="https://github.com/user-attachments/assets/35f79a94-ebdb-4043-b5a8-61fb25b1af8b" />

7. Click **Create**.

---

### Step 3: Add the Custom Prompt Tool to the Agent

1. In the agent view, go to the **Tools** tab.
2. Click **Add tool**.
3. Select the tool: `Custom prompt` (or the name you see).
4. Click **Add to agent** to confirm the addition.

---

### Step 4: Create a New Topic

1. Navigate to the **Topics** tab.
2. Click **+ Add a topic → From blank**.
3. Name the topic: `Forgot Password`.

---

### Step 5: Define the Trigger

1. In the **Trigger** section, leave it as **The agent chooses**.

   This allows Copilot to match user input using AI intent recognition.

---

### Step 6: Ask the User a Question

1. Click the **+** under the trigger.
2. Select **Ask a question**.
3. In the prompt text, type: `What do you need help with?`
4. Add options:

   * Reset my password
   * Unlock my account

<img width="324" height="632" alt="image" src="https://github.com/user-attachments/assets/d1a76c67-bbb2-4c1b-955d-ef107d8f769b" />

For each condition box enter:

**Condition 1: Reset my password**

* **is equal to**  `Reset my password`
* Click on the (+) button and than choose **Send a message**.
* At the Message box, past this:

  ```
  To reset your password, please follow this link: https://reset.yourdomain.com

  If you need further help, let me know!
  ```

**Condition 2: Unlock my account**

* **is equal to**  `Unlock my account`
* Click on the (+) button and than choose **Send a message**.
* At the Message box, past this:

  ```
  To unlock your account, please contact IT support at it-support@yourdomain.com or call extension 1234.
  ```

**All Other Conditions**

* Under **All other conditions** click on the (+) button and than choose **Send a message**.
* At the Message box, past this

  ```
  I'm sorry, I can't help with that request right now. Please contact our support team for further assistance.
  ```

This is a fallback for unmatched user inputs.

<img width="680" height="637" alt="image" src="https://github.com/user-attachments/assets/b9f993cf-cb23-4797-a420-4f7bb38c165f" />


---

### Step 8: Save and Publish

1. Click **Save** (top right).
2. Click **Publish** (top right) to deploy the topic.

---

### Step 9: Test the Agent

1. Click the **Test** button (top-right).
2. Enter inputs like:

   * I forgot my password
   * I need to unlock my account
   * I need help with VPN
3. Verify each path displays the correct message.

---

## Lab Complete ✅
