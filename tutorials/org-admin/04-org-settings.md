# Tutorial: Organization Settings & Preferences

**Audience:** Org Admin
**Format:** Screen recording (OBS)
**Duration:** ~3 minutes
**Prerequisites:** Organization created, members invited (Tutorials 01-02)

## Learning Objectives

1. Navigate the organization settings page
2. Configure key organizational preferences
3. Manage plugins and integrations

## Script

### Scene 1: Introduction (10 sec)

> Let's walk through the organization settings — where you control how your Swarmix instance behaves.

**Visual:** Organization Settings page.

### Scene 2: General Settings (40 sec)

> The General tab is where you manage your organization's identity.

**Steps to show:**

1. Organization name and description — editable
2. Default project settings (if applicable)
3. Organization-wide notification preferences

**Visual:** Show each setting field with brief explanation.

### Scene 3: API Keys Management (40 sec)

> The API Keys tab shows all active keys — both org-level and per-project.

**Steps to show:**

1. View active org keys with creation date and last-used timestamp
2. Generate a new org key
3. Revoke an old key (show the confirmation dialog)
4. Navigate to a project's keys

**Visual:** Highlight the key list with status indicators.

> Keys show their last-used date so you can identify stale keys before revoking them.

### Scene 4: Plugins & Integrations (40 sec)

> Plugins extend Swarmix with external tool integrations — issue trackers, CI systems, and more.

**Steps to show:**

1. Navigate to the Plugins/Integrations tab
2. Show available integrations (Jira, Linear, ClickUp if configured)
3. Show how routing rules work — which tickets go to which external system
4. Show integration health status

**Visual:** Show the integrations list with status dots.

### Scene 5: Governance Defaults (30 sec)

> Organization-wide governance rules apply to all projects unless overridden.

**Steps to show:**

1. Navigate to Governance tab
2. Show default rules (boundary, protocol, responsibility)
3. Explain that projects can add project-specific rules on top

**Visual:** Show the governance rules list with enforcement toggles.

### Scene 6: Wrap-up (20 sec)

> That's the settings overview. Most of these are set-once-and-forget, but the API keys and integrations pages are where you'll return most often.

## Screenshots Needed

| Screenshot | Description | Save as |
| ---------- | ----------- | ------- |
| `settings-general.png` | General settings tab | `assets/org-admin/settings-general.png` |
| `settings-api-keys.png` | API keys list | `assets/org-admin/settings-api-keys.png` |
| `settings-plugins.png` | Plugins/integrations tab | `assets/org-admin/settings-plugins.png` |
| `settings-governance.png` | Governance defaults | `assets/org-admin/settings-governance.png` |
