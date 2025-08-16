# Cursor Rules Organization

This directory contains organized rule files that guide the AI assistant's behavior for different aspects of the project.

## Rule Files Overview

### Critical Priority Rules (Always Applied)
- **`test-quality-requirements.mdc`** - All tests must pass without exception
- **`tests-location.mdc`** - Behavior-driven testing standards and file organization
- **`no-emojis.mdc`** - Prohibits emoji usage throughout the project
- **`incremental-collaboration.mdc`** - Prevents reversing established work during sessions
- **`security-privacy.mdc`** - Security and data privacy protection standards

### High Priority Rules
- **`oop-solid.mdc`** - Object-oriented programming and SOLID principles with mandatory checkpoints
- **`performance-optimization.mdc`** - Performance standards for resource-intensive operations
- **`configuration-management.mdc`** - Centralized and validated configuration management
- **`error-handling-logging.mdc`** - Comprehensive error handling and structured logging
- **`data-validation.mdc`** - Input validation and schema compliance standards
- **`windows-shell.mdc`** - Windows PowerShell command guidelines and restrictions

### Medium Priority Rules  
- **`test-coverage-standards.mdc`** - 80% minimum test coverage per module requirement
- **`dead-code-detection.mdc`** - Systematic identification and safe removal of unused code
- **`documentation-standards.mdc`** - Comprehensive documentation and code comment standards
- **`dependency-management.mdc`** - Secure and maintainable dependency handling
- **`monitoring-observability.mdc`** - System monitoring and performance tracking
- **`documentation-updates.mdc`** - Documentation maintenance requirements
- **`git-commit-guidance.mdc`** - Version control best practices

## Rule Targeting Strategy

### File Pattern Targeting
- **Python Code**: Multiple rules apply to `claude_word_qa/**/*.py`:
  - `oop-solid.mdc`, `dead-code-detection.mdc`, `security-privacy.mdc`
  - `performance-optimization.mdc`, `error-handling-logging.mdc`
  - `data-validation.mdc`, `monitoring-observability.mdc`
- **Configuration Files**: `configuration-management.mdc` applies to `*.toml`, `*.yaml`, `*.json`
- **Documentation**: `documentation-standards.mdc` applies to `**/*.md` and Python files
- **Dependencies**: `dependency-management.mdc` applies to `pyproject.toml` and `requirements*.txt`
- **Test Files**: Multiple rules apply to `tests/**/*.py` and `**/*test*.py`:
  - `test-quality-requirements.mdc`, `test-coverage-standards.mdc`, `tests-location.mdc`
- **All Files**: `git-commit-guidance.mdc` and `windows-shell.mdc` apply globally

### Priority Levels
- **Critical**: Core project standards that must never be violated
- **High**: Important architectural and platform-specific requirements  
- **Medium**: Best practices that improve code quality and maintainability

## Frontmatter Configuration

Each rule file uses YAML frontmatter to specify:

```yaml
---
appliesTo: ["file/pattern/**/*.ext"]  # File targeting
alwaysApply: true                     # Apply regardless of context
priority: critical|high|medium        # Rule importance
context: ["terminal", "commands"]     # Context-specific application
---
```

## Rule Effectiveness

This multi-file approach provides:

1. **Contextual Relevance** - Rules apply only where appropriate
2. **Reduced Token Usage** - Only relevant rules are loaded
3. **Better Organization** - Clear separation of concerns
4. **Team Collaboration** - Parallel development without conflicts
5. **Maintainability** - Easy to update specific rule categories

## Adding New Rules

When adding new rules:

1. Create a descriptive filename: `feature-specific-rules.mdc`
2. Add appropriate frontmatter for targeting and priority
3. Use clear, actionable language
4. Include examples of correct and incorrect usage
5. Update this README to document the new rule

## Rule Interaction

Rules are processed based on:
- **Priority**: Critical > High > Medium
- **Context**: More specific rules take precedence
- **File Matching**: Rules only apply to targeted file patterns

This ensures consistent, efficient, and contextually appropriate AI assistance throughout the project.
