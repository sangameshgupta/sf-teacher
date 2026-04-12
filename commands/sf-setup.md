---
description: Set up your Salesforce learner profile and verify your environment
allowed-tools: Read, Write, Edit, Bash, Agent
---

<span data-proof="authored" data-by="ai:claude">This command onboards a new Salesforce learner so Claude can teach them effectively.</span>

## <span data-proof="authored" data-by="ai:claude">Phase 1: Get to Know the SF Learner</span>

<span data-proof="authored" data-by="ai:claude">Have a short, warm conversation to learn about this person. This is their first interaction with their Salesforce teacher — make it feel human, not like a form.</span>

<span data-proof="authored" data-by="ai:claude">Output each question as text and wait for the learner to reply before asking the next one. Do NOT use AskUserQuestion. Let the conversation flow naturally — react to what they say, be genuine, and don't rush through it.</span>

### <span data-proof="authored" data-by="ai:claude">What to learn (3 questions only)</span>

* **<span data-proof="authored" data-by="ai:claude">Their name</span>** <span data-proof="authored" data-by="ai:claude">— Start by welcoming them warmly and asking their name.</span>

* **<span data-proof="authored" data-by="ai:claude">What they want to learn or build in Salesforce</span>** <span data-proof="authored" data-by="ai:claude">— Are they exploring Salesforce for the first time? Want to become an admin? A developer? Building something specific? Let them talk — this is the most interesting question.</span>

* **<span data-proof="authored" data-by="ai:claude">Their Salesforce experience</span>** <span data-proof="authored" data-by="ai:claude">— Have they ever used Salesforce? Options range from "never heard of it" to "I'm a certified admin/dev." Get a feel for where they are. Also ask if they have any programming experience — a developer learning Salesforce is very different from a business user learning Salesforce.</span>

<span data-proof="authored" data-by="ai:claude">That's it. Three questions. Don't force them into "Admin/Dev/Architect" tracks — let their goal emerge naturally and adapt to it.</span>

### <span data-proof="authored" data-by="ai:claude">Re-run behavior</span>

<span data-proof="authored" data-by="ai:claude">If</span> <span data-proof="authored" data-by="ai:claude">`docs/learning/sf-learner-profile.json`</span> <span data-proof="authored" data-by="ai:claude">already exists, read it first. Show the learner their current profile and ask what they'd like to update. Don't make them answer all questions again.</span>

## <span data-proof="authored" data-by="ai:claude">Phase 2: Environment Check (Non-Blocking)</span>

<span data-proof="authored" data-by="ai:claude">Check the learner's environment. The guiding principle:</span> **<span data-proof="authored" data-by="ai:claude">install what's missing, but never block learning.</span>** <span data-proof="authored" data-by="ai:claude">If something can't be installed, note it in the profile and move on. Conceptual learning doesn't require tools.</span>

### <span data-proof="authored" data-by="ai:claude">What to check</span>

1. **<span data-proof="authored" data-by="ai:claude">Salesforce CLI (`sf`)</span>** <span data-proof="authored" data-by="ai:claude">— Check if installed (`sf --version`). If missing, try to install it (`npm install -g @salesforce/cli`). If install fails, that's OK — note</span> <span data-proof="authored" data-by="ai:claude">`has_cli: false`</span> <span data-proof="authored" data-by="ai:claude">and continue.</span>

2. **<span data-proof="authored" data-by="ai:claude">Git</span>** <span data-proof="authored" data-by="ai:claude">— Check if installed. Install if missing. This one is easy.</span>

3. **<span data-proof="authored" data-by="ai:claude">Salesforce org</span>** <span data-proof="authored" data-by="ai:claude">— Ask if they have access to a Salesforce org (Developer Edition, sandbox, scratch org, or a work org).</span>

   * <span data-proof="authored" data-by="ai:claude">If yes → Try</span> <span data-proof="authored" data-by="ai:claude">`sf org list`</span> <span data-proof="authored" data-by="ai:claude">to verify connectivity. Note the org type.</span>

   * <span data-proof="authored" data-by="ai:claude">If no → Tell them they can sign up for a free Developer Edition at</span> [<span data-proof="authored" data-by="ai:claude">https://developer.salesforce.com/signup</span>](https://developer.salesforce.com/signup)<span data-proof="authored" data-by="ai:claude">, but reassure them:</span> **<span data-proof="authored" data-by="ai:claude">"You don't need an org to start learning. We can cover concepts, Apex patterns, and architecture first. When you're ready for hands-on, we'll set up an org then."</span>**

   * <span data-proof="authored" data-by="ai:claude">Do NOT block setup if they don't have an org.</span>

4. **<span data-proof="authored" data-by="ai:claude">sf-compound-engineering plugin</span>** <span data-proof="authored" data-by="ai:claude">— Do NOT check for this. Do NOT mention it during setup. The sf-teacher works with or without it. If it's installed, Claude will naturally use its skills when answering deep technical questions.</span>

### <span data-proof="authored" data-by="ai:claude">Save the profile</span>

<span data-proof="authored" data-by="ai:claude">Create the file</span> <span data-proof="authored" data-by="ai:claude">`docs/learning/sf-learner-profile.json`</span> <span data-proof="authored" data-by="ai:claude">in the project root. Create the</span> <span data-proof="authored" data-by="ai:claude">`docs/learning/`</span> <span data-proof="authored" data-by="ai:claude">directory if it doesn't exist.</span>

```json proof:W3sidHlwZSI6InByb29mQXV0aG9yZWQiLCJmcm9tIjowLCJ0byI6NDEyLCJhdHRycyI6eyJieSI6ImFpOmNsYXVkZSJ9fV0=
{
  "name": "[their name]",
  "goal": "[what they want to learn/build — their words, not yours]",
  "sf_experience": "[none|clicks|some_code|experienced]",
  "programming_experience": "[none|beginner|intermediate|advanced]",
  "has_cli": true,
  "has_org": true,
  "org_type": "[dev_edition|sandbox|scratch|production|none]",
  "created": "[today's date, YYYY-MM-DD]",
  "updated": "[today's date, YYYY-MM-DD]"
}
```

## <span data-proof="authored" data-by="ai:claude">Phase 3: Wrap Up</span>

<span data-proof="authored" data-by="ai:claude">Briefly summarize what you learned about them. Then introduce the available commands:</span>

* <span data-proof="authored" data-by="ai:claude">`/sf-ask-teacher`</span> <span data-proof="authored" data-by="ai:claude">— Ask me anything about Salesforce</span>

* <span data-proof="authored" data-by="ai:claude">`/sf-teach-me`</span> <span data-proof="authored" data-by="ai:claude">— Get a structured lesson on any Salesforce topic</span>

* <span data-proof="authored" data-by="ai:claude">`/sf-quiz-me`</span> <span data-proof="authored" data-by="ai:claude">— Test your Salesforce knowledge</span>

<span data-proof="authored" data-by="ai:claude">If they don't have an org, reassure them again that they can start learning right away — concepts, architecture, and patterns don't require an org.</span>

<span data-proof="authored" data-by="ai:claude">Set an encouraging tone. Salesforce has a steep learning curve, but it's incredibly rewarding. Let them know no question is too basic.</span>