---
created: 2025-09-04T08:17:49Z
last_updated: 2025-09-04T08:17:49Z
version: 1.0
author: Claude Code PM System
---

# Project Style Guide

## Documentation Standards

### Markdown Conventions
- Use ATX-style headers (#, ##, ###)
- Maximum 80 characters per line
- Include frontmatter in all context files
- Use semantic line breaks (two spaces at end of line)
- Code blocks with language specification
- Tables for structured data presentation

### File Naming
- Lowercase with hyphens (kebab-case)
- Descriptive and concise names
- No spaces or special characters
- .md extension for all documentation
- Consistent naming across similar files

### Documentation Structure
- Clear hierarchy with headers
- Brief introductions for each section
- Examples for complex concepts
- Cross-references where helpful
- Summary or conclusion sections

## Code Style (for scripts)

### Shell Scripts
- Use bash for compatibility
- Shebang: `#!/bin/bash`
- Strict mode: `set -euo pipefail`
- Quote variables: `"${variable}"`
- Functions for reusable code
- Comments explaining non-obvious logic
- Error handling with clear messages

### Example Shell Script Pattern
```bash
#!/bin/bash

# Strict error handling
set -euo pipefail

# Configuration
readonly SCRIPT_DIR="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"
readonly PROJECT_ROOT="$(cd "${SCRIPT_DIR}/../.." && pwd)"

# Functions
log_info() {
    echo "[INFO] $*" >&2
}

log_error() {
    echo "[ERROR] $*" >&2
    exit 1
}

# Main logic
main() {
    # Validate inputs
    if [ $# -eq 0 ]; then
        log_error "Usage: $0 <argument>"
    fi
    
    # Process
    local input="$1"
    log_info "Processing: ${input}"
    
    # Output
    echo "Result: ${input}"
}

# Execute
main "$@"
```

## Command Design

### Slash Commands
- Use colon separator: `/category:action`
- Consistent naming patterns
- Clear, concise names
- Group related functionality
- Help text for all commands

### Command Categories
- `/pm:*` - Project management
- `/context:*` - Context management
- `/testing:*` - Testing operations
- `/utility:*` - General utilities

### Command Implementation
- Preflight checks before execution
- Clear error messages
- Progress indication
- Confirmation for destructive actions
- Summary of results

## File Organization

### Directory Structure
- Flat structure where possible
- Logical grouping of related files
- Clear separation of concerns
- Consistent depth levels

### File Placement
- Core files at root level
- Supporting files in subdirectories
- Temporary files in dedicated locations
- Generated files separate from source

## Naming Conventions

### Variables
- Lowercase with underscores
- Descriptive names
- Constants in UPPER_CASE
- Local variables lowercase
- Exported variables prefixed

### Functions
- Lowercase with underscores
- Verb-noun pattern
- Clear purpose
- Single responsibility

### Files
- kebab-case for files
- Descriptive prefixes
- Consistent suffixes
- No version numbers in names

## Git Workflow

### Commit Messages
- Imperative mood: "Add feature" not "Added feature"
- First line < 50 characters
- Body lines < 72 characters
- Explain why, not what
- Reference issues when applicable

### Branch Strategy
- Feature branches from main
- Descriptive branch names
- Regular merges
- Clean history

## Context Management

### Context Files
- YAML frontmatter with metadata
- Clear sections and subsections
- Concise but comprehensive
- Regular updates
- Version tracking

### Agent Communication
- Brief status updates
- Error details when needed
- Progress indicators
- Clear action items
- Minimal output to main thread

## Error Handling

### Principles
- Fail fast and clearly
- Provide recovery suggestions
- Log errors for debugging
- Don't continue on critical failures
- Graceful degradation for non-critical

### Error Messages
- What went wrong
- Why it happened
- How to fix
- Where to look for details

## Testing Approach

### Test Structure
- Separate test directory
- Clear test naming
- Setup and teardown
- Independent tests
- Comprehensive coverage

### Test Execution
- Log all output
- Clear pass/fail indication
- Detailed failure reports
- Performance metrics
- Environment isolation

## User Experience

### Command Line Interface
- Consistent options and flags
- Help text for all commands
- Progress indication
- Color coding where appropriate
- Clear success/failure feedback

### Documentation
- Examples for all features
- Common use cases
- Troubleshooting guide
- FAQ section
- Tutorial content

## Security Considerations

### Data Handling
- No sensitive data in logs
- Secure temporary files
- Clean up after operations
- Validate all inputs
- Use secure defaults

### Access Control
- Minimum required permissions
- No privilege escalation
- Clear authorization flows
- Audit trails for actions
- Secure by default

## Performance Guidelines

### Efficiency
- Minimize external calls
- Cache where appropriate
- Use efficient algorithms
- Avoid unnecessary work
- Profile and optimize

### Scalability
- Handle large projects
- Manage memory usage
- Parallelize where possible
- Avoid bottlenecks
- Monitor resource usage