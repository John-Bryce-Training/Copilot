# Create a Personal Task Reminder Agent in Copilot Studio

In this exercise, you’ll use Microsoft Copilot Studio to build a personal task assistant. This agent will let users save reminders for tasks and retrieve them later. You’ll learn how to use variables, branching logic, and structured dialog flows.

This exercise will take approximately 30–40 minutes to complete.

**Note**: You must have an active free trial of Microsoft Copilot Studio to complete this lab.

## Step 1: Create a New Agent

1. Go to [https://copilotstudio.microsoft.com](https://copilotstudio.microsoft.com)
2. Sign in with your Microsoft account.
3. From the home page, click **Create** > **New agent**.

> 💡 If prompted with the chat creation interface, select **Skip to configure** to enter settings manually.

4. Provide the following configuration:

   * **Agent name**: `Task Reminder Bot`
   * **Language**: English
   * **Description**: An agent that helps users save and retrieve task reminders.
   * **Tone**: Friendly and casual

5. Click **Create** to finish.

## Step 2: Add Topic - Create a New Reminder

1. Go to the **Topics** tab.
2. Click **+ Add a topic** > **Add from description with Copilot**
3. Enter:

   * **Topic name**: `Create Reminder`
   * **Prompt**:

     ```
     When the user says they want to save a reminder, ask them what the task is and when it should happen. Save the task name and time to variables.
     ```
4. Click **Create**, then open the topic to review the nodes.
5. Ensure the flow:

   * Asks: “What should I remind you about?” → Save to variable `taskName`
   * Asks: “When should I remind you?” → Save to variable `reminderTime`
   * Confirms the reminder: “Got it! I’ll remind you to \[taskName] at \[reminderTime].”
6. Click **Save**.

## Step 3: Add Topic - Show Saved Reminders

1. Again, go to **+ Add a topic** > **Add from description with Copilot**
2. Use:

   * **Topic name**: `Show Reminders`
   * **Prompt**:

     ```
     When the user asks to see their reminders, show the last reminder that was saved using variables.
     ```
3. Confirm that the topic pulls the values from `taskName` and `reminderTime`.

   * Add a fallback message if no values are stored: “You haven’t saved any reminders yet.”

## Step 4: Test Your Agent

Open the **Test your agent** pane and try the following examples:

* `Remind me to send an email tomorrow at 9am`
* `What reminders do I have?`

Check that the agent correctly prompts, stores, and retrieves the values.

## Step 5: Customize Greeting and Fallback

### Greeting

1. Open the **Greeting** system topic.
2. Change the welcome message to:

   ```
   Hi! I’m your task reminder bot. You can ask me to save a task or check what you’ve already saved.
   ```

### Fallback

1. Open the **Fallback** system topic.
2. Add a fallback node with:

   * “Sorry, I didn’t understand. Try saying ‘Remind me to…’ or ‘What are my reminders?’”

## Step 6: Publish Your Agent

1. Open **Settings > Security > Authentication**
2. Choose **No authentication**, then **Save**
3. Go to the **Channels** tab and click **Publish**

## Step 7: Test in Demo Website

1. Open the **Demo website** channel.
2. Set:

   * **Welcome message**: I'm here to help with your reminders!
   * **Conversation starters**:

     ```
     "Remind me to drink water at 3 PM"
     "What are my reminders?"
     ```
3. Click **Save** and open the link to test your agent.

## Summary

In this lab, you created a personal assistant that can:

* Save reminders using variables
* Retrieve the last saved task
* Respond with friendly, contextual messages

You can extend it by integrating with Power Automate for real calendar or notification triggers.
