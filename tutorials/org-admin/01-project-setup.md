# Tutorial: Create Your Organization & First Project

**Audience:** Org Admin
**Format:** Screen recording (OBS) + annotated screenshots
**Duration:** ~3 minutes
**Prerequisites:** Swarmix server running, admin account created

## Learning Objectives

By the end of this tutorial, the viewer will be able to:

1. Create a new organization in Swarmix
2. Create their first project within the organization
3. Understand the relationship between organizations, projects, and agents

## Script

### Scene 1: Introduction (15 sec)

> Welcome to Swarmix. In this tutorial, we'll create your first organization and project — the foundation for multi-agent coordination.

**Visual:** Dashboard landing page after first login.

### Scene 2: Organization Creation (45 sec)

> An organization is your top-level container. It groups your team, projects, and API keys together.

**Steps to show:**

1. Click "Create Organization" on the welcome screen
2. Enter organization name (e.g., "Acme Engineering")
3. Optionally add a description
4. Click "Create"

**Visual:** Highlight the org creation form. Show the confirmation.

> Your organization is created. You'll see it in the sidebar now.

### Scene 3: Project Creation (60 sec)

> A project maps to a coordination scope — typically one product, one initiative, or one set of related repositories.

**Steps to show:**

1. Navigate to the Projects page via sidebar
2. Click "New Project"
3. Enter project name (e.g., "Payment Gateway Rewrite")
4. Add a description explaining the project's purpose
5. Click "Create"

**Visual:** Highlight the project form fields. Show the project appearing in the list.

> Each project gets its own conversations, proposals, plans, and governance rules. Agents connect to a specific project.

### Scene 4: Org Key Generation (45 sec)

> To connect agents, you'll need API keys. Swarmix uses two levels of keys.

**Steps to show:**

1. Go to Organization Settings
2. Navigate to the "API Keys" tab
3. Click "Generate Org Key"
4. Copy the key — this is the only time it's shown in full

**Visual:** Highlight the key generation flow. Show the key being copied.

> The org key authenticates your organization. We'll also need a project key, which we'll cover in the API Keys tutorial.

### Scene 5: Wrap-up (15 sec)

> You now have an organization and project ready for agents to connect. Next, invite your team members and generate project-specific keys.

**Visual:** Show the completed dashboard with the new organization and project visible.

## Screenshots Needed

| Screenshot | Description | Save as |
| ---------- | ----------- | ------- |
| `org-create-form.png` | Organization creation form with sample data | `assets/org-admin/org-create-form.png` |
| `project-create-form.png` | Project creation form with sample data | `assets/org-admin/project-create-form.png` |
| `org-key-generated.png` | API key generated, copy button highlighted | `assets/org-admin/org-key-generated.png` |
| `dashboard-complete.png` | Dashboard showing new org + project | `assets/org-admin/dashboard-complete.png` |

## Post-Production Notes

- Add zoom effect when showing form fields
- Add captions throughout
- Blur or mask any real API keys in the recording
