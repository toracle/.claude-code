# new-task - Create new task workflow

Prompt instruction for setting up GitHub issue, branch, and linking commit

## Environment Check

First, verify required tools are available:

!git status || echo "❌ Not a git repository"
!which gh && gh auth status || echo "❌ GitHub CLI not available or not authenticated"
!which aider && aider --version || echo "❌ AIDER not available"

## Usage
Use this when starting a new task or feature to ensure proper GitHub integration and session continuity.

## Workflow Steps

### 1. Create GitHub Issue
```bash
gh issue create --title "Your Task Title" --body "
## Overview
Brief description of what needs to be done and why.

## Current State  
What exists now and what's missing.

## Acceptance Criteria
- [ ] Specific, testable requirements
- [ ] Clear success metrics
- [ ] Implementation boundaries

## Success Metrics
How we'll know this is complete and valuable.
"
```

### 2. Create Feature Branch
Use issue number in branch name for linking:
```bash
# Pattern: feature/{description}-issue-{number}
git checkout -b feature/your-task-description-issue-N
```

### 3. Create Linking Commit
```bash
git commit --allow-empty -m "Start implementation of [task name]

Related to #N: [GitHub issue title]

This branch implements:
- [Key implementation points]
- [Reference to acceptance criteria]

See GitHub issue #N for detailed acceptance criteria and progress tracking."
```

### 4. Development Process
- Update issue description with progress checkboxes
- Reference issue in commit messages: `Add feature (#N)`
- Create PR when ready: "Related Issue: Closes #N"

## Benefits
- **Session Continuity**: Any session can discover context via branch name
- **GitHub Integration**: Automatic cross-references and issue closing
- **Progress Tracking**: Clear requirements and completion criteria
- **Team Collaboration**: Centralized discussion and decision tracking

## Discovery Commands
Future sessions can find context with:
```bash
git branch --show-current                    # Shows current branch with issue number
gh issue view $(git branch --show-current | grep -o 'issue-[0-9]*' | cut -d'-' -f2)
```
