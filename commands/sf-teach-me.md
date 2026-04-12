---
description: Get a structured Salesforce lesson
argument-hint: [SF topic]
allowed-tools: Read, Write, Edit, Bash
---

**<span data-proof="authored" data-by="ai:claude">IMPORTANT: Before responding, you MUST read this file from the plugin:</span>**

1. <span data-proof="authored" data-by="ai:claude">`${CLAUDE_PLUGIN_ROOT}/skills/sf-teacher/SKILL.md`</span> <span data-proof="authored" data-by="ai:claude">— the core SF teaching skill with pedagogy and guidelines</span>

**<span data-proof="authored" data-by="ai:claude">Do not deliver a lesson without reading this file first.</span>**

<span data-proof="authored" data-by="ai:claude">Next, check the learner's project for a profile:</span>

* <span data-proof="authored" data-by="ai:claude">Read</span> <span data-proof="authored" data-by="ai:claude">`docs/learning/sf-learner-profile.json`</span> <span data-proof="authored" data-by="ai:claude">if it exists</span>

* <span data-proof="authored" data-by="ai:claude">If no profile exists, teach at beginner level and add a note at the end suggesting</span> <span data-proof="authored" data-by="ai:claude">`/sf-setup`</span>

<span data-proof="authored" data-by="ai:claude">The learner wants to learn about: $ARGUMENTS</span>

<span data-proof="authored" data-by="ai:claude">If no topic was provided (empty $ARGUMENTS):</span>

* <span data-proof="authored" data-by="ai:claude">If a learner profile exists, suggest Salesforce topics related to their stated goal. Examples:</span>

  * <span data-proof="authored" data-by="ai:claude">Business user → "Want to learn about custom objects, page layouts, or reports?"</span>

  * <span data-proof="authored" data-by="ai:claude">Aspiring admin → "Want to start with the Salesforce data model, validation rules, or Flows?"</span>

  * <span data-proof="authored" data-by="ai:claude">Developer → "Want to start with Apex basics, SOQL, or triggers?"</span>

* <span data-proof="authored" data-by="ai:claude">If no profile exists, ask: "What Salesforce topic would you like to learn? For example: 'custom objects', 'Apex basics', 'Flows', 'governor limits', 'SOQL', 'Lightning Web Components', 'sharing model'."</span>

## <span data-proof="authored" data-by="ai:claude">Lesson Structure</span>

<span data-proof="authored" data-by="ai:claude">Deliver the lesson in this format, adapting depth and complexity to the learner's experience level:</span>

### <span data-proof="authored" data-by="ai:claude">1. What & Why</span>

<span data-proof="authored" data-by="ai:claude">What is this Salesforce concept? Why does it matter? Why should the learner care? Start with a relatable analogy.</span>

### <span data-proof="authored" data-by="ai:claude">2. Where It Fits</span>

<span data-proof="authored" data-by="ai:claude">How does this relate to the broader Salesforce platform? A brief orientation — where would you find this in Setup? What other features does it connect to? This helps the learner build a mental map of the platform.</span>

### <span data-proof="authored" data-by="ai:claude">3. Core Concepts</span>

<span data-proof="authored" data-by="ai:claude">3-5 key ideas, each explained with an analogy first, then the technical detail. Short paragraphs — 2-3 sentences max per concept.</span>

### <span data-proof="authored" data-by="ai:claude">4. Hands-On</span>

<span data-proof="authored" data-by="ai:claude">Check the learner's profile for org access:</span>

* **<span data-proof="authored" data-by="ai:claude">If they have an org:</span>** <span data-proof="authored" data-by="ai:claude">Give them a specific task to do in their org. For admin topics, guide through clicks in Setup. For dev topics, provide actual deployable code. Be specific: "Go to Setup > Object Manager > Create a new custom object called..."</span>

* **<span data-proof="authored" data-by="ai:claude">If no org (or no profile):</span>** <span data-proof="authored" data-by="ai:claude">Provide a conceptual exercise instead. "Imagine you're designing a data model for a library. What objects would you create? What fields? What relationships?"</span>

### <span data-proof="authored" data-by="ai:claude">5. Best Practices</span>

<span data-proof="authored" data-by="ai:claude">Real-world guidance for this topic. What are the common mistakes? What do experienced Salesforce professionals do differently? If sf-compound-engineering skills are available (apex-patterns, governor-limits, security-guide, etc.), leverage them naturally for deeper best practices. If not, provide guidance from your own knowledge.</span>

### <span data-proof="authored" data-by="ai:claude">6. Going Deeper</span>

<span data-proof="authored" data-by="ai:claude">Suggest 2-3 related Salesforce topics they could explore next. Frame these as curiosity hooks: "Now that you understand custom objects, you might be curious about validation rules — they let you add guardrails to your data..."</span>