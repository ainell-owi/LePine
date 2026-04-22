# AI Tool Ecosystem Guide

**When to use what, and why**

## The Claude Family

### 1. Claude Code (What You're Using Now)
**What**: AI pair programmer in your terminal/VS Code

**When to Use**:
- Writing and editing code
- Refactoring and debugging
- Git operations (commits, PRs)
- File operations (read, search, edit)
- Terminal commands
- Multi-file codebase work

**Strengths**:
- Full codebase context
- Direct file manipulation
- Git integration
- Tool execution (bash, grep, etc.)
- Persistent session in terminal
- Can read and modify ANY file in workspace

**Limitations**:
- Session-specific (no memory between sessions)
- Can't browse web directly (uses WebFetch tool)
- Limited to your local workspace

**Best For**: "Build this feature", "Fix this bug", "Refactor this code"

### 2. Claude App (claude.ai)
**What**: Conversational AI in browser

**When to Use**:
- Brainstorming ideas
- Learning concepts
- Asking questions
- Planning architecture
- Research and analysis
- When you don't need file access

**Strengths**:
- Projects feature (persistent memory within project)
- Can upload documents
- Web search capability
- Conversational interface
- Good for exploration

**Limitations**:
- Can't directly edit your files
- Can't execute commands
- No direct codebase access

**Best For**: "Explain this concept", "Help me plan this system", "What's the best approach?"

### 3. Claude API
**What**: Programmatic access to Claude

**When to Use**:
- Building AI-powered tools
- Automating workflows
- Integrating AI into applications
- Batch processing

**Strengths**:
- Full programmatic control
- Can be embedded in tools
- Scalable for automation

**Limitations**:
- Requires coding
- Pay per use
- No built-in UI

**Best For**: Building custom AI tools and automation

## Development Tools

### 4. GitHub Copilot
**What**: AI code completion in VS Code

**When to Use**:
- Writing code in real-time
- Auto-completing functions
- Generating boilerplate
- Getting quick suggestions

**Strengths**:
- Instant inline suggestions
- Context-aware completions
- Fast and unobtrusive
- Good for repetitive patterns

**Limitations**:
- Limited to code completion
- Can't refactor large files
- No terminal commands
- No multi-file operations

**Best For**: Active coding with smart autocomplete

**vs Claude Code**: Use Copilot for line-by-line coding, Claude Code for larger changes

### 5. MCP (Model Context Protocol) Servers
**What**: Extension system for Claude that adds specialized capabilities

**Available MCP Servers**:
- **File systems**: Access to specific directories
- **Databases**: Query databases directly
- **APIs**: Connect to external services
- **Tools**: Specialized tools (calculators, formatters, etc.)

**When to Use**:
- Need specialized data access
- Want to extend Claude capabilities
- Integrate external services
- Add domain-specific tools

**How to Set Up**: (We'll configure this together)
- Install MCP server packages
- Configure in Claude settings
- Servers load automatically

**Best For**: "Connect to my database", "Access this API", "Use this specialized tool"

## GitHub Tools

### 6. GitHub CLI (`gh`)
**What**: Command-line tool for GitHub operations

**When to Use** (via Claude Code):
- Creating pull requests
- Managing issues
- Viewing PR comments
- Repository operations
- GitHub Actions

**Usage**:
```bash
gh pr create --title "Feature" --body "Description"
gh issue list
gh pr view 123
```

**Best For**: Git operations without leaving terminal

### 7. GitHub Desktop
**What**: GUI for Git operations

**When to Use**:
- Visual diff viewing
- Drag-and-drop commits
- If you prefer GUI over CLI
- Learning git visually

**vs Git CLI**: Desktop is easier to learn, CLI is faster once you know it

## Decision Framework

### "I want to build a new feature"
→ **Claude Code**: Can write, test, and commit code

### "I want to understand a concept"
→ **Claude App**: Better for learning and discussion

### "I want autocomplete while coding"
→ **GitHub Copilot**: Real-time suggestions

### "I want to commit and push code"
→ **Claude Code**: Has git integration

### "I want to create a pull request"
→ **Claude Code**: Can use `gh pr create`

### "I want AI to access external data"
→ **MCP Server**: Extend Claude's capabilities

### "I want to visualize git history"
→ **GitHub Desktop** or VS Code Git extension

### "I want to automate AI workflows"
→ **Claude API**: Build custom tools

## Workflow Patterns

### Pattern 1: Feature Development
1. **Plan**: Claude App or Claude Code (brainstorm)
2. **Build**: Claude Code (write code)
3. **Code**: GitHub Copilot (autocomplete as you go)
4. **Commit**: Claude Code (git operations)
5. **PR**: Claude Code (`gh pr create`)

### Pattern 2: Learning & Research
1. **Learn**: Claude App (ask questions)
2. **Document**: Claude Code (write to files)
3. **Reference**: Keep in workspace for future

### Pattern 3: Debugging
1. **Investigate**: Claude Code (search codebase)
2. **Fix**: Claude Code (edit files)
3. **Test**: Claude Code (run tests)
4. **Commit**: Claude Code (git commit)

### Pattern 4: Idea Capture
1. **Brainstorm**: Claude App or sticky notes
2. **Document**: Claude Code (write to IDEAS.md)
3. **Organize**: Review and categorize periodically
4. **Execute**: Use Claude Code to build

## Your Current Setup

**Active Tools**:
- Claude Code (primary development)
- VS Code
- Git
- GitHub CLI (`gh`)
- Digital sticky notes (Windows)

**Available But Not Using**:
- GitHub Copilot (do you have this enabled?)
- MCP servers (not configured yet)
- Claude API (not needed yet)
- GitHub Desktop (using CLI instead)

**To Explore**:
- MCP servers for TradingView data
- MCP servers for financial APIs
- Custom agents for trading analysis
- Webhook integrations

## MCP Servers Worth Exploring

### For Your Trading Ecosystem:

1. **File System MCP**: Access to specific data directories
2. **Database MCP**: Store and query trading data
3. **HTTP MCP**: Connect to TradingView webhooks
4. **Python MCP**: Run Python scripts from Claude
5. **Custom MCP**: Build your own (e.g., "pinescript-expert-mcp")

### How MCP Enhances Claude Code:
- Adds specialized tools
- Connects to external services
- Provides domain-specific knowledge
- Extends capabilities beyond file/terminal operations

**Example**: A "TradingView MCP" could:
- Fetch chart data
- Validate Pine Script
- Access indicator library
- Query market data

## Quick Reference

| Task | Best Tool | Alternative |
|------|-----------|-------------|
| Write code | Claude Code | - |
| Autocomplete | Copilot | - |
| Learn concepts | Claude App | Claude Code |
| Git commit | Claude Code | Git CLI |
| Create PR | Claude Code (`gh`) | GitHub web |
| Brainstorm | Claude App | Claude Code |
| Debug | Claude Code | - |
| Access external data | MCP | API calls |
| Visual git | GitHub Desktop | VS Code |
| Automate | Claude API | MCP servers |

## Next Steps for You

1. **Enable GitHub Copilot** (if not already)
2. **Configure MCP servers** for trading data
3. **Set up webhook system** for TradingView alerts
4. **Build idea capture workflow** (see IDEA_CAPTURE.md)
5. **Explore Claude API** for automation later

## Common Confusion Cleared

**"Should I use Claude app or Claude Code?"**
- Coding/building → Claude Code
- Learning/planning → Either (your choice)
- Claude Code is more powerful for development

**"When do I need MCP?"**
- When Claude needs capabilities beyond files/terminal
- External data, specialized tools, service integration

**"What about agents?"**
- Agents are automated AI workers (can be built with API)
- Claude Code can spawn sub-agents for tasks
- We'll explore this when building trading automation

**"GitHub Copilot vs Claude Code?"**
- Use BOTH: Copilot for autocomplete, Claude Code for big changes
- They complement each other

## Summary

**Your Power Stack**:
- **Claude Code**: Primary development (you're already here!)
- **GitHub Copilot**: Real-time autocomplete
- **MCP Servers**: Specialized capabilities
- **Claude App**: When you prefer web interface

**Remember**:
- There's overlap between tools - that's OK
- Use what feels natural
- Start with Claude Code (you're doing it right)
- Add tools as you need them, not preemptively
- Don't worry about using "the right tool" - workflow matters more
