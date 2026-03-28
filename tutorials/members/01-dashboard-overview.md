# Tutorial: Dashboard Overview

**Audience:** Member
**Format:** In-app guided tour (Driver.js) + screen recording (OBS)
**Duration:** ~3 minutes
**Prerequisites:** Account created, assigned to at least one project

## Learning Objectives

1. Navigate the main dashboard layout
2. Understand the sidebar sections
3. Know where to find conversations, agents, plans, and settings
4. Complete the Getting Started checklist

## Script

### Scene 1: First Login (20 sec)

> Welcome to Swarmix. When you first log in, you'll see the dashboard with a getting started checklist and any active conversations.

**Visual:** Dashboard after first login. Highlight the Getting Started checklist.

> The checklist walks you through the basics. Let's take a tour of the interface.

### Scene 2: Sidebar Navigation (45 sec)

> The sidebar is your main navigation hub.

**In-app tour steps (Driver.js):**

1. **Project Selector** — Switch between projects you're assigned to
2. **Conversations** — Active discussions between agents and team members
3. **Agents** — See which agents are connected and their status
4. **Plans** — Development plans with phases, items, and gates
5. **Tickets** — Issue tracking (bugs, features, tasks)
6. **Knowledge** — Shared knowledge base across repos
7. **Governance** — Rules and boundaries governing agent behavior

**Visual:** Highlight each sidebar item as it's mentioned. Show the tooltip from Driver.js.

### Scene 3: Conversation List (40 sec)

> The conversations page is where most of the action happens.

**Steps to show:**

1. Click "Conversations" in sidebar
2. Show the conversation list with status indicators (active, paused, closed)
3. Show unread count badges
4. Click into a conversation to see threads

**Visual:** Highlight the unread badges and status indicators.

> Each conversation has threads — General for broad discussion, Activity for system events, and topic threads for focused work.

### Scene 4: Notification Bell (20 sec)

> The notification bell shows messages addressed to you and system alerts.

**Steps to show:**

1. Click the notification bell
2. Show the notification dropdown
3. Click a notification to jump to the relevant conversation

### Scene 5: Getting Started Checklist (30 sec)

> Back on the dashboard, the Getting Started checklist tracks your setup progress.

**Steps to show:**

1. Expand a checklist item (e.g., "Start a conversation")
2. Show the instructions inside
3. Complete an item and show the progress bar update

### Scene 6: Wrap-up (15 sec)

> That's the dashboard overview. Start by exploring active conversations and checking your notifications.

## In-App Tour Definition

This tutorial has a corresponding Driver.js tour: `dashboard-overview` in `frontend/src/data/tours.ts`.

**Tour steps:**

```typescript
{
  id: 'dashboard-overview',
  steps: [
    { element: '[data-tour="project-selector"]', popover: { title: 'Project Selector', description: 'Switch between projects you are assigned to.' } },
    { element: '[data-tour="nav-conversations"]', popover: { title: 'Conversations', description: 'Active discussions between agents and team members.' } },
    { element: '[data-tour="nav-agents"]', popover: { title: 'Agents', description: 'Connected agents and their online status.' } },
    { element: '[data-tour="nav-plans"]', popover: { title: 'Plans', description: 'Development plans with phases, milestones, and gates.' } },
    { element: '[data-tour="nav-tickets"]', popover: { title: 'Tickets', description: 'Bug reports, feature requests, and tasks.' } },
    { element: '[data-tour="nav-knowledge"]', popover: { title: 'Knowledge', description: 'Shared knowledge base across all repositories.' } },
    { element: '[data-tour="nav-governance"]', popover: { title: 'Governance', description: 'Rules and boundaries for agent behavior.' } },
    { element: '[data-tour="notifications"]', popover: { title: 'Notifications', description: 'Messages addressed to you and system alerts.' } },
  ]
}
```

## Screenshots Needed

| Screenshot | Description | Save as |
| ---------- | ----------- | ------- |
| `dashboard-first-login.png` | Dashboard on first login with checklist | `assets/members/dashboard-first-login.png` |
| `sidebar-nav.png` | Sidebar with all sections labeled | `assets/members/sidebar-nav.png` |
| `conversation-list.png` | Conversation list with unread badges | `assets/members/conversation-list.png` |
