# 🟢 00 — n8n Basics

Welcome to the **n8n Learning Repository**!

This section is designed for absolute beginners. You don't need any previous n8n experience.

By the end of this guide, you'll understand:

- What n8n is
- What workflows and nodes are
- How triggers work
- How data moves through a workflow
- The basics of JSON
- How expressions work
- How to create your first simple n8n workflow

---

## 📚 1. What is n8n?

**n8n** is a workflow automation platform.

It lets you connect different services and make them work together automatically.

For example:

```text
Someone fills out a form
        ↓
n8n receives the data
        ↓
Save the information to Google Sheets
        ↓
Send a Discord notification
        ↓
Send a confirmation email
```

Instead of doing these tasks manually, n8n can perform them automatically.

### A simple mental model

Think of n8n as:

```text
Something happens
       ↓
n8n receives data
       ↓
n8n processes the data
       ↓
n8n does something with it
```

---

# 🔗 2. What is a Workflow?

A **workflow** is a collection of connected nodes that perform a task.

For example:

```text
[Manual Trigger]
       ↓
[Edit Fields]
       ↓
[Discord]
```

Each node performs one part of the job.

Think of a workflow like a production line:

```text
Raw material
     ↓
Machine 1
     ↓
Machine 2
     ↓
Machine 3
     ↓
Finished product
```

In n8n:

```text
Input
 ↓
Node
 ↓
Node
 ↓
Output
```

A workflow can be very small or extremely complex.

---

# 🧩 3. What is a Node?

A **node** is a building block of an n8n workflow.

Different nodes perform different jobs.

Examples:

| Node | Purpose |
| --- | --- |
| Manual Trigger | Starts a workflow manually |
| Schedule Trigger | Starts a workflow at a specific time |
| Webhook | Receives data from another application |
| Edit Fields | Creates or modifies data |
| HTTP Request | Communicates with APIs |
| IF | Makes a decision |
| Google Sheets | Reads or writes spreadsheet data |
| Discord | Sends messages to Discord |

A workflow is simply multiple nodes connected together.

### Node categories

The n8n node picker groups nodes into categories such as:

- **AI** — AI agents and AI-related tasks
- **Action in an app** — Work with services such as Google Sheets, Telegram, or Notion
- **Data transformation** — Manipulate, filter, or transform data
- **Flow** — Branch, merge, loop, and control workflow execution
- **Core** — Run code, make HTTP requests, create webhooks, and other core operations
- **Human review** — Request approval or review through supported services

You don't need to memorize these categories. They are simply ways to find the node you need.

---

# 🚦 4. Triggers

A **trigger** is what starts a workflow.

For example:

### Manual Trigger

You start the workflow yourself.

```text
You click Execute
       ↓
Workflow starts
```

### Schedule Trigger

The workflow starts automatically at a scheduled time.

```text
Every day at 9:00 AM
       ↓
Workflow starts
```

### Webhook Trigger

Another application sends a request to n8n.

```text
Website
   ↓
Webhook
   ↓
Workflow starts
```

The trigger is basically saying:

> "Something happened. Start the workflow."

---

# ⚙️ 5. Actions and Processing

After a workflow starts, other nodes perform work.

For example:

```text
Webhook
   ↓
Edit Fields
   ↓
Google Sheets
   ↓
Discord
```

The workflow could:

1. Receive information
2. Modify the information
3. Save it
4. Notify someone

Triggers start workflows.

Other nodes process the data or perform actions.

---

# 📦 6. Data in n8n

n8n commonly works with structured data, especially **JSON**.

Example:

```json
{
  "name": "Alice",
  "age": 20,
  "student": true
}
```

Here:

```text
name     → "Alice"
age      → 20
student  → true
```

These are called **key-value pairs**.

- `name` is a key and `"Alice"` is its value.
- `age` is a key and `20` is its value.
- `student` is a key and `true` is its value.

---

# 🗂️ 7. JSON Basics

You will encounter JSON constantly when working with n8n.

## String

```json
{
  "name": "Alice"
}
```

`"Alice"` is a string.

## Number

```json
{
  "age": 20
}
```

`20` is a number.

## Boolean

```json
{
  "student": true
}
```

`true` is a boolean.

A boolean can be either `true` or `false`.

## Array

```json
{
  "skills": [
    "Python",
    "JavaScript",
    "Linux"
  ]
}
```

An array contains multiple values.

## Nested Object

```json
{
  "user": {
    "name": "Alice",
    "age": 20
  }
}
```

Objects can contain other objects.

---

# 🔄 8. Data Flow

One of the most important concepts in n8n is **data flow**.

Imagine this workflow:

```text
[Manual Trigger]
       ↓
[Edit Fields]
       ↓
[Edit Fields]
```

The first node starts the workflow.

The next node creates data:

```json
{
  "name": "Alice"
}
```

The following node receives that data and can modify it.

For example:

```json
{
  "name": "Alice",
  "age": 20
}
```

So data travels through the workflow:

```text
Node 1
  ↓
Data
  ↓
Node 2
  ↓
Modified Data
  ↓
Node 3
```

### Important idea

When debugging an n8n workflow, inspect the output of each node.

Ask:

- What data entered this node?
- What data did it produce?
- What keys exist?
- What values exist?
- Can the next node use this data?

This habit will save you **hours of debugging** later.

---

# 🧮 9. Expressions

Expressions allow you to dynamically use data from previous nodes.

A basic expression looks like:

```text
{{ $json.name }}
```

Suppose the previous node outputs:

```json
{
  "name": "Alice"
}
```

Then:

```text
{{ $json.name }}
```

produces:

```text
Alice
```

You can also combine text and data:

```text
Hello {{ $json.name }}!
```

Result:

```text
Hello Alice!
```

Expressions become extremely important when building real automations.

### `$json`

`$json` refers to the JSON data available from the current input.

For example, if the incoming data is:

```json
{
  "name": "Alice",
  "age": 20
}
```

You can access the values with:

```text
{{ $json.name }}
```

and:

```text
{{ $json.age }}
```

---

# 🧪 10. Your First Workflow

Now let's build your first workflow.

We will create:

```text
[Manual Trigger]
       ↓
[Edit Fields]
```

The **Edit Fields** node is used to create or modify fields.

> **Note:** In newer versions of n8n, the old **Set** node is called **Edit Fields (Set)**. You may find it under **Data transformation** or by searching for `Edit Fields` / `Set`.

## Step 1 — Create a workflow

Create a new workflow and give it a name such as:

```text
L0 - First Workflow
```

## Step 2 — Add Manual Trigger

Add a **Manual Trigger** node.

This lets you start the workflow yourself by clicking **Execute Workflow**.

## Step 3 — Add Edit Fields

Add an **Edit Fields (Set)** node after the Manual Trigger.

Your workflow should look like:

```text
[Manual Trigger]
       ↓
[Edit Fields]
```

## Step 4 — Add fields

Configure the Edit Fields node with:

```text
name   = Alice
age    = 20
course = B.Sc Computer Science
```

## Step 5 — Execute the workflow

Click **Execute Workflow**.

Open the output of the Edit Fields node.

You should see something similar to:

```json
{
  "name": "Alice",
  "age": 20,
  "course": "B.Sc Computer Science"
}
```

🎉 Congratulations!

You just created your first n8n workflow.

---

# 🔍 11. Inspecting Node Output

When you execute a node, n8n shows you its output.

For example:

```json
{
  "name": "Alice",
  "age": 20
}
```

Don't just look at whether the node succeeded.

Learn to inspect the actual data.

Ask yourself:

- What data did this node receive?
- What data did it produce?
- What keys exist?
- What values exist?
- Can the next node use this data?

Understanding node input and output is one of the most important skills in n8n.

---

# 🛠️ 12. A Simple Real-World Example

Imagine you run a website.

Someone submits:

```text
Name: John
Email: john@example.com
```

Your workflow could be:

```text
[Webhook]
     ↓
[Edit Fields]
     ↓
[Google Sheets]
     ↓
[Discord]
```

The webhook might receive:

```json
{
  "name": "John",
  "email": "john@example.com"
}
```

n8n can then use:

```text
{{ $json.name }}
```

and:

```text
{{ $json.email }}
```

to send the information to other services.

That's the basic idea behind much more complicated automations.

---

# 🧠 13. The n8n Mental Model

Remember these four things:

## 1. Trigger

**When should the workflow start?**

```text
Webhook
Schedule
Manual Trigger
```

## 2. Input

**What data did we receive?**

```json
{
  "name": "John"
}
```

## 3. Processing

**What should we do with the data?**

```text
IF
Edit Fields
Code
Filter
Transform
```

## 4. Output

**What should happen next?**

```text
Send email
Save to database
Send Discord message
Call an API
```

Put together:

```text
TRIGGER
   ↓
INPUT
   ↓
PROCESS
   ↓
OUTPUT
```

This is the core mental model of n8n.

---

# 📝 14. Beginner Challenges

Don't just read the guide. Try these yourself.

## Challenge 1 — Create basic data

Create a workflow that outputs:

```json
{
  "name": "Your Name",
  "course": "B.Sc Computer Science"
}
```

---

## Challenge 2 — Add more data

Add your age:

```json
{
  "name": "Your Name",
  "course": "B.Sc Computer Science",
  "age": 20
}
```

---

## Challenge 3 — Use an expression

Create a message using:

```text
Hello, my name is {{ $json.name }}.
```

If the input contains:

```json
{
  "name": "Alice"
}
```

the result should be:

```text
Hello, my name is Alice.
```

---

## Challenge 4 — Pass data through multiple nodes

Create:

```text
[Manual Trigger]
       ↓
[Edit Fields]
       ↓
[Edit Fields]
```

Create data in the first Edit Fields node and use it in the second node.

---

## Challenge 5 — Send data to Discord

Build:

```text
[Manual Trigger]
       ↓
[Edit Fields]
       ↓
[Discord]
```

Send a Discord message containing the name from your JSON.

For example, if your data is:

```json
{
  "name": "Alice"
}
```

the Discord message could be:

```text
Hello Alice!
```

> **Security note:** Never commit Discord webhook URLs, API keys, passwords, or other credentials to this repository. Use n8n credentials or placeholders instead.

---

# ✅ Level 0 Checklist

Before moving to Level 1, you should understand:

- [ ] What n8n is
- [ ] What a workflow is
- [ ] What a node is
- [ ] What a trigger is
- [ ] What an action is
- [ ] How nodes connect
- [ ] How data flows between nodes
- [ ] Basic JSON
- [ ] Strings, numbers, booleans, and arrays
- [ ] How to inspect node output
- [ ] Basic expressions
- [ ] How to use `$json`
- [ ] How to execute a workflow
- [ ] How to build a basic automation

If you can do all of these, you're ready for **Level 1 — Beginner Automations**.

---

## 🚀 What's Next?

In Level 1, we'll start building useful automations using real services.

You'll learn things like:

```text
Webhook → Discord
Form → Google Sheets
Schedule → Email
API → Data Processing
```

That's where n8n starts getting fun. 🚀
