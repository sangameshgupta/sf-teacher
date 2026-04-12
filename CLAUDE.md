# <span data-proof="authored" data-by="ai:claude">CLAUDE.md</span>

<span data-proof="authored" data-by="ai:claude">This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.</span>

## <span data-proof="authored" data-by="ai:claude">Project Overview</span>

<span data-proof="authored" data-by="ai:claude">This is the</span> **<span data-proof="authored" data-by="ai:claude">sf-teacher</span>** <span data-proof="authored" data-by="ai:claude">plugin — a Claude Code plugin that turns Claude into an adaptive Salesforce teacher. It teaches all areas of Salesforce (admin, development, architecture, integration) at any experience level.</span>

## <span data-proof="authored" data-by="ai:claude">Plugin Architecture</span>

```
sf-teacher/
├── .claude-plugin/
│   ├── plugin.json          # name, version, description, author, keywords
│   └── marketplace.json     # source: "./" (flat layout)
├── commands/*.md            # Slash commands (YAML frontmatter + markdown body)
├── skills/sf-teacher/
│   ├── SKILL.md             # Core skill with trigger descriptions and pedagogy
│   └── examples/            # Model interaction examples
├── CLAUDE.md                # This file
└── README.md                # Installation & usage
```

## <span data-proof="authored" data-by="ai:claude">Key Conventions</span>

* **<span data-proof="authored" data-by="ai:claude">Command frontmatter:</span>**<span data-proof="authored" data-by="ai:claude"></span> <span data-proof="authored" data-by="ai:claude">`description`,</span> <span data-proof="authored" data-by="ai:claude">`allowed-tools`,</span> <span data-proof="authored" data-by="ai:claude">`argument-hint`. Use</span> <span data-proof="authored" data-by="ai:claude">`$ARGUMENTS`</span> <span data-proof="authored" data-by="ai:claude">for user input.</span>

* **<span data-proof="authored" data-by="ai:claude">Skill references:</span>** <span data-proof="authored" data-by="ai:claude">Use</span> <span data-proof="authored" data-by="ai:claude">`${CLAUDE_PLUGIN_ROOT}/path/to/file`</span> <span data-proof="authored" data-by="ai:claude">in commands.</span>

* **<span data-proof="authored" data-by="ai:claude">Learner profile:</span>** <span data-proof="authored" data-by="ai:claude">Stored in</span> <span data-proof="authored" data-by="ai:claude">`docs/learning/sf-learner-profile.json`</span> <span data-proof="authored" data-by="ai:claude">in the user's project (NOT in CLAUDE.md).</span>

* **<span data-proof="authored" data-by="ai:claude">No-profile degradation:</span>** <span data-proof="authored" data-by="ai:claude">All commands work without a profile — answer with beginner defaults, suggest</span> <span data-proof="authored" data-by="ai:claude">`/sf-setup`.</span>

## <span data-proof="authored" data-by="ai:claude">Dependency on sf-compound-engineering</span>

<span data-proof="authored" data-by="ai:claude">This plugin has a</span> **<span data-proof="authored" data-by="ai:claude">soft runtime dependency</span>** <span data-proof="authored" data-by="ai:claude">on the sf-compound-engineering plugin. It does NOT:</span>

* <span data-proof="authored" data-by="ai:claude">Check if sf-compound is installed</span>

* <span data-proof="authored" data-by="ai:claude">Warn if it's missing</span>

* <span data-proof="authored" data-by="ai:claude">Branch logic based on its presence</span>

<span data-proof="authored" data-by="ai:claude">It simply says in SKILL.md: "leverage any available SF skills naturally." If sf-compound is installed, Claude uses its skills (apex-patterns, lwc-patterns, governor-limits, etc.) automatically. If not, Claude answers from its own knowledge.</span>

## <span data-proof="authored" data-by="ai:claude">Version Management</span>

<span data-proof="authored" data-by="ai:claude">Bump</span> <span data-proof="authored" data-by="ai:claude">`version`</span> <span data-proof="authored" data-by="ai:claude">in both</span> <span data-proof="authored" data-by="ai:claude">`plugin.json`</span> <span data-proof="authored" data-by="ai:claude">and</span> <span data-proof="authored" data-by="ai:claude">`marketplace.json`</span> <span data-proof="authored" data-by="ai:claude">simultaneously. Only bump for meaningful changes.</span>