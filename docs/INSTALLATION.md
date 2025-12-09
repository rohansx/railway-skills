# Installation Guide

## Prerequisites

### 1. Railway CLI

Install the Railway CLI:

```bash
npm install -g @railway/cli
```

Login to Railway:

```bash
railway login
```

### 2. Railway MCP Server

Add the Railway MCP Server to Claude Code:

```bash
claude mcp add railway-mcp-server -- npx -y @railway/mcp-server
```

Or add to your MCP config manually:

**Cursor (`.cursor/mcp.json`):**
```json
{
  "mcpServers": {
    "railway-mcp-server": {
      "command": "npx",
      "args": ["-y", "@railway/mcp-server"]
    }
  }
}
```

**VS Code (`.vscode/mcp.json`):**
```json
{
  "servers": {
    "railway-mcp-server": {
      "type": "stdio",
      "command": "npx",
      "args": ["-y", "@railway/mcp-server"]
    }
  }
}
```

## Installing Railway Skills

### Method 1: Claude Code Plugin (Recommended)

```bash
/plugin install rohanmhetar/railway-skills
```

### Method 2: Manual Installation

1. Clone the repository:
```bash
git clone https://github.com/rohanmhetar/railway-skills.git
```

2. Copy skills to your Claude Code skills directory:
```bash
cp -r railway-skills/skills/* ~/.claude/skills/
```

3. Restart Claude Code to load the skills.

## Verification

Test that everything is working:

1. Open Claude Code
2. Ask: "Check my Railway status"
3. Claude should use the `check-railway-status` tool
4. You should see confirmation that Railway CLI is installed and logged in

## Troubleshooting

### "Railway CLI not found"

Install the CLI:
```bash
npm install -g @railway/cli
```

### "Not logged in to Railway"

Login:
```bash
railway login
```

### "MCP server not responding"

1. Check MCP config is correct
2. Restart Claude Code
3. Try reinstalling: `npx -y @railway/mcp-server`

### Skills not activating

1. Verify skills are in `~/.claude/skills/`
2. Restart Claude Code
3. Try explicit trigger: "Using Railway MCP tools, deploy my app"

## Next Steps

Once installed, try these prompts:

- "Deploy my current directory to Railway"
- "Add a Postgres database to my Railway project"
- "Check my Railway deployment logs"
- "Help me debug my failed Railway deployment"
