# Slack Connector

Send Swarmix notifications to Slack channels with Block Kit formatting.

**Status:** Available | **Minimum tier:** Team

## Features

- **Ticket events:** Created, transitioned, assigned
- **Proposal events:** Submitted, resolved (accepted/rejected)
- **Agent events:** Connected, disconnected
- **Block Kit formatting:** Rich messages with fields, buttons, and severity colors
- **Channel routing:** Route different event types to different channels

This is a one-way (outbound) connector — Swarmix sends notifications to Slack, but Slack messages are not synced back to Swarmix.

## Configuration

Set these values when adding the integration in the Swarmix dashboard:

| Field | Description |
|-------|-------------|
| `botToken` | Slack Bot User OAuth Token (starts with `xoxb-`) |
| `signingSecret` | Slack App Signing Secret (for webhook verification) |
| `defaultChannelId` | Default channel ID for notifications |
| `channelOverrides` | (optional) Route specific event types to specific channels |

## Channel Overrides

You can route different events to different Slack channels:

```json
{
  "ticket.created": "C0123TICKETS",
  "proposal.created": "C0123PROPOSALS",
  "agent.connected": "C0123OPS"
}
```

Events without an override go to the `defaultChannelId`.
