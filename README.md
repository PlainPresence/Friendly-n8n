# 🚀 Friendly n8n

A beginner-friendly, hands-on repository for learning **n8n workflow automation** from the ground up.

The goal is simple:

> **Learn by building, not by watching.**

Every level introduces a concept, explains it, and then gives you workflows and challenges to build yourself.

---

## 💙 Support the Project

If **Friendly n8n** helps you learn automation, you can support the project:

**[💙 Support Me](https://www.thankyouverymuch.co/plainpresence)**

Your support helps keep the tutorials, workflows, examples, and challenges coming. 🙌

---

## 🧭 Learning Roadmap

```text
n8n Learning
│
├── 🟢 00 — Basics
│   ├── What is n8n?
│   ├── Workflows
│   ├── Nodes
│   ├── Triggers
│   ├── JSON
│   ├── Data flow
│   └── Expressions
│
├── 🔵 01 — Beginner Automations (WIP)
│   ├── Webhooks
│   ├── Discord
│   ├── Google Sheets
│   ├── Email
│   └── Scheduled workflows
│
├── 🟡 02 — APIs & Data (WIP)
│   ├── HTTP requests
│   ├── REST APIs
│   ├── JSON manipulation
│   ├── Authentication
│   └── Error handling
│
├── 🟠 03 — Business Automations (WIP)
│   ├── Lead capture
│   ├── Lead notifications
│   ├── CRM automation
│   ├── Appointment reminders
│   └── Customer workflows
│
├── 🔴 04 — AI Automations (WIP)
│   ├── AI nodes
│   ├── AI agents
│   ├── Structured output
│   ├── Document processing
│   └── AI-powered business workflows
│
└── ⚫ 05 — Production (WIP)
    ├── Credentials
    ├── Security
    ├── Logging
    ├── Retries
    ├── Error workflows
    ├── Environment variables
    └── Deployment
```

---

# 🟢 Start Here

If you've never used n8n before, start with:

**[00 — Basics](./00-basics/README.md)**

You'll learn the fundamentals before touching complicated automations.

---

# 📚 Levels

| Level | Topic                | Status         |
| ----- | -------------------- | -------------- |
| 🟢 00 | n8n Basics           | 🚧 In Progress |
| 🔵 01 | Beginner Automations | 🔒 Coming Soon |
| 🟡 02 | APIs & Data          | 🔒 Coming Soon |
| 🟠 03 | Business Automations | 🔒 Coming Soon |
| 🔴 04 | AI Automations       | 🔒 Coming Soon |
| ⚫ 05  | Production           | 🔒 Coming Soon |

---

# 🧠 How This Repository Works

Each level follows the same idea:

```text
Learn the concept
       ↓
Build a workflow
       ↓
Inspect the data
       ↓
Break something
       ↓
Fix it
       ↓
Complete a challenge
       ↓
Move to the next level
```

Don't just import workflows and move on.

**Build them yourself first.**

The workflow JSON files are there so you can compare your work, experiment, and recover if something goes wrong.

---

# 📁 Repository Structure

```text
n8n-learning/
│
├── README.md
│
├── 00-basics/
│   ├── README.md
│   └── workflows/
│       └── first-workflow.json
│
├── 01-beginner/
│   ├── README.md
│   └── workflows/
│
├── 02-apis-data/
│   ├── README.md
│   └── workflows/
│
├── 03-business/
│   ├── README.md
│   └── workflows/
│
├── 04-ai/
│   ├── README.md
│   └── workflows/
│
├── 05-production/
│   ├── README.md
│   └── workflows/
│
└── docs/
    ├── common-errors.md
    ├── security.md
    └── environment-variables.md
```

---

# 🧪 What You'll Build

By the end of the repository, you'll have built automations such as:

```text
Webhook
   ↓
Process Data
   ↓
Discord Notification
```

```text
Form
   ↓
Validate Data
   ↓
Google Sheets
   ↓
Email
```

```text
Schedule
   ↓
HTTP Request
   ↓
Process API Data
   ↓
Send Report
```

```text
New Lead
   ↓
Qualify Lead
   ↓
Save to CRM
   ↓
Notify Sales
   ↓
Send Follow-up
```

And eventually:

```text
Customer Request
       ↓
      AI
       ↓
Understand Request
       ↓
Make Decision
       ↓
Call Tools / APIs
       ↓
Return Result
```

---

# 🛡️ Security Rules

Before uploading workflows to GitHub, **remove secrets**.

Never commit:

```text
API keys
Passwords
Discord webhook URLs
Access tokens
OAuth secrets
Database passwords
Private credentials
```

Use:

* n8n Credentials
* Environment variables
* Placeholder values

For example:

```text
YOUR_API_KEY
YOUR_DISCORD_WEBHOOK
YOUR_GOOGLE_SHEET_ID
```

A workflow that works is useless if it accidentally leaks someone's credentials. 🔐

---

# 🤝 Contributing

Found a mistake?

Have a better workflow?

Want to add a new example?

Feel free to contribute.

Good contributions should:

* Explain what the workflow teaches
* Include setup instructions
* Avoid real credentials
* Be beginner-friendly
* Include expected input/output where useful

---

# ⭐ Philosophy

This repository isn't meant to teach you how to blindly copy workflows.

It's meant to teach you how to **understand and build them yourself**.

The ultimate goal is to reach a point where you can look at a problem and think:

```text
What triggers this?
       ↓
What data do I receive?
       ↓
What needs to happen to that data?
       ↓
What service should receive the result?
```

Then turn that idea into an actual n8n workflow.

---

# 🚀 Ready?

Start here:

## 🟢 [00 — n8n Basics](./00-basics/README.md)

Learn the fundamentals, build your first workflow, and complete the beginner challenges.

**Happy automating! 🤖**
