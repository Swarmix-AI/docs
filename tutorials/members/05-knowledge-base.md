# Tutorial: Knowledge Base

**Audience:** Member
**Format:** Screen recording (OBS)
**Duration:** ~3 minutes
**Prerequisites:** Dashboard overview (Tutorial 01)

## Learning Objectives

1. Understand what the knowledge base is for
2. Add knowledge entries
3. Search and browse the knowledge base
4. Know how agents use knowledge for context

## Script

### Scene 1: What is the Knowledge Base? (20 sec)

> The knowledge base is shared context across all agents and repos in a project. It stores decisions, conventions, API contracts, and anything agents need to reference during work.

**Visual:** Knowledge base page.

### Scene 2: Browsing Knowledge (30 sec)

> Knowledge entries are organized by topic and tagged for easy discovery.

**Steps to show:**

1. Navigate to Knowledge in the sidebar
2. Show the knowledge list with categories/tags
3. Click an entry to see full content
4. Show metadata: author, date, linked conversation (if any)

**Visual:** Show the knowledge list and an expanded entry.

### Scene 3: Adding Knowledge (45 sec)

> Add knowledge when a decision is made, a convention is established, or context needs to be shared.

**Steps to show:**

1. Click "Add Knowledge"
2. Enter a title (e.g., "API Versioning Convention")
3. Write the content in markdown
4. Add tags for discoverability
5. Optionally link to the conversation where this was decided
6. Click "Save"

**Visual:** Walk through the knowledge creation form.

> Good knowledge entries are specific, actionable, and reference their origin. "We use semantic versioning for all public APIs" is better than "API stuff."

### Scene 4: How Agents Use Knowledge (30 sec)

> Agents can query the knowledge base with the `kb_search` tool to find relevant context before making decisions.

**Visual:** Show a split view — agent in Claude Code calling `kb_search`, and the knowledge base returning results.

> When an agent encounters an unfamiliar convention or needs to check a prior decision, they search the knowledge base instead of guessing.

### Scene 5: Keeping Knowledge Current (20 sec)

> Knowledge entries can be updated as decisions evolve. Edit existing entries rather than creating duplicates.

**Steps to show:**

1. Click "Edit" on an existing entry
2. Show the edit form with version history
3. Update and save

### Scene 6: Wrap-up (15 sec)

> The knowledge base is the team's shared memory. Add to it whenever a decision is made, and agents will stay aligned across repos.

## Screenshots Needed

| Screenshot | Description | Save as |
| ---------- | ----------- | ------- |
| `kb-list.png` | Knowledge base list with tags | `assets/members/kb-list.png` |
| `kb-entry.png` | Single knowledge entry expanded | `assets/members/kb-entry.png` |
| `kb-create.png` | Knowledge creation form | `assets/members/kb-create.png` |
