# GitHub Copilot Configuration Generator Prompt

## Context
You are tasked with generating project configuration files to standardize and enhance GitHub Copilot code suggestions. These configurations will serve as intelligent guardrails for code generation.

## Required Output
Generate three types of configuration files:
1. `.github/copilot-instructions.md` - Global project standards
2. `.github/instructions/*.instructions.md` - Task-specific guidance files
3. `.github/prompts/*.prompt.md` - Reusable code generation templates

## File Requirements

### Global Project Instructions
File: `.github/copilot-instructions.md`
- Maximum 500 words
- Include: tech stack, coding standards, testing requirements
- Focus on actionable, project-specific guidelines
- Exclude: formatting instructions, external links
- Format as clear bullet points or numbered steps

### Task Instructions
Directory: `.github/instructions/`
- Include YAML front matter with `applyTo` patterns
- Create separate files for distinct development tasks
- Structure with clear headings and examples
- Focus on one specific task type per file
- Include validation criteria and testing requirements

### Prompt Templates
Directory: `.github/prompts/`
- Use `[VARIABLE_NAME]` for customizable elements
- Include input requirements and expected outputs
- Provide concrete code examples
- Specify file structure expectations
- List validation criteria

## Technical Requirements
- All files must use Markdown format
- Code examples must be in proper language-specific fenced blocks
- Front matter must be valid YAML
- File paths must match project structure
- Configuration must not conflict with existing tooling

## Validation Criteria
- Copilot suggestions match project standards
- Instructions are clear and actionable
- Examples follow current best practices
- Paths and patterns are valid
- Content is security-compliant

## Deliverables
1. Complete set of configuration files
2. All files properly formatted and organized
3. Examples that demonstrate proper usage
4. Clear validation steps for testing
5. Implementation guidelines for team adoption