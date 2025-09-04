# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the **Claude Code PM (Project Management)** system - a workflow tool designed to enhance AI-assisted software development. It uses GitHub Issues as a database and parallel AI agents for execution. The system provides a structured methodology for spec-driven development with full traceability from PRD to production.

## System Architecture

The PM system operates in 5 phases:
1. **Product Planning** - Create comprehensive PRDs through guided brainstorming
2. **Implementation Planning** - Transform PRDs into technical epics
3. **Task Decomposition** - Break epics into actionable tasks
4. **GitHub Synchronization** - Push work to GitHub Issues
5. **Parallel Execution** - Execute tasks using specialized agents

## Key Commands

### Project Management
- `/pm:init` - Initialize the PM system in a project
- `/pm:prd-new <feature>` - Create new Product Requirements Document
- `/pm:prd-parse <feature>` - Convert PRD to implementation epic
- `/pm:epic-oneshot <feature>` - Decompose epic and sync to GitHub
- `/pm:issue-start <number>` - Begin work on an issue with specialized agent
- `/pm:next` - Get next priority task
- `/pm:status` - Show project dashboard

### Context Management
- `/context:create` - Create initial project context documentation
- `/context:update` - Update context with recent changes
- `/context:prime` - Load context into current conversation

### Testing
- `/testing:prime` - Configure testing setup
- `/testing:run [target]` - Execute tests with analysis

## Agent System

The system uses specialized sub-agents for context optimization:

- **code-analyzer** - Hunt bugs across multiple files, return concise reports
- **file-analyzer** - Read and summarize verbose files (logs, outputs)
- **test-runner** - Execute tests without dumping output to main thread
- **parallel-worker** - Coordinate multiple parallel work streams

**Always use sub-agents when:**
- Reading files (especially logs or verbose outputs)
- Searching code or analyzing logic flows
- Running tests and analyzing results
- Executing parallel work streams

## Core Principles

### No Vibe Coding
Every line of code must trace back to a specification. Follow the 5-phase discipline:
1. Brainstorm deeper than comfortable
2. Write specs that leave nothing to interpretation
3. Architect with explicit technical decisions
4. Build exactly what was specified
5. Maintain transparent progress at every step

### Context Preservation
- Main conversation stays strategic
- Implementation details handled by agents
- Context never pollutes the main thread
- Work happens in parallel with clean separation

### Parallel Execution
- Single issues spawn multiple parallel work streams
- Agents coordinate through Git commits
- Context isolation prevents conflicts
- Main thread maintains oversight without drowning in details

## File Structure When Installed

```
.claude/
├── CLAUDE.md          # Instructions for Claude
├── agents/            # Task-oriented agents
├── commands/          # Command definitions
├── context/           # Project context files
├── epics/             # Local workspace (add to .gitignore)
├── prds/              # PRD files
├── rules/             # Rule files
└── scripts/           # Script files
```

## Development Workflow

1. **Create PRD**: `/pm:prd-new feature-name`
2. **Plan Implementation**: `/pm:prd-parse feature-name`
3. **Decompose Tasks**: `/pm:epic-oneshot feature-name`
4. **Execute Work**: `/pm:issue-start <issue-number>`
5. **Track Progress**: `/pm:status`

## GitHub Integration

- Uses GitHub Issues as the database
- Requires `gh` CLI and `gh-sub-issue` extension
- Epic issues track sub-task completion
- Comments provide audit trail
- Labels organize work (`epic:feature`, `task:feature`)

## Testing

The system includes a test logging script at `.claude/scripts/test-and-log.sh` for running tests with automatic log redirection. Use this pattern when implementing test execution in projects.

## Important Notes

- This is a workflow/template repository, not a traditional application
- Install into projects using: `curl -sSL https://raw.githubusercontent.com/automazeio/ccpm/main/ccpm.sh | bash`
- The system preserves context across sessions and enables parallel AI agent execution
- All work traces back to specifications for full auditability