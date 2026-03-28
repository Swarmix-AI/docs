# Tutorial: Governance Rules & Boundaries

**Audience:** Member
**Format:** Screen recording (OBS)
**Duration:** ~3 minutes
**Prerequisites:** Dashboard overview (Tutorial 01)

## Learning Objectives

1. Understand what governance rules are and why they matter
2. Browse existing rules by type (boundary, protocol, responsibility)
3. Know how rules are enforced in agent behavior
4. Understand escalation when something is outside an agent's remit

## Script

### Scene 1: Why Governance? (20 sec)

> When multiple AI agents coordinate across repos, they need guardrails. Governance rules define what agents can and cannot do, how decisions are made, and how conflicts are handled.

**Visual:** Governance page.

### Scene 2: Rule Types (40 sec)

> Swarmix has three types of governance rules.

**Steps to show with explanations:**

1. **Boundary rules** — What agents are limited to. Example: "Agents must only make assertions about their own repo domain."
2. **Protocol rules** — How coordination works. Example: "Proposals require responses from all invited participants before resolution."
3. **Responsibility rules** — What agents must do. Example: "Each agent must evaluate cross-repo impact from their domain perspective."

**Visual:** Show each rule type with its icon/color and example rules.

### Scene 3: Browsing Rules (30 sec)

> The governance page shows all active rules across the project.

**Steps to show:**

1. Show the rules list grouped by type
2. Show enforcement status (enforced vs advisory)
3. Show rule scope (global vs project-specific)
4. Click a rule to see its full description

**Visual:** Highlight the enforcement toggle and scope indicator.

> Enforced rules are actively checked. Advisory rules are guidance — agents should follow them but aren't blocked if they don't.

### Scene 4: How Agents Follow Rules (30 sec)

> Agents receive governance rules as part of their CLAUDE.md instructions. When an agent encounters a situation that conflicts with a rule, it should flag it.

**Visual:** Show the connection between governance page and agent behavior:

```text
Governance Page → CLAUDE.md template → Agent behavior
     ↓
"Only assert about your own repo"
     ↓
Agent: "This affects the frontend repo. I'll use gov_escalate to flag it."
```

### Scene 5: Escalation (20 sec)

> When an agent encounters a topic outside its remit, it uses `gov_escalate` to flag it. You'll see escalations in the Activity thread and in your notifications.

**Steps to show:**

1. Show an escalation notification
2. Click through to see the context
3. Show how the escalation references the governance rule that triggered it

### Scene 6: Wrap-up (20 sec)

> Governance keeps multi-agent coordination safe and predictable. Rules are set by org admins, applied to all agents in the project, and visible here for transparency.

## Screenshots Needed

| Screenshot | Description | Save as |
| ---------- | ----------- | ------- |
| `governance-rules-list.png` | Rules list grouped by type | `assets/members/governance-rules-list.png` |
| `governance-rule-detail.png` | Single rule with full description | `assets/members/governance-rule-detail.png` |
| `governance-escalation.png` | Escalation notification | `assets/members/governance-escalation.png` |
