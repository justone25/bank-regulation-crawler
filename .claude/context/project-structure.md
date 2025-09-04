---
created: 2025-09-04T08:17:49Z
last_updated: 2025-09-04T08:17:49Z
version: 1.0
author: Claude Code PM System
---

# Project Structure

## Root Directory Organization

```
reg-assist/
├── .claude/                 # Claude Code PM system files
│   ├── context/            # Project context files
│   │   ├── README.md       # Context directory documentation
│   │   └── *.md           # Context documentation files
│   ├── scripts/            # Utility scripts
│   │   ├── pm/           # Project management scripts
│   │   └── test-and-log.sh # Test execution script
│   └── [other system dirs] # Agents, commands, epics, prds, rules
├── AGENTS.md              # Agent system documentation
├── CLAUDE.md              # Main Claude instructions
├── COMMANDS.md            # Complete command reference
├── LICENSE                # MIT License
├── README.md              # Main project documentation
└── screenshot.webp        # System screenshot
```

## Key Components

### Documentation Files
- **README.md** (491 lines) - Comprehensive system documentation
- **CLAUDE.md** - Instructions for Claude Code instances
- **AGENTS.md** - Specialized agent documentation
- **COMMANDS.md** - Complete command reference

### System Scripts
- **test-and-log.sh** - Test execution with logging
- **pm/*.sh** - Project management command scripts

## File Naming Patterns

### Documentation
- All documentation uses `.md` extension
- Filenames are lowercase with hyphens
- Main files use uppercase for emphasis (README, CLAUDE)

### Scripts
- Shell scripts use `.sh` extension
- Located in `.claude/scripts/` directory
- Organized by function (pm/, testing/)

## Directory Organization Principles

### Flat Structure
- Minimal nesting for easy navigation
- Clear separation of concerns
- Logical grouping of related files

### Accessibility
- Key files at root level
- Supporting files in subdirectories
- Clear naming conventions

## Installation Structure

When installed in target projects, the system creates:
```
[target-project]/
└── .claude/
    ├── CLAUDE.md          # Project instructions
    ├── agents/            # Task-oriented agents
    ├── commands/          # Command definitions
    ├── context/           # Project context
    ├── epics/             # Local workspace
    ├── prds/              # PRD files
    ├── rules/             # Project rules
    └── scripts/           # Utility scripts
```

## Key Design Decisions

### Template Repository
- Designed to be installed into other projects
- Contains documentation and templates only
- No build configuration or source code

### Documentation-First
- Comprehensive documentation for all features
- Clear examples and usage patterns
- Multiple entry points for different user needs