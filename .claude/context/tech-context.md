---
created: 2025-09-04T08:17:49Z
last_updated: 2025-09-04T08:17:49Z
version: 1.0
author: Claude Code PM System
---

# Technical Context

## Project Type

**Claude Code PM System** - A workflow and template repository for AI-assisted software development

### Nature
- Template/Documentation repository
- No traditional build process
- Shell script based installation
- Documentation-driven project

## Core Technologies

### Shell Scripts
- **Bash** - Primary scripting language for utilities
- **Installation script** - Single-command deployment
- **Utility scripts** - Test execution, project management

### Documentation
- **Markdown** - All documentation format
- **Mermaid** - Diagrams in README.md
- **YAML Frontmatter** - Context file metadata

### External Dependencies
- **GitHub CLI (gh)** - Required for GitHub integration
- **gh-sub-issue extension** - For parent-child issue relationships
- **curl/wget** - For installation script download

## Development Tools

### Version Control
- **Git** - Version control system
- **GitHub** - Remote repository platform
- **Issues API** - Project management database

### Command Line Tools
- Standard Unix/Linux/macOS command line tools
- No specialized development tools required
- Cross-platform compatibility (Unix-like systems)

## System Requirements

### For Installation
- Shell access (bash, zsh, etc.)
- Internet connection for initial download
- Write permissions in target directory

### For Operation
- GitHub CLI installed and authenticated
- Access to GitHub repository
- Standard Unix tools (find, grep, etc.)

## Architecture Patterns

### Script-Based Architecture
- Declarative documentation
- Imperative utilities
- Configuration through files
- Convention over configuration

### Integration Points
- GitHub Issues API
- Claude Code interface
- Standard shell environment
- Git workflows

## Security Considerations

### No Sensitive Data
- No API keys or tokens stored
- No user authentication required
- No personal data collection

### Safe Operations
- Read-only file operations by default
- User confirmation for destructive actions
- No system modifications outside project directory

## Performance Characteristics

### Lightweight
- Minimal resource requirements
- Fast installation and setup
- No background processes
- No runtime dependencies

### Scalable
- Works with projects of any size
- Parallel execution capability
- Context optimization prevents bloat