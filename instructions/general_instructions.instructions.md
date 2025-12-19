---
applyTo: '**'
---
# Global GitHub Copilot Instructions

These are my global preferences for Copilot suggestions. Repository-level instructions may override these.

## General
- Be concise and focus on idiomatic, secure, and testable code.
- Prefer readable variable and function names; avoid single-letter names except for loop indices.
- Provide a one-line summary for non-trivial code changes.

## Frontend (TypeScript)
- Assume project uses TypeScript with `strict` settings.
- Prefer React functional components with hooks.
- Use `PascalCase` for components and `camelCase` for functions/variables.
- Prefer named exports. Use `default` only for top-level apps when appropriate.
- Favor immutability and pure functions where possible.
- Provide small, focused examples and include types for public APIs.
- Suggest `eslint` rules compatible with `@typescript-eslint`.

## Backend (Python)
- Common frameworks: Django and FastAPI.
- Target Python 3.10+; use type annotations for public functions and methods.
- Follow PEP8 formatting and idiomatic Python code.
- For Django: prefer class-based views and ModelForms where suitable; use ORM queries safely (avoid raw SQL unless necessary).
- For FastAPI: use Pydantic models for request/response schemas and dependency injection for services.
- Include brief suggestions for unit tests (pytest) and mention where to place tests.

## Testing & Docs
- Prefer `pytest` for Python tests and `Jest` for TypeScript tests.
- When suggesting new functions or modules, include a short docstring or JSDoc comment.

## Documentation
- Prefer lightweight Markdown docs (`.md`) in a `docs/` folder for project-level documentation.
- For API schema documentation, prefer OpenAPI/Swagger (FastAPI auto-generates) or DRF/OpenAPI for Django.
- When adding or changing public APIs, suggest an example usage snippet and update `docs/` and changelog entries.
- For inline documentation: prefer clear docstrings (Python) and JSDoc comments (TypeScript) with parameter and return type descriptions.
- When generating longer explanations, keep sections short with clear headings and code examples.

### Mermaid diagrams
- Prefer Mermaid diagrams for simple architecture and flow visuals, embedded in Markdown files.
- Ensure diagrams are usable in both light and dark modes: choose colors with sufficient contrast in both themes or use CSS theme-aware variables when possible.
- Optimize diagrams for the VS Code Markdown preview by keeping them small and avoiding overly complex layouts; split very large diagrams into smaller focused diagrams.
- Include a short code block example showing how to specify theme-aware colors, and mention the recommended preview extension/settings if needed.
## When in Doubt
- Act ONLY based on the facts provided; avoid assumptions about project context.
- Ask clarifying questions before making large changes.
- If multiple valid approaches exist, prefer the safer, more maintainable option.
