---
description: Test your Salesforce knowledge with a question
argument-hint: [SF topic or leave blank]
allowed-tools: Read, Write, Edit
---

**<span data-proof="authored" data-by="ai:claude">IMPORTANT: Before responding, you MUST read this file from the plugin:</span>**

1. <span data-proof="authored" data-by="ai:claude">`${CLAUDE_PLUGIN_ROOT}/skills/sf-teacher/SKILL.md`</span> <span data-proof="authored" data-by="ai:claude">— the core SF teaching skill with pedagogy and guidelines</span>

**<span data-proof="authored" data-by="ai:claude">Do not quiz without reading this file first.</span>**

<span data-proof="authored" data-by="ai:claude">Next, check the learner's project for a profile:</span>

* <span data-proof="authored" data-by="ai:claude">Read</span> <span data-proof="authored" data-by="ai:claude">`docs/learning/sf-learner-profile.json`</span> <span data-proof="authored" data-by="ai:claude">if it exists</span>

* <span data-proof="authored" data-by="ai:claude">If no profile exists, default to beginner-level questions</span>

<span data-proof="authored" data-by="ai:claude">The learner wants to be quizzed on: $ARGUMENTS</span>

<span data-proof="authored" data-by="ai:claude">If no topic was provided (empty $ARGUMENTS):</span>

* <span data-proof="authored" data-by="ai:claude">If a learner profile exists, quiz on a topic related to their stated goal</span>

* <span data-proof="authored" data-by="ai:claude">If no profile exists, ask: "What Salesforce topic should I quiz you on? For example: 'custom objects', 'Apex', 'governor limits', 'Flows', 'SOQL', 'sharing model', 'data modeling'."</span>

## <span data-proof="authored" data-by="ai:claude">Quiz Flow (Single Question Per Invocation)</span>

<span data-proof="authored" data-by="ai:claude">Present</span> **<span data-proof="authored" data-by="ai:claude">one question</span>** <span data-proof="authored" data-by="ai:claude">per</span> <span data-proof="authored" data-by="ai:claude">`/sf-quiz-me`</span> <span data-proof="authored" data-by="ai:claude">invocation. Do NOT ask multiple questions at once.</span>

### <span data-proof="authored" data-by="ai:claude">Step 1: Ask the Question</span>

<span data-proof="authored" data-by="ai:claude">Choose a question type appropriate to the topic and the learner's level:</span>

**<span data-proof="authored" data-by="ai:claude">For business users / beginners:</span>**

* **<span data-proof="authored" data-by="ai:claude">Multiple choice</span>** <span data-proof="authored" data-by="ai:claude">— "Which of these is NOT a standard Salesforce object? A) Account B) Contact C) Customer D) Opportunity"</span>

* **<span data-proof="authored" data-by="ai:claude">Scenario-based</span>** <span data-proof="authored" data-by="ai:claude">— "A sales manager wants to see all deals closing this quarter. What Salesforce feature would you recommend?"</span>

* **<span data-proof="authored" data-by="ai:claude">True/False</span>** <span data-proof="authored" data-by="ai:claude">— "True or False: A lookup relationship allows cascade delete."</span>

**<span data-proof="authored" data-by="ai:claude">For admins:</span>**

* **<span data-proof="authored" data-by="ai:claude">Configuration scenarios</span>** <span data-proof="authored" data-by="ai:claude">— "You need to prevent users from saving a Contact without an email. What's the best approach?"</span>

* **<span data-proof="authored" data-by="ai:claude">Best practice</span>** <span data-proof="authored" data-by="ai:claude">— "Which automation tool would you use for: sending an email when an Opportunity stage changes?"</span>

* **<span data-proof="authored" data-by="ai:claude">Spot the issue</span>** <span data-proof="authored" data-by="ai:claude">— Show a Flow or validation rule with a problem</span>

**<span data-proof="authored" data-by="ai:claude">For developers:</span>**

* **<span data-proof="authored" data-by="ai:claude">Spot the governor limit violation</span>** <span data-proof="authored" data-by="ai:claude">— Show Apex code with a SOQL-in-a-loop or DML-in-a-loop</span>

* **<span data-proof="authored" data-by="ai:claude">Bulkification check</span>** <span data-proof="authored" data-by="ai:claude">— "What's wrong with this trigger?"</span>

* **<span data-proof="authored" data-by="ai:claude">Architecture decisions</span>** <span data-proof="authored" data-by="ai:claude">— "You need real-time integration with an external system. Platform Events or REST callout? Why?"</span>

* **<span data-proof="authored" data-by="ai:claude">SOQL challenges</span>** <span data-proof="authored" data-by="ai:claude">— "Write a query that returns all Accounts with at least one closed-won Opportunity"</span>

### <span data-proof="authored" data-by="ai:claude">Step 2: Wait for Their Answer</span>

<span data-proof="authored" data-by="ai:claude">After presenting the question, STOP. Wait for the learner to reply. Do not reveal the answer or give hints unless they ask.</span>

### <span data-proof="authored" data-by="ai:claude">Step 3: Give Feedback</span>

<span data-proof="authored" data-by="ai:claude">After they answer:</span>

* **<span data-proof="authored" data-by="ai:claude">If correct:</span>** <span data-proof="authored" data-by="ai:claude">Celebrate genuinely. Explain</span> *<span data-proof="authored" data-by="ai:claude">why</span>* <span data-proof="authored" data-by="ai:claude">it's correct — reinforce the Salesforce concept. Connect to real-world scenarios.</span>

* **<span data-proof="authored" data-by="ai:claude">If incorrect:</span>** <span data-proof="authored" data-by="ai:claude">Be encouraging. Explain the correct answer with an analogy. For developer questions, show the corrected code. For admin questions, explain the Setup path.</span>

* **<span data-proof="authored" data-by="ai:claude">If partially correct:</span>** <span data-proof="authored" data-by="ai:claude">Acknowledge what they got right, then fill in the gap.</span>

### <span data-proof="authored" data-by="ai:claude">Step 4: Encourage Another Round</span>

<span data-proof="authored" data-by="ai:claude">End with: "Want another question? Run</span> <span data-proof="authored" data-by="ai:claude">`/sf-quiz-me`</span> <span data-proof="authored" data-by="ai:claude">again! You can also try</span> <span data-proof="authored" data-by="ai:claude">`/sf-quiz-me [different topic]`</span> <span data-proof="authored" data-by="ai:claude">to test yourself on a different area."</span>