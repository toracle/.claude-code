---
name: Resume Development Session
description: Quickly discover project context and continue work efficiently
version: 1.0
---

# Resume Development Session

Please help me resume development on this project by running the session startup discovery process:

## Environment Validation

First, verify the environment is properly set up:

!pwd
!ls -la
!git status || echo "❌ Not a git repository"
!which gh && gh auth status || echo "❌ GitHub CLI not available or not authenticated"

## Context Discovery

Check we were on a task:

<git-status>
!git branch --show-current
!git status
!git log --oneline -5
</git-status>

<github-status>
!gh issue list --state open
!gh pr list --state open
</github-status>

If we are on a git feature branch and have matched github issue, read those entries too:

* github issue body
* github issue comments
* related github PR body
* related github PR comments

## Documentation Review

Read project documentation to understand context and current specifications:

@README.md
@docs/README.md
@CLAUDE.md

## Tool Availability Check

Check if development tools are available:

!which aider && aider --version && !aider --help || echo "❌ AIDER not available"

## Analysis and Next Steps

Based on the discovery results:

1. **Current Branch Analysis**: 
   - If on `main`: Review recent commits and open issues for next task
   - If on feature branch: Extract issue number and check related GitHub issue
   - If uncommitted changes exist: Review and decide on commit vs continue

2. **Project State Summary**:
   - What functionality is currently working
   - What was completed in recent commits
   - What tasks are currently open/in-progress
   - Verify documentation links are working (README.md → docs/README.md → specific guides)

3. **Recommended Next Step**:
   - Provide specific, actionable next step based on current context
   - Consider: testing with real server, implementing new features, or fixing issues
   - Include relevant issue numbers and implementation approaches

4. **Implementation Notes**:
   - Reference project guidelines in CLAUDE.md
   - Use spiral development approach (minimal viable first)
   - Follow documentation-first development
   - Use GitHub issues for task coordination
   - **Use AIDER for coding tasks** - leverage AI-powered coding assistant for structure-preserving transformations

Please provide a concise summary and clear recommendation for continuing development.
