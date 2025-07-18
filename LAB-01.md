# Create a Customer Service Agent in Copilot Studio

In this exercise, you’ll use Microsoft Copilot Studio to build a simple customer service agent for a fictional business. The agent will help customers with common questions such as business hours, location, services provided, and return policies.

This exercise will take approximately 30–40 minutes to complete.

**Note**: This lab assumes you have already signed up for a free Copilot Studio trial at [https://copilotstudio.microsoft.com](https://copilotstudio.microsoft.com).

## Step 1: Create a New Agent

1. Open your browser and go to [https://copilotstudio.microsoft.com](https://copilotstudio.microsoft.com)
2. Sign in with your Microsoft account.
3. On the home page, select **Create** from the left-hand menu.
4. Click on **New agent**.

> 💡 If the chat creation experience opens, choose **Skip to configure** to enter settings manually.

5. Enter the following details:

   * **Agent name**: `Contoso Support Bot`
   * **Language**: English
   * **Description**: An agent that answers questions about Contoso’s services, hours, and policies.
   * **Tone**: Friendly and professional

6. Click **Create** at the top right to create your agent.

## Step 2: Test the Agent

1. Once the agent is created, select the **Test your agent** pane on the right.
2. Enter the following test prompt:

   ```
   Hello
   ```
3. The agent should respond with a default greeting.
4. Try the following:

   ```
   What are your business hours?
   ```

## Step 3: Add Topics for Common Customer Questions

### Business Hours

1. Go to the **Topics** tab.
2. Select **+ Add a topic** > **Add from description with Copilot**
3. Enter:

   * **Topic name**: `Business Hours`
   * **Prompt**:

     ```
     When a user asks about opening hours or business hours, tell them we’re open Monday to Friday from 9 AM to 6 PM.
     ```
4. Click **Create**, then **Save**

### Store Location

Repeat the process:

* **Topic name**: `Store Location`
* **Prompt**:

  ```
  When a user asks where the store is located, respond that we are at 123 Main Street, Tel Aviv.
  ```

### Services Offered

* **Topic name**: `Services`
* **Prompt**:

  ```
  When the user asks about services, respond that we offer computer repair, hardware sales, and software installation.
  ```

### Return Policy

* **Topic name**: `Return Policy`
* **Prompt**:

  ```
  When asked about return or refund policies, respond that returns are accepted within 14 days with receipt.
  ```

## Step 4: Test Each Topic

Try the following prompts in the test pane:

* `Where are you located?`
* `Do you fix computers?`
* `What’s your return policy?`
* `What are your hours?`

## Step 5: Configure Greeting and Fallback Topics

### Greeting

1. Go to **Topics > Greeting**
2. Edit the message to:

   ```
   Hi! I'm Contoso's assistant. I can help with our store hours, services, location, and return policy. What would you like to know?
   ```

### Fallback

1. Open the **Fallback** topic
2. Ensure it invites the user to try rephrasing the question.

## Step 6: (Optional) Add Generative Answer

1. Open **Topics > Conversational boosting**
2. Enable generative AI
3. (Optional) Add a file in the **Knowledge** tab for more accurate answers

## Step 7: Publish the Agent

1. Go to **Settings > Security > Authentication**
2. Select **No authentication** and click **Save**
3. Go to the **Channels** tab and click **Publish**

## Step 8: Use Demo Website

1. Click the **Demo website** channel
2. Set:

   * **Welcome message**: Ask me anything about Contoso’s hours, services, location, or return policy!
   * **Conversation starters**:

     ```
     "What are your hours?"
     "Where is your store?"
     "What services do you offer?"
     ```
3. Click **Save**, then copy the link and test it in a browser

## Summary

You created a customer service agent that:

* Answers specific customer questions
* Uses defined topics for clear responses
* Can be tested and shared through a public link

You can extend it further with:

* Multilingual support
* Entity recognition
* Power Automate integration
