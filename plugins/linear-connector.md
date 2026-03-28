# Linear Connector

Bidirectional sync between Swarmix tickets and Linear issues.

**Status:** Available | **Minimum tier:** Team

## Features

- **Outbound:** Auto-create Linear issues when tickets are created in Swarmix
- **Inbound:** Webhook-driven updates when Linear issues change
- **Status mapping:** Map Swarmix statuses to Linear workflow states
- **Priority mapping:** Configurable priority value mapping

## Configuration

Set these values when adding the integration in the Swarmix dashboard:

| Field | Description |
|-------|-------------|
| `apiKey` | Linear API key (from Settings > API) |
| `teamId` | Linear team ID |
| `webhookSigningSecret` | Webhook signing secret for verification |

## How It Works

Once configured, Swarmix routes tickets to Linear based on the routing rules you set up in the integration settings (by type, priority, and labels).

- When a ticket is created in Swarmix that matches the routing rules, a corresponding Linear issue is created automatically
- When a Linear issue is updated, the webhook pushes changes back to the linked Swarmix ticket
- Status transitions, assignments, and priority changes are synced in both directions

## MCP Tools

Agents interact with integrations using these tools:

| Tool | Description |
|------|-------------|
| `integration_list` | See configured integrations and their routing rules |
| `integration_status` | Check sync health and recent errors |
| `ticket_link_external` | Manually link a Swarmix ticket to an existing Linear issue |
| `ticket_unlink_external` | Remove the sync link (does not delete the Linear issue) |
| `ticket_pull_external` | Force re-sync a ticket from Linear |
| `ticket_create_subtask` | Create a sub-ticket (also created as a Linear sub-issue if parent is synced) |
