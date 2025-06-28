# Claude Code Configuration Directory

Personal configuration directory for [Claude Code](https://docs.anthropic.com/en/docs/claude-code), providing custom instructions and slash commands for AI-powered development sessions.

## Overview

This repository contains:
- **Global development guidelines** (`CLAUDE.md`) - Applied to all projects and sessions
- **Custom slash commands** (`commands/`) - Reusable workflow automation
- **Session management** - Tools for discovery, resumption, and task tracking

## Contents

### 📋 CLAUDE.md - Core Development Guidelines

Comprehensive coding guidelines based on living structures and incremental dialogue principles:

- **Structure-Preserving Transformations** - Evolve code through small, testable increments
- **BFS-Style Exploration** - Generate multiple approaches before committing
- **AIDER Integration** - AI-powered coding assistant usage patterns
- **Task Management Strategy** - Adaptive GitHub vs file-based tracking
- **Documentation Organization** - Timeless docs in files, temporal docs adaptively
- **Testing Patterns** - Proper unit testing without subprocess dependencies

Key principles:
- Make changes in 5-15 line increments
- Create permanent test files (no ad-hoc code execution)
- Follow existing patterns rather than imposing new ones
- Use tools over manual processes
- Base decisions on data/analysis

### 🔧 Slash Commands

#### `/resume` - Resume Development Session
Quick project context discovery for continuing work efficiently:
- Git state analysis (branch, status, recent commits)
- GitHub integration (issues, PRs)
- Documentation review
- Implementation testing
- Next step recommendations

#### `/new-task` - Create New Task Workflow  
Complete workflow for starting new features with proper GitHub integration:
- GitHub issue creation with structured templates
- Feature branch creation with issue linking
- Linking commit for session continuity
- Progress tracking integration

## Usage

### Global Application
The `CLAUDE.md` file is automatically applied to all Claude Code sessions, providing consistent development patterns across projects.

### Slash Commands
Use custom commands with the `/` prefix in Claude Code:
```
/resume    # Quick project context discovery
/new-task  # Start new feature with GitHub integration
```

### Session Discovery
When resuming work, commands help discover:
- Current branch and uncommitted changes
- Open GitHub issues and PRs
- Project documentation and specifications
- Working implementation status
- Clear next steps

## Documentation Philosophy

### Timeless vs Temporal Documentation

**Timeless Documents** - Always stored as files in `/docs/`:
- **Architecture decisions** - System design and patterns that persist across tasks
- **API documentation** - Interfaces and contracts that define the system
- **Development guidelines** - Code standards and practices that remain consistent
- **Core concepts** - Fundamental ideas that guide all development

**Temporal Documents** - Adaptive storage based on environment:
- **GitHub Strategy** (when available): Issues for requirements, PRs for implementation details
- **File Strategy** (fallback): `/docs/tasks/{task-name}/` for task-specific documentation
- **Task progress** - Session logs and development updates
- **Implementation decisions** - Task-specific technical choices

### Why This Separation Matters

1. **Timeless Knowledge Preservation** - Architecture and core concepts remain accessible in files regardless of GitHub availability
2. **Collaborative Efficiency** - Task discussions happen in GitHub when available for team coordination
3. **Environment Independence** - Essential documentation works offline and across different collaboration contexts
4. **Clean Code Repository** - Persistent knowledge stays in version control, temporary discussions in appropriate channels

## Benefits

- **Consistency** - Same high-quality development patterns across all projects
- **Efficiency** - Quick session startup and context discovery
- **Adaptive Tracking** - GitHub when available, files when not
- **Knowledge Preservation** - Critical docs always in files, task discussions where optimal
- **Structure Preservation** - Incremental changes that strengthen existing code
- **Tool Leverage** - AIDER and other AI tools for optimal productivity

## Development Philosophy

Based on living structures principles:
1. **Quality emerges from process, not upfront design**
2. **Small transformations preserve system wholeness**
3. **Continuous dialogue between intent and implementation**
4. **Generate solutions rather than fabricate them**

---

*For more details on Claude Code, see the [official documentation](https://docs.anthropic.com/en/docs/claude-code).*