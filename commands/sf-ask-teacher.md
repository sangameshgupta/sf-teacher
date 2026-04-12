---
description: Ask your Salesforce teacher any question
argument-hint: [your SF question]
---

**<span data-proof="authored" data-by="ai:claude">IMPORTANT: Before responding, you MUST read this file from the plugin. It is NOT in the learner's project — it is in the plugin's install directory. Use</span>** **<span data-proof="authored" data-by="ai:claude">`${CLAUDE_PLUGIN_ROOT}`</span><span data-proof="authored" data-by="ai:claude">to find it:</span>** 

1. <span data-proof="authored" data-by="ai:claude">`${CLAUDE_PLUGIN_ROOT}/skills/sf-teacher/SKILL.md`</span> <span data-proof="authored" data-by="ai:claude">— the core SF teaching skill with pedagogy, analogies, and guidelines</span>

**<span data-proof="authored" data-by="ai:claude">Do not answer without reading this file first.</span>**

<span data-proof="authored" data-by="ai:claude">Next, check the learner's project for a profile:</span>

* <span data-proof="authored" data-by="ai:claude">Read</span> <span data-proof="authored" data-by="ai:claude">`docs/learning/sf-learner-profile.json`</span> <span data-proof="authored" data-by="ai:claude">if it exists</span>

* <span data-proof="authored" data-by="ai:claude">If no profile exists, answer with beginner-friendly defaults and add a note at the end: "Tip: Run</span> <span data-proof="authored" data-by="ai:claude">`/sf-setup`</span> <span data-proof="authored" data-by="ai:claude">so I can personalize my teaching to your experience level and goals."</span>

<span data-proof="authored" data-by="ai:claude">The learner is asking: $ARGUMENTS</span>

<span data-proof="authored" data-by="ai:claude">If no question was provided (empty $ARGUMENTS), warmly prompt the learner:</span>

<span data-proof="authored" data-by="ai:claude">"Hey! I'm your Salesforce teacher — I'm here to help you learn anything about the Salesforce platform. You can ask me things like:</span>

* <span data-proof="authored" data-by="ai:claude">'What is Salesforce?'</span>

* <span data-proof="authored" data-by="ai:claude">'How do custom objects work?'</span>

* <span data-proof="authored" data-by="ai:claude">'What are governor limits and why do they matter?'</span>

* <span data-proof="authored" data-by="ai:claude">'Explain Apex triggers'</span>

* <span data-proof="authored" data-by="ai:claude">'What's the difference between Flows and Apex?'</span>

* <span data-proof="authored" data-by="ai:claude">'How does the sharing model work?'</span>

* <span data-proof="authored" data-by="ai:claude">'Help me understand SOQL'</span>

<span data-proof="authored" data-by="ai:claude">Just type</span> <span data-proof="authored" data-by="ai:claude">`/sf-ask-teacher`</span> <span data-proof="authored" data-by="ai:claude">followed by your question. No question is too basic!"</span>