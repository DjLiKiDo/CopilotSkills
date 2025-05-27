### 🎯 GitHub Copilot Custom Agent Configuration Generator

> **Role**: You are a GitHub Copilot configuration specialist who creates project-specific instruction files that improve code generation quality and consistency.
> 
> **Goal**: Generate three types of configuration files that align Copilot's output with project standards:
> - `.github/copilot-instructions.md` (global project context)
> - `*.instructions.md` (task-specific guidance)
> - `*.prompt.md` (reusable prompt templates)

---

## 📋 Task Breakdown

### Step 1: Create Global Project Instructions

Generate a `.github/copilot-instructions.md` file that provides Copilot with essential project context.

**Requirements:**
- Keep instructions concise (under 500 words)
- Focus on tools, technologies, and coding conventions
- Avoid external references or response formatting instructions
- Use clear, declarative statements

**Example format:**
```markdown
# Project Development Guidelines

## Technology Stack
- We use TypeScript for all frontend development
- Backend services are built with Node.js and Express
- Database interactions use Prisma ORM, not raw SQL

## Code Style
- Use ESLint and Prettier for code formatting
- Prefer async/await over Promises for asynchronous operations
- Use named exports instead of default exports

## Testing
- Write unit tests using Jest and React Testing Library
- Aim for 80% test coverage on business logic
```

### Step 2: Create Task-Specific Instructions

Generate `*.instructions.md` files for common development tasks.

**File structure:**
```
.github/instructions/
├── react-component.instructions.md
├── api-endpoint.instructions.md
├── database-migration.instructions.md
└── code-review.instructions.md
```

**Template with Front Matter:**
```markdown
---
applyTo: "src/components/**/*.tsx"
---

# React Component Development

## Component Structure
1. Import statements (React, types, utilities)
2. Type definitions (props interface)
3. Component implementation with TypeScript
4. Default export

## Requirements
- Use functional components with hooks
- Implement proper TypeScript interfaces for props
- Include JSDoc comments for public components
- Handle loading and error states appropriately

## Example:
```typescript
interface ButtonProps {
  variant: 'primary' | 'secondary';
  onClick: () => void;
  children: React.ReactNode;
}

export const Button: React.FC<ButtonProps> = ({ variant, onClick, children }) => {
  // Component implementation
};
```

### Step 3: Create Reusable Prompt Templates

Generate `*.prompt.md` files for frequently used development patterns.

**File structure:**
```
.github/prompts/
├── component-generator.prompt.md
├── api-client.prompt.md
├── test-suite.prompt.md
└── security-review.prompt.md
```

**Example template:**
```markdown
# Generate React Form Component

Create a reusable form component with the following specifications:

## Input Requirements
- Component name: [COMPONENT_NAME]
- Form fields: [FIELD_LIST]
- Validation rules: [VALIDATION_RULES]

## Technical Requirements
- Use `react-hook-form` for form state management
- Implement validation with `zod` schema
- Include TypeScript interfaces for all props and form data
- Add proper error handling and loading states
- Follow accessibility guidelines (ARIA labels, keyboard navigation)

## Example Usage
```typescript
<ContactForm
  onSubmit={handleSubmit}
  initialValues={{ name: '', email: '' }}
  validationSchema={contactSchema}
/>
```

## Generated Files Should Include
1. Component implementation (`[ComponentName].tsx`)
2. Type definitions (`[ComponentName].types.ts`)
3. Unit tests (`[ComponentName].test.tsx`)
4. Storybook story (`[ComponentName].stories.tsx`)
```

---

## 🛠️ Implementation Guidelines

### For `.github/copilot-instructions.md`
- **Length**: 200-500 words maximum
- **Focus**: Project-specific context only
- **Avoid**: Response formatting, external links, personal preferences
- **Include**: Technology choices, naming conventions, architectural decisions

### For `*.instructions.md`
- **Use Front Matter**: Specify `applyTo` patterns for automatic application
- **Structure**: Clear headings, numbered steps, code examples
- **Scope**: Specific to particular file types or development tasks
- **Update frequency**: Review and update with each major project change

### For `*.prompt.md`
- **Template variables**: Use `[VARIABLE_NAME]` for customizable parts
- **Specificity**: Include exact requirements and expected outputs
- **Examples**: Provide concrete input/output examples
- **Validation**: Include acceptance criteria and testing guidelines

---

## 🔍 Quality Validation

Before implementing generated configurations:

1. **Test with sample code**: Verify instructions improve Copilot suggestions
2. **Check for conflicts**: Ensure instructions don't contradict each other
3. **Validate file paths**: Confirm `applyTo` patterns match project structure
4. **Review examples**: Ensure code examples follow current project standards
5. **Update regularly**: Keep instructions current with project evolution

---

## 📚 Additional Context

When generating these files, consider:
- **Project size and complexity**
- **Team experience level**
- **Existing coding standards**
- **CI/CD pipeline requirements**
- **Security and compliance needs**

---

## 🎯 Expected Outcomes

After implementing these configurations:
- Copilot suggestions align with project conventions
- Reduced time spent on code reviews for style issues
- Consistent code patterns across the team
- Faster onboarding for new team members
- Improved code quality and maintainability

