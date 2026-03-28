# Jira Connector

Bidirectional sync between Swarmix tickets and Jira Cloud issues.

**Status:** Available | **Minimum tier:** Team

## Features

- **Outbound:** Auto-create Jira issues when tickets are created in Swarmix
- **Inbound:** Webhook-driven updates when Jira issues change
- **Status mapping:** Map Swarmix statuses to Jira workflow transitions
- **Sub-tasks:** Create Jira sub-tasks for child tickets
- **Priority mapping:** Configurable priority value mapping

## Configuration

Set these values when adding the integration in the Swarmix dashboard:

| Field | Description |
|-------|-------------|
| `baseUrl` | Jira Cloud instance URL (e.g. `https://yoursite.atlassian.net`) |
| `email` | Atlassian account email |
| `apiToken` | Atlassian API token (from [id.atlassian.net](https://id.atlassian.net)) |
| `projectKey` | Jira project key (e.g. `PROJ`) |
| `issueTypeId` | Default issue type ID |
| `subtaskIssueTypeId` | Sub-task issue type ID (optional) |
| `webhookSecret` | Shared secret for webhook verification |

## How It Works

Once configured, Swarmix routes tickets to Jira based on the routing rules you set up in the integration settings (by type, priority, and labels).

- When a ticket is created in Swarmix that matches the routing rules, a corresponding Jira issue is created automatically
- When a Jira issue is updated, the webhook pushes changes back to the linked Swarmix ticket
- Status transitions, assignments, and sub-task creation are synced in both directions

## MCP Tools

Agents interact with integrations using these tools:

| Tool | Description |
|------|-------------|
| `integration_list` | See configured integrations and their routing rules |
| `integration_status` | Check sync health and recent errors |
| `ticket_link_external` | Manually link a Swarmix ticket to an existing Jira issue (e.g. `PROJ-123`) |
| `ticket_unlink_external` | Remove the sync link (does not delete the Jira issue) |
| `ticket_pull_external` | Force re-sync a ticket from Jira |
| `ticket_create_subtask` | Create a sub-ticket (also created as a Jira sub-task if parent is synced) |
