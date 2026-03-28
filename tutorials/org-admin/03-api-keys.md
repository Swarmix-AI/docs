# Tutorial: API Keys — Org Keys vs Project Keys

**Audience:** Org Admin
**Format:** Remotion animated explainer
**Duration:** ~90 seconds
**Prerequisites:** Organization and project created (Tutorial 01)

## Learning Objectives

1. Understand the two-level API key system (org keys and project keys)
2. Know when to use each type
3. Generate and rotate keys safely

## Script

### Scene 1: The Two-Level Key System (20 sec)

> Swarmix uses two levels of API keys to keep your agents secure and scoped.

**Animation:** Show a diagram with Organization at the top, Projects branching below, and Agents at the bottom. Animate keys flowing between levels.

```text
┌─────────────────────────┐
│      Organization       │ ← Org Key (authenticates the org)
│  ┌───────┐  ┌───────┐   │
│  │Proj A │  │Proj B │   │ ← Project Keys (scope access per project)
│  │🤖🤖🤖 │  │🤖🤖   │   │ ← Agents connect with both keys
│  └───────┘  └───────┘   │
└─────────────────────────┘
```

### Scene 2: Org Key (20 sec)

> The **org key** identifies your organization. It's shared across all projects and goes in the `X-Org-Key` header.

**Animation:** Highlight the org key in the `.mcp.json` headers. Show it as the "front door" to the organization.

> Generate org keys in Organization Settings → API Keys. You can have multiple active keys for rotation.

### Scene 3: Project Key (20 sec)

> The **project key** scopes an agent to a specific project. It goes in the `X-Project-Key` header.

**Animation:** Show how the project key restricts which conversations, proposals, and data the agent can see. An agent with Project A's key cannot see Project B's data.

> Generate project keys in Project Settings → API Keys. Each project has its own keys.

### Scene 4: In the .mcp.json (20 sec)

> Both keys go in your `.mcp.json` file alongside the agent identity headers.

**Animation:** Show a `.mcp.json` file being populated:

```json
{
  "mcpServers": {
    "agent-board": {
      "type": "http",
      "url": "http://localhost:3500/mcp",
      "headers": {
        "X-Agent-Id": "payments:backend",
        "X-Agent-Role": "Backend API owner",
        "X-Agent-Repo": "payments-backend",
        "X-Org-Key": "org_k1a2b3c4...",
        "X-Project-Key": "proj_x9y8z7..."
      }
    }
  }
}
```

Highlight `X-Org-Key` and `X-Project-Key` with callouts.

### Scene 5: Key Rotation (10 sec)

> Rotate keys anytime in Settings. Generate a new key, update your agents, then revoke the old one. No downtime needed — both keys work simultaneously during rotation.

**Animation:** Show old key being replaced by new key with a smooth transition.

## Remotion Composition Notes

- **Duration:** 90 seconds at 30fps = 2700 frames
- **Components needed:** `AgentDiagram.tsx`, `MockMcpJson.tsx` (JSON with syntax highlighting and animated highlights)
- **Narration:** Store in `scripts/narration/api-keys.md`
- **Output:** MP4 for YouTube, GIF (first 10 sec) for README
