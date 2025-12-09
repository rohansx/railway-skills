# railway-skills

**Expert Claude Code skills for deploying flawless apps on Railway using the official Railway MCP Server**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Railway MCP](https://img.shields.io/badge/railway--mcp-compatible-green.svg)](https://github.com/railwayapp/railway-mcp-server)

---

## 🎯 What is this?

This repository contains **6 complementary Claude Code skills** that teach AI assistants how to deploy and manage production-ready applications on Railway using the [official Railway MCP Server](https://github.com/railwayapp/railway-mcp-server).

### Why These Skills Exist

Deploying apps on Railway via AI can be challenging. Common issues include:

* Not knowing which MCP tool to use for what task
* Environment variable gotchas (PORT, DATABASE_URL patterns)
* Deployment failures from missing configurations
* Multi-service architectures that don't connect properly

These skills solve these problems by teaching Claude:

* ✅ Correct Railway MCP tool usage patterns
* ✅ Environment variable best practices and gotchas
* ✅ Proven deployment patterns for common stacks
* ✅ Troubleshooting deployment failures
* ✅ Multi-service architecture patterns

---

## 📚 The 6 Skills

### 1. **Railway MCP Tools Expert** (HIGHEST PRIORITY)

Expert guide for using Railway MCP tools effectively.

**Activates when**: Deploying projects, managing services, working with Railway infrastructure.

**Key Features**:
* Tool selection guide (which tool for which task)
* Correct parameter formats and options
* Common mistakes and how to avoid them
* Workflow sequences for complex operations

### 2. **Railway Deployment**

Master Railway deployments from code to production.

**Activates when**: Deploying apps, fixing deploy failures, configuring builds.

**Key Features**:
* Deployment workflow checklist
* `railway.toml` configuration guide
* Dockerfile vs Nixpacks decision tree
* Health check configuration
* Zero-downtime deployment patterns

### 3. **Railway Environment**

Environment variables, secrets, and configuration management.

**Activates when**: Setting env vars, connecting services, managing secrets.

**Key Features**:
* **Critical gotcha**: Railway assigns PORT dynamically
* Database connection patterns (DATABASE_URL vs individual vars)
* Service-to-service communication via private networking
* Reference variables (${{service.VAR}})
* Secrets management best practices

### 4. **Railway Templates**

Deploy from Railway's 650+ template library.

**Activates when**: Deploying databases, queues, pre-built services.

**Key Features**:
* Template discovery patterns
* Popular template configurations (Postgres, Redis, etc.)
* Customizing template deployments
* Connecting templates to your services

### 5. **Railway Troubleshooting**

Debug deployment failures and runtime issues.

**Activates when**: Deployments fail, services crash, connections timeout.

**Key Features**:
* Build failure diagnosis
* Runtime crash debugging
* Connection refused troubleshooting
* Log interpretation guide
* Common error catalog with solutions

### 6. **Railway Patterns**

Multi-service architecture patterns for production apps.

**Activates when**: Building full-stack apps, microservices, production architectures.

**Key Features**:
* Frontend + Backend + Database pattern
* API Gateway patterns
* Background worker patterns
* Monorepo deployment strategies
* Production checklist

---

## 🚀 Installation

### Prerequisites

1. **Railway MCP Server** installed and configured
   ```bash
   # For Claude Code:
   claude mcp add railway-mcp-server -- npx -y @railway/mcp-server
   ```

2. **Railway CLI** installed and logged in
   ```bash
   npm install -g @railway/cli
   railway login
   ```

3. **Claude Code** or compatible AI assistant

### Install Skills

**Method 1: Claude Code Plugin** (Recommended)

```bash
/plugin install rohanmhetar/railway-skills
```

**Method 2: Manual Installation**

```bash
# Clone this repository
git clone https://github.com/rohanmhetar/railway-skills.git

# Copy skills to Claude Code skills directory
cp -r railway-skills/skills/* ~/.claude/skills/
```

---

## 💡 Usage

Skills activate **automatically** when relevant queries are detected:

```
"Deploy my app to Railway"
→ Activates: Railway MCP Tools Expert + Railway Deployment

"Set up a Postgres database"
→ Activates: Railway Templates

"My deployment is failing"
→ Activates: Railway Troubleshooting

"Connect my frontend to my backend"
→ Activates: Railway Patterns + Railway Environment

"What environment variables do I need?"
→ Activates: Railway Environment
```

### Skills Work Together

When you ask: **"Deploy a Next.js app with Postgres database"**

1. **Railway MCP Tools Expert** identifies correct tool sequence
2. **Railway Templates** deploys Postgres from template library
3. **Railway Deployment** configures Next.js build settings
4. **Railway Environment** sets up DATABASE_URL connection
5. **Railway Patterns** ensures proper service linking

All skills compose seamlessly!

---

## 📖 Documentation

* [Installation Guide](docs/INSTALLATION.md) - Detailed setup instructions
* [Usage Guide](docs/USAGE.md) - How to use skills effectively
* [Contributing Guide](docs/CONTRIBUTING.md) - How to contribute

---

## 🔗 Related Projects

* [railway-mcp-server](https://github.com/railwayapp/railway-mcp-server) - Official Railway MCP Server
* [Railway CLI](https://docs.railway.com/guides/cli) - Railway command-line interface
* [Railway Templates](https://railway.com/templates) - Template marketplace
* [n8n-skills](https://github.com/czlonkowski/n8n-skills) - Inspiration for this project

---

## 📊 What's Included

* **6** complementary skills that work together
* **650+** Railway templates supported
* **Production-tested** deployment patterns
* **Comprehensive** error catalogs and troubleshooting guides

---

## 📝 License

MIT License - see [LICENSE](LICENSE) file for details.

---

## 🙏 Credits

Inspired by [n8n-skills](https://github.com/czlonkowski/n8n-skills) by Romuald Członkowski.

---

**Ready to deploy flawless apps on Railway? Get started now!** 🚀
