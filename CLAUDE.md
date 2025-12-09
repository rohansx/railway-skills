# CLAUDE.md - Railway Skills

This repository contains Claude Code skills for Railway deployments.

## Project Structure

```
railway-skills/
├── skills/                    # Individual skill folders
│   ├── railway-mcp-tools/     # MCP tool usage (HIGHEST PRIORITY)
│   ├── railway-deployment/    # Deployment patterns
│   ├── railway-environment/   # Environment variables
│   ├── railway-templates/     # Template deployments
│   ├── railway-troubleshooting/ # Debugging guide
│   └── railway-patterns/      # Multi-service architectures
├── docs/                      # Documentation
├── evaluations/               # Test scenarios
├── .claude-plugin/            # Plugin config
├── CLAUDE.md                  # This file
├── README.md                  # Main documentation
└── LICENSE                    # MIT License
```

## How Skills Work

Each skill in `skills/` has a `SKILL.md` file that Claude Code loads when relevant queries are detected.

### Activation Triggers

Skills activate automatically based on query content:
- "Deploy to Railway" → railway-mcp-tools + railway-deployment
- "Add Postgres" → railway-templates
- "Deployment failing" → railway-troubleshooting
- "Connect frontend to backend" → railway-patterns + railway-environment

## Key Concepts

### Railway MCP Server
These skills work with the official Railway MCP Server (`@railway/mcp-server`).
The MCP server provides tools like `deploy`, `list-services`, `set-variables`.
Skills teach Claude HOW to use these tools effectively.

### Critical Gotchas
1. **PORT**: Never hardcode - Railway assigns dynamically
2. **DATABASE_URL**: Use reference syntax `${{Postgres.DATABASE_URL}}`
3. **Private networking**: Use `RAILWAY_PRIVATE_DOMAIN` for internal services
4. **Always check status first**: `check-railway-status` before any operation

## Development

To add a new skill:
1. Create folder in `skills/`
2. Add `SKILL.md` with content
3. Follow existing skill format
4. Add evaluations in `evaluations/`

## Testing

Skills should be tested with real Railway deployments:
1. Install Railway CLI
2. Login with `railway login`
3. Install MCP server
4. Test skill activation with sample prompts
