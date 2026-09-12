# Nanobot Robotic Arms 🤖

A personal AI assistant workspace repository for **nanobot**, a lightweight, open-source AI agent framework written in Python with a React/TypeScript WebUI.

## Overview

This repository serves as the workspace for configuring, extending, and managing nanobot agent instructions, workspace preferences, and long-term memory. It includes configuration templates, agent guidelines, and session management for multi-platform AI interactions.

## Tech Stack

- **Python**: 65.4% - Core agent logic and backend
- **TypeScript**: 20.8% - WebUI and frontend  
- **HTML/CSS**: 13.1% - UI styling and markup
- **Shell/PowerShell**: 0.6% - Utility scripts

## Repository Structure

```
nanobot-robotic-arms/
├── AGENTS.md                    # Agent instructions & workspace guidance
├── SOUL.md                      # Core principles & execution rules
├── USER.md                      # User profile & personalization
├── HEARTBEAT.md                 # Periodic background tasks
├── nanobot-main-1/              # Main nanobot source code
├── nanobot-design-system/       # Design system components
├── docs/                        # Documentation
├── memory/                      # Long-term memory storage
├── sessions/                    # Session history logs
├── prompts/                     # Prompt templates
├── cron/                        # Scheduled task configurations
└── .claude/                     # Claude-specific settings
```

## Quick Start

### Prerequisites

- Python 3.11+
- Node.js & Bun (for WebUI development)

### Key Files

- **[AGENTS.md](AGENTS.md)** - Start here for agent workspace guidance
- **[SOUL.md](SOUL.md)** - Core personality & execution principles
- **[USER.md](USER.md)** - Customize your user preferences

### Development Commands

```bash
# Python testing & linting
pytest tests/test_openai_api.py::test_function -v
ruff check nanobot/

# WebUI development (proxies to :8765)
cd webui && bun run dev
cd webui && bun run build
cd webui && bun run test

# Start the gateway
nanobot gateway
```

## Core Architecture

### Message Flow

1. **Channels** �� External platforms publish `InboundMessage` events
2. **MessageBus** → Async queue decouples channels from agent core
3. **AgentLoop** → Consumes messages, builds context, coordinates turns
4. **AgentRunner** → Executes LLM conversation loop with tool calls
5. **Channels** ← Responses published back to appropriate platform

### Key Subsystems

- **LLM Providers** - Anthropic, OpenAI, Azure, Bedrock, GitHub Copilot, etc.
- **Channels** - Telegram, Discord, Slack, Feishu, Matrix, WeChat, Teams, etc.
- **Tools** - Filesystem, shell execution, web search, MCP servers, cron, notebooks
- **Memory** - Session history with Dream two-phase consolidation
- **WebUI** - Vite-based React SPA with WebSocket multiplex protocol
- **API Server** - OpenAI-compatible HTTP endpoints (`/v1/chat/completions`)

## Features

✨ **Multi-Platform Support** - Integrate with 15+ chat channels  
🧠 **Advanced Memory** - Two-phase memory consolidation with atomic writes  
🛠️ **Rich Tools** - Filesystem, shell, web search, MCP, cron, notebooks  
🎨 **Modern WebUI** - Real-time React SPA with WebSocket communication  
⚙️ **Flexible Configuration** - Pydantic-based config with JSON aliases  
🔌 **OpenAI-Compatible API** - Use as a drop-in AI service  

## Configuration

Settings are stored in `~/.nanobot/config.json`. Key features:

- Support for camelCase JSON aliases
- Per-channel configurations
- LLM provider settings
- Heartbeat task scheduling

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md) for contribution flow and PR guidelines.

### Code Style

- Line length: 100 characters
- Linter: `ruff` with rules E, F, I, N, W
- Test framework: pytest with `asyncio_mode = "auto"`

## Documentation

- **Architecture Constraints**: `.agent/design.md`
- **Security Boundaries**: `.agent/security.md`  
- **Common Gotchas**: `.agent/gotchas.md`

## License

Check repository settings for license information.

## Contact

For issues or questions, open a GitHub issue or check the [discussions](https://github.com/csuqiceng/nanobot-robotic-arms/discussions).

---

**Last Updated**: 2026-09-12  
**Repository**: [csuqiceng/nanobot-robotic-arms](https://github.com/csuqiceng/nanobot-robotic-arms)
