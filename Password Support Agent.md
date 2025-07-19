# Copilot Studio Lab: Password Support Agent

This lab will guide you through the step-by-step process of building a simple support agent in Microsoft Copilot Studio. The agent will assist users in resetting passwords or unlocking their accounts.

## Objective

Create a Tech Support Agent that responds to common requests:

* Reset my password
* Unlock my account

## Step-by-Step Instructions

### Step 1: Create a New Tool (Custom Prompt)

**🎯 Goal:** Create a reusable AI-powered tool to answer technical questions with clarity and friendliness.

**🔎 Why this matters:**
This tool acts as a building block for AI responses. Once it's built, it can be reused in different agents or flows.

1. Go to the **Tools** tab.
2. Click on **+ New tool** (blue button).
3. Select **Prompt** as the tool type.
4. In the text field that says *Describe what you want your prompt to do…*, paste:

   ```
   Answer the user's technical question with a simple explanation. Use friendly tone and, when relevant, include an example or short code snippet.
   ```

   This tells the AI how to behave: simplify, explain, and optionally use examples.   
6. Press **Enter** or click the arrow button to generate the preview.
7. When a variable appears at the bottom (usually called Technical Question), click it.
8. Change the **Name** to `question`.
9. Set **Sample data** to:

   ```
   What is the difference between Azure Blob Storage and Azure Files?
   ```
10. Click **Close**.

<img width="919" height="333" alt="image" src="https://github.com/user-attachments/assets/96797bd1-dba7-45c6-9098-61b1983d93d5" />

11. Click **Test** (top-right), select the sample data, and ensure the output makes sense.

    This step confirms the prompt logic works as intended.
12. In the required **Description** for the agent to know when to use this tool, enter:

    ```
    This tool helps answer technical questions in a clear and friendly way, with simple examples when needed.
    ```
13. Click **Save**.

The tool is now ready for use by an agent.

---

### Step 2: Create a New Agent

**🎯 Goal:** Define a digital agent that uses the tool we created to respond to questions.

**🔎 Why this matters:**
The agent is the interface users interact with. Connecting it to the tool makes it intelligent and helpful.

1. Navigate to the **Agents** section.
2. Click on **+ New agent**.
3. Click **Skip to configure** (top-right corner) to bypass the wizard and set up manually.
4. Name your agent: `Tech Support Agent`.
5. Description:

   ```
   This agent helps users get clear answers to technical questions in simple language. It is intended for employees or customers who need quick, understandable support for IT and cloud-related topics.
   ```
6. Instructions:

   ```
   This agent answers users’ technical questions in a clear, simple, and friendly manner. It reads each question carefully, provides a straightforward explanation, and avoids unnecessary technical jargon. When relevant, it uses examples or code snippets to clarify the answer.
   ```
7. Click **Create**.

---

### Step 3: Add the Custom Prompt Tool to the Agent

**🎯 Goal:** Make the tool available for the agent to use in conversations.

**🔎 Why this matters:**
Without adding the tool to the agent, the agent won’t know it exists or be able to use it.

1. In the agent view, go to the **Tools** tab.
2. Click **Add tool to agent**.
3. Select the tool: `Custom prompt` (or the name you see).
4. Confirm the addition.

---

### Step 4: Create a New Topic

**🎯 Goal:** Define a structured interaction (flow) around common password-related issues.

**🔎 Why this matters:**
Topics let you create guided conversations with users, such as password recovery flows.

1. Navigate to the **Topics** tab.
2. Click **+ Add a topic → From blank**.
3. Name the topic: `Forgot Password`.

---

### Step 5: Define the Trigger

**🎯 Goal:** Let the agent decide when to activate this topic.

**🔎 Why this matters:**
The trigger defines when this flow will be invoked based on user input.

1. In the **Trigger** section, leave it as **The agent chooses**.

   This allows Copilot to match user input using AI intent recognition.

---

### Step 6: Ask the User a Question

**🎯 Goal:** Understand what the user actually needs help with.

**🔎 Why this matters:**
Asking the user a clarifying question ensures we offer the correct path for help.

1. Click the **+** under the trigger.
2. Select **Ask a question**.
3. In the prompt text, type: `What do you need help with?`
4. Add options:

   * Reset my password
   * Unlock my account

<img width="324" height="632" alt="image" src="https://github.com/user-attachments/assets/d1a76c67-bbb2-4c1b-955d-ef107d8f769b" />


   We’ll use this variable in the next step to branch the flow.

---

### Step 7: Add Condition Nodes

**🎯 Goal:** Handle user responses with specific guidance.

**🔎 Why this matters:**
Conditions personalize the conversation flow based on user answers.

1. Click **+** below the question to add a **Condition** block.

**Condition 1: Password Reset**

* **If:** userIssue equals `Reset my password`
* **Then:** Add a **Message**:

  ```
  To reset your password, please follow this link: https://reset.yourdomain.com

  If you need further help, let me know!
  ```

**Condition 2: Unlock Account**

* **If:** userIssue equals `Unlock my account`
* **Then:** Add a **Message**:

  ```
  To unlock your account, please contact IT support at it-support@yourdomain.com or call extension 1234.
  ```

**All Other Conditions**

* Under **All other conditions**, add:

  ```
  I'm sorry, I can't help with that request right now. Please contact our support team for further assistance.
  ```

This is a fallback for unmatched user inputs.

---

### Step 8: Save and Publish

**🎯 Goal:** Finalize and deploy the work so users can interact with it.

**🔎 Why this matters:**
Until you publish, your changes are saved locally and won’t be used in live environments.

1. Click **Save** (top right).
2. Click **Publish** (top right) to deploy the topic.

---

### Step 9: Test the Agent

**🎯 Goal:** Verify the full flow is working as expected.

**🔎 Why this matters:**
Testing validates the end-user experience and ensures the logic works properly.

1. Click the **Test** button (top-right).
2. Enter inputs like:

   * I forgot my password
   * I need to unlock my account
   * I need help with VPN
3. Verify each path displays the correct message.

---

## Lab Complete ✅

You have now built a working support agent in Copilot Studio with:

* A prompt-based tool for answering technical questions
* A topic that handles common user issues
* A full test and publish flow

**Next steps:**

* Add more tools (e.g., summarize emails, explain commands)
* Build flows for common IT tasks
* Connect to data or external APIs

**End of lab file**
