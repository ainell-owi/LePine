# Workspace Structure Explained

## Overview

This document explains the overall structure of your "kirbys paw for higher" workspace, including what special folders like `.github/` and `.venv/` are, and how everything fits together.

## What Is `.github/` Folder?

The `.github/` folder contains **GitHub-specific configuration files** that help AI agents and tools understand your project.

### Location
- **Path**: `f:\kirbys paw for higher\.github\`
- **Key file**: `copilot-instructions.md`

### Purpose
- **AI Agent Instructions**: Tells AI coding assistants (like GitHub Copilot) how to work with your codebase
- **Project Context**: Explains the architecture, workflows, and patterns
- **Best Practices**: Documents project-specific conventions

### What's Inside
- `copilot-instructions.md` - Instructions for AI agents working in this workspace
- Explains the three-layer architecture
- Documents critical workflows (Python setup, AI tools sync, etc.)
- Lists project-specific patterns

### Why It Matters
When AI agents work in your workspace, they read `.github/copilot-instructions.md` to understand:
- How your project is organized
- What tools and workflows you use
- How to write code that fits your patterns

## What Is `.venv/` Folder?

The `.venv/` folder is a **Python virtual environment** - an isolated Python environment for your project.

### Location
- **Path**: `f:\kirbys paw for higher\python_envs\py314\venv\`
- **Note**: The actual `.venv/` is inside `python_envs/py314/`

### Purpose
- **Isolated Python Environment**: Keeps your project's Python packages separate from system Python
- **Version Control**: Ensures everyone uses the same package versions
- **Dependency Management**: Prevents conflicts between different projects

### What's Inside
- **Python interpreter**: Python 3.14 executable
- **Installed packages**: All Python libraries your project needs
- **Scripts**: Activation scripts for Windows (`activate.bat`, `Activate.ps1`)

### How to Use It

**Activate the virtual environment** (required before using Python):

```powershell
# Navigate to the venv folder
cd "F:\kirbys paw for higher\python_envs\py314\venv\Scripts"

# Activate (PowerShell)
.\Activate.ps1

# Or activate (Command Prompt)
.\activate.bat
```

**After activation**, your terminal prompt will show `(venv)` indicating the environment is active.

**Deactivate** when done:
```powershell
deactivate
```

### Why It Matters
- **Prevents conflicts**: Different projects can use different Python package versions
- **Clean environment**: Only installs what your project needs
- **Reproducible**: Others can recreate your exact environment

## Three-Layer Architecture

Your workspace is organized into three distinct layers:

### Layer 1: AI Development Tools (`GitHub Repos/`)
**Purpose**: Tools that enhance AI-assisted development

**Repositories**:
- `ai-lib/` - Reusable AI productivity tools (chat modes, instructions, MCP configs)
- `agentboost/` - CLI for generating project-aware `AGENTS.md` files

**Use Case**: Enhance AI assistance across all your projects

### Layer 2: Pine Script Ecosystem (`GitHub Repos/`)
**Purpose**: Everything related to Pine Script v6 development

**Repositories**:
- `pinescript-vscode-extension/` - VS Code extension with full v6 support
- `pinescriptv6/` - Complete v6 reference manual (LLM-ready markdown)
- `Pydantic-AI-Pinescript-Expert/` - RAG-based AI agent for Pine Script
- `PinescriptV6-docs-crawler/` - Documentation scraping tools
- `pinescript/` - 276+ technical indicators library (QuanTAlib)
- `awesome-pinescript/` - Curated Pine Script resources
- `pinescript-v6-mcp/` - MCP-formatted documentation
- `TradingView/` - Example scripts

**Use Case**: Build, test, and deploy Pine Script strategies

### Layer 3: Trading Components (`Indicators/`)
**Purpose**: Your actual trading strategies and indicators

**Folders**:
- `Indicators/indicators/` - Your custom indicators
- `Indicators/libraries/` - Your custom libraries
- `Indicators/strategies/` - Your trading strategies

**Use Case**: Your personal trading work

## Complete Folder Structure

```
kirbys paw for higher/
├── .github/                          ← GitHub configuration
│   └── copilot-instructions.md      (AI agent instructions)
│
├── GitHub Repos/                     ← All cloned repositories
│   ├── ai-lib/                       (AI productivity tools)
│   ├── agentboost/                   (Agent generation CLI)
│   ├── pinescript-vscode-extension/   (VS Code extension)
│   ├── pinescriptv6/                 (v6 reference manual)
│   ├── Pydantic-AI-Pinescript-Expert/ (RAG AI agent)
│   ├── PinescriptV6-docs-crawler/    (Docs scraper)
│   ├── pinescript/                   (276+ indicators)
│   ├── awesome-pinescript/           (Resource list)
│   ├── pinescript-v6-mcp/            (MCP docs)
│   └── TradingView/                  (Example scripts)
│
├── Indicators/                       ← Your personal work
│   ├── indicators/                  (Your custom indicators)
│   ├── libraries/                    (Your custom libraries)
│   └── strategies/                   (Your trading strategies)
│
├── python_envs/                      ← Python environments
│   ├── py314/
│   │   └── venv/                     ← Python virtual environment
│   │       ├── Scripts/
│   │       │   └── activate          (Activation script)
│   │       ├── Lib/
│   │       └── pyvenv.cfg
│   └── py315/
│
├── kirbysspilledmilk/                ← Personal files
│   ├── Pine Script v6 Trading Ecosystem_ GitHub Repositories and Integration Tools for 2025.pdf
│   └── rough_layout_of_workspace-idea.md
│
├── ai scripts/                       ← AI-related scripts
│   ├── copilot-instructions github.md
│   └── copilot-instructions.md
│
└── kirbys paw for higher.code-workspace  ← VS Code workspace file
```

## Key Concepts

### Virtual Environment (`.venv/`)
- Isolated Python environment
- Located in `python_envs/py314/venv/`
- Must activate before using Python
- Keeps dependencies separate

### GitHub Configuration (`.github/`)
- AI agent instructions
- Project documentation
- Helps AI understand your codebase

### Repository Organization (`GitHub Repos/`)
- All cloned repositories in one place
- Easy to find and update
- Separated by purpose (AI tools, Pine Script, etc.)

### Personal Work (`Indicators/`)
- Your custom trading code
- Separate from repository code
- Protected from repository updates

## Summary

- **`.github/`**: AI agent instructions and project configuration
- **`.venv/`**: Isolated Python environment (in `python_envs/py314/venv/`)
- **Three layers**: AI Tools → Pine Script Ecosystem → Trading Components
- **Organization**: Repos in `GitHub Repos/`, personal work in `Indicators/`
- **Python setup**: Always activate venv before Python operations

This structure keeps everything organized and makes it easy for both you and AI agents to understand your workspace!

