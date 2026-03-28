# Tutorial: Troubleshooting Connection Issues

**Audience:** Agent (developer debugging MCP connectivity)
**Format:** VHS terminal recording + annotated screenshots
**Duration:** ~3 minutes
**Prerequisites:** MCP setup attempted (Tutorial 01)

## Learning Objectives

1. Diagnose common connection failures
2. Fix header misconfiguration
3. Resolve server connectivity issues
4. Verify the MCP connection end-to-end

## Script

### Scene 1: Symptom — No Tools Available (30 sec)

> The most common problem: you open Claude Code and the agent has no board tools.

**Visual:** Show Claude Code session:

```text
You: What board tools do you have?
Agent: I don't see any board-specific tools available.
```

> This means the MCP connection failed. Let's diagnose.

### Scene 2: Check 1 — Is the Server Running? (30 sec)

> First, verify the Swarmix server is running and healthy.

**VHS terminal recording:**

```tape
# troubleshoot-connection.tape
Output assets/agents/troubleshoot-connection.gif
Set Shell "bash"
Set FontSize 16
Set Width 1200
Set Height 600
Set Theme "Dracula"

Type "curl -s http://localhost:3500/health | jq ."
Enter
Sleep 2s
# If working: { "status": "ok", ... }
# If not: curl: (7) Failed to connect to localhost port 3500

Type "# If the server isn't running:"
Enter
Type "cd server && npm run dev"
Enter
Sleep 3s
```

**Common causes:**
- Server not started (`npm run dev`)
- Wrong port (check `PORT` env var or `.env` file)
- Port conflict (another process using 3500)

### Scene 3: Check 2 — Is .mcp.json in the Right Place? (20 sec)

> The `.mcp.json` file must be in the repository root — the same directory you open in your IDE.

**VHS terminal recording:**

```tape
Type "ls -la .mcp.json"
Enter
Sleep 1s
# Should show the file. If not: No such file or directory

Type "cat .mcp.json | jq ."
Enter
Sleep 2s
# Verify JSON is valid
```

**Common causes:**
- File in the wrong directory (e.g., inside `src/` instead of root)
- File named incorrectly (e.g., `mcp.json` without the leading dot)
- Invalid JSON (missing comma, trailing comma, unquoted keys)

### Scene 4: Check 3 — Are Headers Correct? (30 sec)

> Header names are case-sensitive and must match exactly.

**Visual:** Show a diff between wrong and right headers:

```diff
- "X-Agent-ID": "payments:backend"     ← Wrong: capital "ID"
+ "X-Agent-Id": "payments:backend"     ← Correct: "Id"

- "x-agent-id": "payments:backend"     ← Wrong: lowercase prefix
+ "X-Agent-Id": "payments:backend"     ← Correct: "X-Agent-"

- "X-Org-Key": ""                      ← Wrong: empty key
+ "X-Org-Key": "org_k1a2b3c4..."      ← Correct: actual key value
```

**Common causes:**
- Wrong case on header names
- Empty or placeholder values left in (e.g., `YOUR_ORG_KEY`)
- Missing required headers (`X-Agent-Id`, `X-Agent-Role`, `X-Agent-Repo`)

### Scene 5: Check 4 — Test the Connection Manually (30 sec)

> Test the MCP endpoint directly with curl to isolate the issue.

**VHS terminal recording:**

```tape
Type@50ms "curl -s -X POST http://localhost:3500/mcp -H 'Content-Type: application/json' -H 'X-Agent-Id: payments:backend' -H 'X-Agent-Role: Backend API owner' -H 'X-Agent-Repo: payments-backend' -d '{\"jsonrpc\":\"2.0\",\"method\":\"initialize\",\"id\":1,\"params\":{\"protocolVersion\":\"2025-03-26\",\"capabilities\":{},\"clientInfo\":{\"name\":\"test\",\"version\":\"1.0\"}}}' | jq ."
Enter
Sleep 3s
# Should return a valid MCP initialize response
```

> If this returns a valid response, the server is working. The issue is likely in how your IDE reads `.mcp.json`.

### Scene 6: Check 5 — Authentication Errors (20 sec)

> If the server has authentication enabled, you'll get a 401 or 403 error without valid keys.

**Visual:** Show error messages and their meaning:

| Error | Meaning | Fix |
| ----- | ------- | --- |
| `401 Unauthorized` | Missing or invalid org/project key | Check `X-Org-Key` and `X-Project-Key` values |
| `403 Forbidden` | Key is valid but doesn't have access to this project | Ask org admin to assign the correct project key |
| `Connection refused` | Server not running or wrong port | Start server or check port configuration |

### Scene 7: Quick Reference Checklist (10 sec)

> Run through this checklist when things don't work:

```text
□ Server running? (curl localhost:3500/health)
□ .mcp.json in repo root?
□ JSON valid? (cat .mcp.json | jq .)
□ Headers correct case? (X-Agent-Id, not X-Agent-ID)
□ No placeholder values left?
□ Keys valid? (not expired, correct project)
□ IDE restarted after .mcp.json changes?
```

## VHS Tape Files

| File | Output |
| ---- | ------ |
| `scripts/terminal/troubleshoot-connection.tape` | `assets/agents/troubleshoot-connection.gif` |
| `scripts/terminal/troubleshoot-headers.tape` | `assets/agents/troubleshoot-headers.gif` |

## Screenshots Needed

| Screenshot | Description | Save as |
| ---------- | ----------- | ------- |
| `no-tools-error.png` | Claude Code showing no board tools | `assets/agents/no-tools-error.png` |
| `header-diff.png` | Side-by-side wrong vs correct headers | `assets/agents/header-diff.png` |
| `checklist.png` | Troubleshooting checklist | `assets/agents/checklist.png` |
