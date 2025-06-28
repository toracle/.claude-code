# Code Generation Guidelines: The Living Process of Incremental Dialogue

> Leverage wisdom about living structures and the practical need for incremental dialogue to guide meaningful software development through responsive, attentive processes of small transformations.

## Philosophical Foundation

Meaningful software emerges through a **responsive, attentive process of small transformations** guided by continuous feedback and respect for existing patterns. This approach draws from two fundamental insights:

1. **Living Structures**: Software systems, like living organisms, have natural centers of vitality that must be preserved and strengthened rather than disrupted
2. **Incremental Dialogue**: Development proceeds through continuous conversation between intent and implementation, allowing solutions to evolve organically

These principles point to the same truth: **quality emerges from process, not from upfront design**.

## Executive Summary

This document provides comprehensive guidelines for AI coding agents, covering:
- **Core Development Principles** - Philosophical foundation rooted in living structures
- **Implementation Process** - Detailed workflow for structure-preserving transformations
- **Tool Usage Guides** - Practical instructions for development tools
- **Documentation Strategy** - How to organize and maintain project knowledge
- **Quick Reference** - Essential patterns and decision frameworks

Designed for generic use across projects while maintaining deep philosophical grounding and practical utility.

## Table of Contents

1. [Core Development Principles](#core-development-principles)
2. [Tool Usage Guides](#tool-usage-guides)
   - [AIDER Tool Usage](#aider-tool-usage)
   - [Testing Patterns](#testing-patterns)
3. [Documentation Strategy](#documentation-strategy)
4. [Quick Reference](#quick-reference)

---

# Core Development Principles

Fundamental principles guiding quality software development through incremental, structure-preserving transformations.

## 1. Structure-Preserving Baby Steps
**Rule**: Evolve code through small, testable increments that respect existing patterns.

**Implementation**:
- Make changes of 5-15 lines per iteration (flexible based on context)
- Verify each change with immediate testing
- Allow complexity to emerge gradually rather than through upfront design
- Enable course correction without major rework
- Use mocking for UI or external dependencies (database, network)
- Respect API call limits - keep steps small

## 2. Living Centers & Explicit Assumptions
**Rule**: Identify and strengthen key abstractions that give the system coherence.

**Implementation**:
- State your interpretation of requirements before implementing
- Maintain appropriate boundaries while enabling necessary relationships
- Separate fact from inference in your understanding
- Strengthen existing patterns rather than imposing new ones

## 3. Validation Through Working Examples
**Rule**: Each transformation should enhance the wholeness of the system.

**Implementation**:
- Check alignment with intent frequently through working examples
- Look for latent structure wanting to emerge from the current state
- Request specific feedback on crucial design decisions
- Verify behavior preservation after each change

## 4. Generate, Don't Fabricate; Explore, Don't Assume
**Rule**: Build upon existing patterns rather than imposing artificial structures. When direction is unclear, explore multiple paths.

**Implementation**:
- **BFS-Style Exploration**: When facing decisions, present small alternatives for 3-4 different approaches
- **Structure-Preserving Evaluation**: For each option, assess which strengthens existing patterns most naturally
- **Empirical Validation**: Let working examples guide direction rather than theoretical analysis
- **Follow Natural Flow**: Look for the solution that wants to emerge from the problem domain
- **Code Sketches**: Use minimal implementations to validate understanding before committing
- **Pattern Recognition**: Study existing code patterns and domain context to inform choices

**Example Decision Process**:
1. Identify 3-4 viable approaches
2. Create minimal prototypes for each
3. Evaluate which feels most "at home" in the existing codebase
4. Choose the path that strengthens rather than disrupts existing centers
5. Proceed incrementally with chosen approach

## Living Development Workflow

### Phase 1: Observe & Understand (Sensing the Living Centers)
- **Study existing code patterns** and domain context with fresh eyes
- **Identify the living centers** - What gives this system its coherence and vitality?
- **Recognize the forces at play** - What tensions and requirements shape this domain?
- **Surface potential misinterpretations** before proceeding - separate fact from assumption
- **Feel for the natural structure** wanting to emerge from the current state

### Phase 2: Explore & Evaluate (BFS-Style Investigation)
- **Generate 3-4 viable approaches** when direction is unclear
- **Create minimal prototypes** for each approach (5-15 lines each)
- **Evaluate structure-preservation** - Which approach strengthens existing patterns?
- **Assess natural fit** - Which feels most "at home" in the codebase?
- **Choose the path** that enhances wholeness rather than fragmenting it

### Phase 3: Transform & Validate (Incremental Implementation)
- **Make small, structure-preserving transformations** (5-15 lines per step)
- **Verify behavior preservation** and alignment with intent after each step
- **Refactor continuously** as complexity emerges naturally
- **Be willing to backtrack** when a transformation feels forced or unnatural
- **Let the solution unfold** rather than imposing preconceived structure

### Phase 4: Communicate & Evolve (Dialogue-Driven Refinement)
- **Make your reasoning transparent** - explain why this approach feels right
- **Connect implementation to requirements** through working examples
- **Show concrete evidence** of structure preservation and enhancement
- **Request specific feedback** on crucial design decisions
- **Allow the solution to evolve** through responsive dialogue rather than rigid adherence to initial plans



# Specific Development Principles

Detailed principles for maintaining code quality and development efficiency, discovered and refined through practice.

## Principle 1: No Ad-Hoc Code Execution

**Rule**: Never run ad-hoc test code directly. Always create permanent test files.

### Why This Matters
- **Regression Testing**: Ad-hoc code is lost, permanent tests can be rerun
- **Documentation**: Test files serve as living documentation of expected behavior
- **Collaboration**: Other developers can understand and verify functionality
- **Quality Assurance**: Systematic testing prevents future breakage

### Implementation
```python
# ❌ BAD: Ad-hoc testing
# Running: python -c "from wbweb import HiccupRenderer; print(renderer.render(...))"

# ✅ GOOD: Permanent test file
# File: tests/test_extraction_verification.py
class TestHiccupRendererExtraction:
    def test_basic_functionality(self):
        from wbweb import HiccupRenderer
        renderer = HiccupRenderer()
        result = renderer.render(["p", {}, "Hello"])
        assert result == "<p>Hello</p>"
```

### Examples in Practice
- **Structure Analysis**: Create analysis tools instead of manual exploration
- **Extraction Verification**: Create verification tests instead of ad-hoc import tests
- **Functionality Testing**: Permanent test suites over temporary validation scripts

## Principle 2: Structure-Preserving Transformations

**Rule**: Make changes that strengthen existing patterns rather than imposing new ones.

### Core Concepts
- **Preserve Existing Centers**: Identify and strengthen the vital structures already present
- **Small Incremental Steps**: Transform gradually to maintain system wholeness
- **Follow Natural Flow**: Let the solution emerge from the problem domain
- **Validate Continuously**: Verify each step preserves functionality

### Implementation Pattern
1. **Observe**: Understand existing structure and patterns
2. **Transform**: Make minimal changes that respect existing design
3. **Validate**: Verify the transformation preserves wholeness
4. **Iterate**: Build on successful transformations

### Examples in Practice
- **Component Extraction**: Minimal changes when structure already fits
- **Package Organization**: Follow existing project structure patterns
- **Test Structure**: Preserve original test patterns while adding verification

## Principle 3: Tool Creation Over Manual Work

**Rule**: When facing repetitive or complex analysis, create reusable tools instead of manual processes.

### Why This Matters
- **Scalability**: Tools can be reused across sessions and projects
- **Accuracy**: Automated analysis reduces human error
- **Documentation**: Tools serve as executable documentation of processes
- **Efficiency**: Amortize effort across multiple uses

### Examples in Practice
- **Structure Analyzer**: Create systematic codebase analysis tools
- **Verification Framework**: Build validation frameworks for testing extractions
- **Progress Tracking**: File-based documentation system for multi-session work

## Principle 4: Data-Driven Decision Making

**Rule**: Base decisions on systematic analysis rather than assumptions or intuition.

### Implementation
- **Coupling Analysis**: Use dependency graphs to determine extraction order
- **Complexity Metrics**: Lines of code, dependency counts, business logic detection
- **Validation Results**: Test outcomes guide next steps

### Examples in Practice
- **Extraction Order**: Use coupling scores to identify optimal targets
- **Business Logic Detection**: Keyword-based analysis to identify components needing cleanup
- **Success Metrics**: Test pass rates validate extraction success

## Principle 5: Incremental Validation

**Rule**: Validate each step immediately rather than building up unverified complexity.

### Why This Matters
- **Early Error Detection**: Catch problems when they're easy to fix
- **Confidence Building**: Each validated step increases confidence in approach
- **Rollback Capability**: Small steps make it easy to backtrack when needed

### Implementation Pattern
1. **Make Small Change**: 5-15 lines of code or single concept
2. **Immediate Validation**: Run tests, verify behavior
3. **Document Results**: Update progress, commit working state
4. **Plan Next Step**: Based on validation results

### Examples in Practice
- **Component Extraction**: Validate imports, then functionality, then complete test suite
- **Package Structure**: Set up structure, then implementation, then tests
- **Each Session**: Commit working state before proceeding

## Principle 6: Living Documentation

**Rule**: Documentation should evolve with the codebase and serve multiple purposes.

### Characteristics of Living Documentation
- **Executable**: Tests and analysis scripts that document by running
- **Evolving**: Updated as understanding deepens
- **Multi-Purpose**: Serves both human readers and automated processes
- **Discoverable**: Organized for easy navigation and reference

### Examples in Practice
- **Analysis Tools**: Document codebase while providing analysis
- **Verification Tests**: Document expected behavior while ensuring correctness
- **Progress Tracking**: Record decisions and reasoning for future reference

## Principle 7: Separation of Concerns in Documentation

**Rule**: Distinguish between timeless architectural knowledge and temporal task-specific information.

### Implementation
- **Timeless Docs** (`/docs/`): Architecture, principles, API documentation
- **Temporal Docs** (`/docs/tasks/{branch-name}/`): Task plans, progress, decisions
- **Archive on Completion**: Move temporal docs to archive after task completion

## Principle 8: Proper Unit Testing Patterns

**Rule**: Use standard unit testing practices, avoid subprocess calls and external process dependencies in tests.

### Why This Matters
- **Reliability**: Subprocess tests are brittle and dependent on external environment
- **Speed**: In-process tests run faster than subprocess calls
- **Isolation**: Unit tests should test units in isolation, not integration across processes
- **Maintainability**: Standard testing patterns are easier to understand and maintain

### Anti-Patterns to Avoid
```python
# ❌ BAD: Using subprocess.run() in tests
result = subprocess.run([
    sys.executable, "-c", 
    "from external_package import Component; print(Component().method())"
], capture_output=True, text=True)

# ❌ BAD: Testing external codebases from within your test suite
# Tests in wbweb should not be responsible for testing wbgpt functionality
```

### Preferred Patterns
```python
# ✅ GOOD: Direct unit testing
from wbweb import Component
component = Component()
result = component.method()
assert result == expected

# ✅ GOOD: Mock external dependencies if needed
from unittest.mock import Mock
mock_external = Mock()
mock_external.method.return_value = "expected"
```

### Implementation Guidelines
- **Test Your Code**: Focus tests on the code you own and control
- **Mock Dependencies**: Use mocking for external dependencies, not subprocess calls
- **Integration Tests Separate**: Keep integration tests separate from unit tests
- **Cross-System Testing**: If needed, use proper integration testing frameworks

### Examples in Practice
- **Fixed**: Replace subprocess-based external testing with focused unit tests
- **Improved**: Use mocks for Request objects instead of subprocess calls
- **Better Isolation**: Test component logic without external process dependencies

## Principle Integration

These principles work together to create a sustainable development process:

1. **Tool Creation** provides the infrastructure
2. **Data-Driven Decisions** guide the direction  
3. **Structure-Preserving Transformations** maintain quality
4. **Incremental Validation** ensures each step works
5. **No Ad-Hoc Code** preserves knowledge
6. **Living Documentation** captures the process
7. **Separation of Concerns** organizes knowledge properly
8. **Proper Unit Testing** ensures reliable, maintainable validation

The result is a development process that scales, preserves knowledge, and maintains system quality over time.

---

# Tool Usage Guides

Practical instructions for using development tools effectively within the coding agent workflow.

## AIDER Tool Usage

AIDER is an AI-powered coding assistant for non-interactive command-line usage - perfect for automated coding tasks. Use it with coding task actively to save cost.

### 🚀 Pre-Configured Setup
**AIDER is typically pre-configured when available.** No setup usually needed!

### ✅ Session Setup Check
**At the start of each coding session, verify AIDER availability:**

```bash
# Quick session check (run once per session)
which aider && aider --version
```

**Expected Output:**
```
✅ /usr/local/bin/aider (or path)
✅ aider 0.x.x
```

**If available → AIDER can be used throughout the session**  
**If not available → use regular coding tools only**

### ⚡ Non-Interactive Command-Line Usage

AIDER excels at one-shot coding tasks via command line - perfect for structure-preserving transformations:

```bash
# Basic pattern (for simple, isolated changes)
aider -m "your coding request"

# Target specific files (most common pattern)
aider --file path/to/file.py -m "your coding request"

# Include context files (for structure-aware changes)
aider --file main.py --read docs/spec.md -m "implement feature X"

# Multiple related files (for coordinated transformations)
aider --file module.py --file tests/test_module.py -m "add feature with tests"
```

### 🎯 When to Use AIDER vs When to Avoid It

#### ✅ **EFFECTIVE - Use AIDER For:**
- **Python/JavaScript/TypeScript files** - Language model understands syntax well
- **Structured code changes** - Adding functions, classes, methods
- **Bug fixes with context** - Specific error messages and stack traces
- **Refactoring** - Following existing patterns in the codebase
- **Test creation** - Generating tests based on implementation
- **Documentation code** - Docstrings, type hints, code comments
- **Configuration files** - JSON, YAML, TOML with clear structure

#### ❌ **INEFFECTIVE - Avoid AIDER For:**
- **Plain text/prose** - Natural language writing, documentation prose
- **Markdown content** - Blog posts, README prose sections, tutorials
- **Creative writing** - User-facing content, marketing copy
- **Data files** - CSV, large JSON data, logs
- **Binary files** - Images, PDFs, compiled files
- **Complex manual formatting** - Tables, ASCII art, specific layouts
- **Exploratory analysis** - "What does this code do?" questions

#### 🤔 **DECISION RULE:**
```bash
# Ask: "Is this primarily about code structure/logic?"
# YES → Use AIDER
# NO → Use regular coding tools (Read, Edit, etc.)
```

### 🛠️ Essential Command Patterns

```bash
# Edit specific files
aider --file main.py --file utils.py -m "your request"

# Include read-only reference files for context
aider --file main.py --read conventions.md --read docs/api.md -m "your request"

# Target multiple related files
aider --file app.py --file models.py --file tests/test_app.py -m "your request"
```

**Key Options:**
- `--file FILE` - Files to edit (can be used multiple times)
- `--read FILE` - Read-only context files (can be used multiple times)  
- `--message "text"` or `-m "text"` - The coding request
- `--yes-always` - Auto-confirm (useful for automation)

### 🎯 Common Usage Patterns

```bash
# Single file changes
aider --file src/module.py -m "Add validation method to User class"

# Coordinated multi-file changes  
aider --file src/models.py --file tests/test_models.py -m "Add feature with tests"

# Context-aware development
aider --file new_feature.py --read existing_feature.py -m "Create new feature following existing patterns"

# Bug fixes with context
aider --file problematic_file.py --read error.log -m "Fix the timeout error"
```

### 🚨 Important AIDER Notes

**Automatic Git Commits:**
- AIDER automatically creates git commits with descriptive messages
- Each change is tracked and can be easily reverted
- No manual git operations needed

**File Management:**
- Respects `.gitignore` patterns automatically  
- Only modifies files explicitly specified with `--file`
- Use `--read` for large reference files to avoid editing them

## Testing Patterns

### Proper Unit Testing Guidelines
**Rule**: Use standard unit testing practices, avoid subprocess calls and external process dependencies.

```python
# ✅ GOOD: Direct unit testing
from mypackage import Component
component = Component()
result = component.method()
assert result == expected

# ✅ GOOD: Mock external dependencies
from unittest.mock import Mock
mock_external = Mock()
mock_external.method.return_value = "expected"

# ❌ BAD: Using subprocess.run() in tests
result = subprocess.run([sys.executable, "-c", "..."], capture_output=True)
```

**Key Guidelines:**
- Test your code, not external systems
- Use mocking for external dependencies
- Keep integration tests separate from unit tests
- Focus on the code you own and control

---

# Task Management Strategy

## Core Principle: Adaptive Documentation Based on Environment

**Primary Strategy**: Use GitHub Issues and PRs when available  
**Fallback Strategy**: Use local files when GitHub unavailable  
**Auto-Detection**: Choose appropriate method based on environment

### Environment Detection

Before starting any task, determine the optimal tracking approach:

```bash
# Check environment capabilities
git status && which gh && gh auth status
```

**✅ GitHub Available**: Git repo + GitHub CLI authenticated → Use GitHub Strategy  
**❌ GitHub Unavailable**: Missing git/gh/auth → Use File Strategy

## GitHub Strategy (Primary)

**Use when**: Git repository + GitHub CLI available and authenticated

### Task Documentation Hierarchy

1. **GitHub Issues** - Problem space (WHAT & WHY)
   - Requirements and acceptance criteria
   - Business objectives and scope
   - High-level progress tracking
   - Requirement changes and clarifications

2. **GitHub PRs** - Solution space (HOW) 
   - Technical implementation details
   - Architecture decisions and rationale
   - Detailed session progress
   - Code review and technical discussions

3. **Issue Comments** - Early development progress
   - Initial technical exploration (before PR)
   - Requirements clarification
   - Major blockers affecting scope

4. **PR Comments** - Implementation details
   - Code-specific discussions
   - Technical refinements
   - Architecture feedback

### Branch-Issue Linking

Always include issue numbers in branch names for session continuity:

```bash
# ✅ GOOD: Clear issue linking
feature/auth-system-issue-42
bugfix/timeout-error-issue-15
refactor/api-layer-issue-8

# ❌ BAD: No context for future sessions
feature/auth-system
bugfix/timeout-error
```

### GitHub Workflow

1. **Planning Phase**:
   ```bash
   # Create GitHub issue with detailed acceptance criteria
   gh issue create --title "Task Title" --body "..."
   # Note the issue number (e.g., #42)
   ```

2. **Development Phase**:
   ```bash
   # Create branch with issue number
   git checkout -b feature/description-issue-42
   
   # Create linking commit
   git commit --allow-empty -m "Start implementation of [task name]
   
   Related to #42: [GitHub issue title]
   
   See GitHub issue #42 for detailed acceptance criteria."
   ```

3. **Session Progress**:
   - Update issue comments with progress
   - Reference issue in commits: `git commit -m "Add auth models (#42)"`
   - Create PR when ready: "Related Issue: Closes #42"

4. **Session Discovery**:
   ```bash
   # Discover current context
   git branch --show-current    # Shows branch with issue number
   gh issue list --state open   # Shows active work
   gh issue view 42            # Shows detailed context
   ```

### Content Separation

**Issue Body (Problem Space)**:
- ✅ Acceptance criteria with checkboxes
- ✅ Business objectives and scope
- ✅ Dependencies and requirements
- ❌ Technical implementation details

**PR Description (Solution Space)**:
- ✅ Implementation approach and architecture
- ✅ Technical decisions and rationale  
- ✅ Detailed progress and session logs
- ✅ Explicit issue linking: "Related Issue: Closes #42"
- ❌ Business requirements or scope definition

## File Strategy (Fallback)

**Use when**: GitHub unavailable (no git repo, no gh CLI, or no auth)

### Local Documentation Structure

```
project/
├── docs/
│   ├── ARCHITECTURE.md      # Timeless: System design
│   ├── API.md              # Timeless: Interfaces
│   └── tasks/
│       └── {task-name}/    # Temporal: Task-specific
│           ├── PLAN.md     # Goals and approach
│           ├── PROGRESS.md # Session tracking
│           └── DECISIONS.md # Technical choices
```

### File-Based Workflow

1. **Planning Phase**:
   ```bash
   mkdir -p docs/tasks/auth-system
   echo "# Task Plan" > docs/tasks/auth-system/PLAN.md
   echo "# Progress Log" > docs/tasks/auth-system/PROGRESS.md
   ```

2. **Session Tracking**:
   - Update PROGRESS.md with session logs
   - Document decisions in DECISIONS.md
   - Reference files in commit messages

3. **Completion**:
   ```bash
   # Archive completed tasks
   mkdir -p docs/archive
   mv docs/tasks/auth-system docs/archive/
   ```

## Adaptive Implementation

### Environment-Aware Task Creation

```bash
# Universal task creation command
if git status && which gh && gh auth status >/dev/null 2>&1; then
    echo "✅ Using GitHub Strategy"
    gh issue create --title "..." --body "..."
else
    echo "📁 Using File Strategy"
    mkdir -p docs/tasks/task-name
    echo "# Task Plan" > docs/tasks/task-name/PLAN.md
fi
```

### Session Discovery Commands

**GitHub Strategy**:
```bash
git branch --show-current && gh issue list --state open
```

**File Strategy**:
```bash
find docs/tasks -name "PROGRESS.md" -exec echo "=== {} ===" \; -exec head -5 {} \;
```

## Benefits of Adaptive Approach

1. **Environment Flexibility** - Works in any development context
2. **Optimal Collaboration** - Uses GitHub when available for team coordination
3. **Fallback Reliability** - Always has a working documentation method
4. **Session Continuity** - Clear discovery patterns for both strategies
5. **Consistent Patterns** - Similar workflow regardless of tracking method

## Documentation Types

### Timeless Documents (Always Local)
**Location**: `/docs/` (root directory)
- **Architecture** - System design and patterns
- **API Documentation** - Public interfaces and usage  
- **Development Guidelines** - Code standards and practices
- **Core Concepts** - Fundamental ideas and philosophy

### Temporal Documents (Adaptive Location)
**GitHub Strategy**: Issues and PR descriptions  
**File Strategy**: `/docs/tasks/{task-name}/`
- **Task Plans** - Goals and implementation approach
- **Progress Tracking** - Session-by-session updates
- **Technical Decisions** - Implementation choices and rationale
- **Testing Approaches** - Task-specific validation strategies

---

# Quick Reference

## Core Workflow
1. **Observe & Understand** - Study existing patterns and context
2. **Transform & Validate** - Make small, structure-preserving changes
3. **Communicate & Evolve** - Make reasoning transparent, show examples

## AIDER Quick Commands
```bash
# Session check
which aider && aider --version

# Basic usage
aider --file path/to/file.py -m "specific request"

# With context
aider --file implementation.py --read specification.md -m "implement feature"

# Multiple files
aider --file module.py --file tests/test_module.py -m "add feature with tests"
```

## Decision Matrix
| Task Type | Use AIDER? | Alternative |
|-----------|------------|-------------|
| Code files (.py, .js, .ts) | ✅ Yes | - |
| Structured changes | ✅ Yes | - |
| Bug fixes with context | ✅ Yes | - |
| Markdown/prose | ❌ No | Edit tool |
| Data files | ❌ No | Edit tool |
| Exploratory analysis | ❌ No | Read tool |

## Development Principles Checklist
- [ ] Make changes in small steps (5-15 lines)
- [ ] Verify each change immediately
- [ ] Create permanent test files (no ad-hoc code)
- [ ] Follow existing patterns
- [ ] Use tools over manual processes
- [ ] Base decisions on data/analysis
- [ ] Document decisions and reasoning

---

*Last updated: 2025-06-27 | Version: 1.0*
