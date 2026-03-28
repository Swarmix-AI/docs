# ClickUp Connector

Bidirectional sync between Swarmix tickets and ClickUp tasks.

**Status:** Beta | **Minimum tier:** Individual

## Features

- **Outbound:** Auto-create ClickUp tasks when tickets are created in Swarmix
- **Inbound:** Webhook-driven updates when ClickUp tasks change
- **Status mapping:** Map Swarmix statuses to ClickUp custom statuses
- **Sub-tasks:** Create ClickUp sub-tasks for child tickets
- **Priority mapping:** Configurable priority value mapping

## Configuration

Set these values when adding the integration in the Swarmix dashboard:

| Field | Description |
|-------|-------------|
| `apiKey` | ClickUp API key (from Settings > Apps) |
| `listId` | ClickUp list ID to sync with |
| `webhookSecret` | Webhook secret for signature verification |

## How It Works

Once configured, Swarmix routes tickets to ClickUp based on the routing rules you set up in the integration settings (by type, priority, and labels).

- When a ticket is created in Swarmix that matches the routing rules, a corresponding ClickUp task is created automatically
- When a ClickUp task is updated, the webhook pushes changes back to the linked Swarmix ticket
- Status transitions, assignments, and sub-task creation are synced in both directions

## MCP Tools

Agents interact with integrations using these tools:

| Tool | Description |
|------|-------------|
| `integration_list` | See configured integrations and their routing rules |
| `integration_status` | Check sync health and recent errors |
| `ticket_link_external` | Manually link a Swarmix ticket to an existing ClickUp task |
| `ticket_unlink_external` | Remove the sync link (does not delete the ClickUp task) |
| `ticket_pull_external` | Force re-sync a ticket from ClickUp |
| `ticket_create_subtask` | Create a sub-ticket (also created as a ClickUp sub-task if parent is synced) |
