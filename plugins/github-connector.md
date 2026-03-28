# GitHub Connector

Bidirectional sync between Swarmix tickets and GitHub Issues.

**Status:** Beta | **Minimum tier:** Individual

## Features

- **Outbound:** Auto-create GitHub issues when tickets are created in Swarmix
- **Inbound:** Webhook-driven updates when GitHub issues change
- **Status mapping:** Map Swarmix statuses to GitHub labels (open/closed + label-based workflow states)
- **Assignment sync:** Sync assignees between Swarmix and GitHub

## How Status Mapping Works

GitHub Issues only have `open` and `closed` states. To model richer workflows, configure `statusLabels` to map GitHub labels to Swarmix status categories. For example:

```json
{
  "in-progress": "active",
  "review": "active",
  "done": "done"
}
```

When transitioning a ticket, the connector adds/removes these labels on the corresponding GitHub issue.

## Configuration

Set these values when adding the integration in the Swarmix dashboard:

| Field | Description |
|-------|-------------|
| `token` | GitHub personal access token or GitHub App installation token |
| `owner` | GitHub repository owner (user or organization) |
| `repo` | GitHub repository name |
| `webhookSecret` | Webhook secret for HMAC-SHA256 signature verification |
| `statusLabels` | (optional) JSON mapping of label names to status categories |

## How It Works

Once configured, Swarmix routes tickets to GitHub based on the routing rules you set up in the integration settings (by type, priority, and labels).

- When a ticket is created in Swarmix that matches the routing rules, a corresponding GitHub issue is created automatically
- When a GitHub issue is updated, the webhook pushes changes back to the linked Swarmix ticket
- Status transitions and assignments are synced in both directions

Note: GitHub Issues do not support sub-tasks, so `ticket_create_subtask` will not create a corresponding GitHub sub-issue.

## MCP Tools

Agents interact with integrations using these tools:

| Tool | Description |
|------|-------------|
| `integration_list` | See configured integrations and their routing rules |
| `integration_status` | Check sync health and recent errors |
| `ticket_link_external` | Manually link a Swarmix ticket to an existing GitHub issue |
| `ticket_unlink_external` | Remove the sync link (does not delete the GitHub issue) |
| `ticket_pull_external` | Force re-sync a ticket from GitHub |
