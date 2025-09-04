---
created: 2025-09-04T08:17:49Z
last_updated: 2025-09-04T08:17:49Z
version: 1.0
author: Claude Code PM System
---

# System Patterns

## Architectural Patterns

### Template Repository Pattern
The system follows a template repository pattern where:
- Core functionality is documentation-based
- Installation copies structure to target projects
- No compilation or build process required
- Self-contained and portable

### Command-Driven Architecture
All functionality exposed through commands:
- Slash commands for Claude Code interface
- Shell scripts for command line execution
- Consistent naming conventions
- Modular command structure

### Context Optimization Pattern
Designed to minimize context usage:
- Specialized agents for heavy lifting
- Concise summaries from verbose operations
- Hierarchical context management
- Isolation of implementation details

## Design Patterns

### Agent Pattern
Specialized sub-agents handle specific tasks:
- **code-analyzer** - Code analysis and bug detection
- **file-analyzer** - File summarization and insight extraction
- **test-runner** - Test execution and result analysis
- **parallel-worker** - Coordination of multiple work streams

### Workflow Pattern
Structured 5-phase development process:
1. **Product Planning** - PRD creation through brainstorming
2. **Implementation Planning** - Technical architecture and planning
3. **Task Decomposition** - Breaking work into actionable items
4. **Synchronization** - Pushing work to GitHub Issues
5. **Execution** - Parallel implementation with agents

### GitHub as Database Pattern
Using GitHub Issues as project database:
- Issues represent work items
- Comments provide audit trail
- Labels enable organization
- Parent-child relationships for hierarchy

## Data Flow Patterns

### Local-First Pattern
All operations work locally first:
- Fast local file operations
- Explicit synchronization with remote
- Offline capability for planning
- Conflict prevention through design

### Immutable Context Pattern
Context files are versioned and immutable:
- Timestamped creation
- Updates create new versions
- Clear audit trail
- Reproducible environments

## Integration Patterns

### Convention Over Configuration
- Standardized file structures
- Predictable naming conventions
- Default behaviors that work
- Minimal configuration required

### Extensibility Pattern
- Modular command system
- Pluggable agent architecture
- Customizable through rules
- Adaptable to different project types

## Anti-Patterns Avoided

### No Vibe Coding
- Every decision must be documented
- No assumptions or implicit requirements
- Full traceability from requirement to code
- Spec-driven development enforced

### No Context Pollution
- Implementation details stay in agents
- Main conversation remains strategic
- Verbose outputs captured and summarized
- Hierarchical context management

### No Serial Bottlenecks
- Parallel execution of independent tasks
- Multiple agents working simultaneously
- Non-blocking operations
- Efficient resource utilization

## Communication Patterns

### Asynchronous Updates
- Agents work independently
- Progress tracked locally
- Synchronization when ready
- No blocking communication

### Event-Driven Architecture
- Commands trigger actions
- Events update state
- Observers react to changes
- Loose coupling between components

## Error Handling Patterns

### Graceful Degradation
- Optional features fail silently
- Core functionality remains available
- Clear error messages
- Recovery paths provided

### Validation Before Action
- Pre-flight checks for all operations
- User confirmation for destructive actions
- Rollback capabilities
- State validation before changes