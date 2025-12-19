---
applyTo: '**.md'
---

# Document Generation GitHub Copilot Instructions

This document provides specific instructions and best practices for GitHub Copilot to follow when generating project documentation and Mermaid diagrams. It outlines the preferred formats, structures, styles, and theming configurations to ensure consistency and high-quality output across the repository.

## General
- **Tone**: Professional, objective, and concise. Avoid first-person narrative ("I", "we") unless referring to the team/organization in a specific context.
- **Audience**: Assume the audience is technical (developers, data scientists).
- **Formatting**: Use standard Markdown. Ensure headers are properly nested. Use code blocks for all code, commands, and file content.
- **Links**: Use relative paths for internal links to ensure they work in the repository view.
- **Context**: When referencing files or components, verify their existence in the workspace to ensure accuracy.


## Documentation
- **Format**: Use Markdown (`.md`) for all documentation. Place project-level docs in `docs/`.
- **Structure**:
    - **Title**: Clear and descriptive.
    - **Overview**: 1-2 sentences explaining the purpose.
    - **Prerequisites**: What is needed before starting (if applicable).
    - **Usage/Steps**: Numbered lists for procedures.
    - **Examples**: Provide clear code snippets or command examples.
- **Style**:
    - Be concise and direct. Use active voice.
    - Use **bold** for UI elements or key terms.
    - Use `code ticks` for file paths, variables, and commands.
- **API Docs**:
    - For Python: Use Google-style docstrings.
    - For TypeScript: Use JSDoc.
    - For HTTP APIs: Prefer OpenAPI/Swagger.
- **Maintenance**:
    - When modifying code, always check if `README.md` or `docs/` need updates.
    - Keep the `CHANGELOG.md` updated with significant changes.

### Mermaid Diagrams

- **Diagram Types**: Use `flowchart` (or `graph`) for process flows, `sequenceDiagram` for interactions, `classDiagram` for object modeling, `stateDiagram-v2` for state machines, and `erDiagram` for database schemas. For high-level system architecture, consider `C4Context` or `architecture` (if supported) diagrams.

- **Theming & Accessibility**:
    - **Standard Theme**: Use the `neutral` theme by default. It provides the best accessibility and readability across different environments (light/dark mode, printed PDFs).
    
    - **Theme Variants**:
        - **Default (Neutral)**: Use for most documentation.
          ```mermaid
          %%{init: {'theme':'neutral'}}%%
          flowchart LR
              A[Start] --> B[Process]
              B --> C[End]
          ```
        
        - **Brand/Architecture**: Use for high-level system diagrams where branding is important.
          ```mermaid
          %%{init: {'theme':'base', 'themeVariables': {'primaryColor':'#007ACC','primaryTextColor':'#ffffff','primaryBorderColor':'#005A9E','lineColor':'#005A9E','secondaryColor':'#E6F2F9','tertiaryColor':'#ffffff'}}}%%
          flowchart LR
              A[User Service] --> B[Data Service]
              B --> C[Storage]
          ```
        
        - **Critical/Warning**: Use for error handling flows or critical alerts.
          ```mermaid
          %%{init: {'theme':'base', 'themeVariables': {'primaryColor':'#D32F2F','primaryTextColor':'#ffffff','primaryBorderColor':'#B71C1C','lineColor':'#D32F2F','secondaryColor':'#FFEBEE','tertiaryColor':'#ffffff'}}}%%
          flowchart LR
              A[Error Detected] --> B[Log Error]
              B --> C[Notify User]
          ```
    
    - **Accessibility Rules**:
        - **Color Contrast**: Ensure text-to-background contrast meets WCAG AA standards (minimum 4.5:1 for normal text, 3:1 for large text).
        - **Light/Dark Mode**: Test diagrams in both modes. The `neutral` theme adapts automatically; custom themes should specify sufficient contrast in `primaryTextColor` and background colors.
        - **Color Independence**: Do not rely solely on color to convey meaning. Use:
            - **Text labels** on all nodes and edges (e.g., `A[Database]` instead of just `A`)
            - **Different shapes** to distinguish node types (e.g., `()` for circles, `[]` for rectangles, `{}` for diamonds)
            - **Patterns or icons** where supported
        - **Font Size**: Keep default font sizes for readability. Avoid overly complex diagrams that force small text.
        - **Testing**: Preview diagrams in VS Code with both light and dark themes enabled before committing.

- **Best Practices**:
    - Use **subgraphs** to group related components in flowcharts.
    - Keep diagrams simple and focused. Split complex diagrams into multiple smaller ones.
    - Use meaningful node IDs (e.g., `UserService` instead of `A`) to make the code readable.
    - Add labels to links to clarify relationships (e.g., `A -->|Requests| B`).
    - For sequence diagrams, use `autonumber` to automatically number messages.
    - Include a brief text description or caption before each diagram explaining its purpose.

## When in Doubt
- Ask clarifying questions before making large changes.
- If multiple valid approaches exist, prefer the safer, more maintainable option.
