````
"github.copilot.chat.commitMessageGeneration.instructions": [
  {
    "text": "Follow the Conventional Commits format strictly for commit messages. \n\n If there are multiple changes, use the structure below:\n\n```\n<type>[optional scope]: <description>\n\n[optional body]\n```\n\nGuidelines:\n\n1. **Type and Scope**: Choose an appropriate type (e.g., `feat`, `fix`, `docs`, `chore`, `style`, `test`, `ci`, `i18n`) and optional scope to describe the affected module or feature.\n\n2. **Description**: Write a concise, informative description in the header; use backticks if referencing code or specific terms.\n\n3. **Body**: For additional details, use a well-structured body section:\n   - Use bullet points (`*`) for clarity.\n  - Clearly describe the motivation, context, or technical details behind the change, if applicable.\n\n **NOTES**:\n\n - If there is only one change, you don't need to include the 'body' section.\n\n - Commit messages should be Friendly, clean, SIMPLE, informative, and professional, aiding readability and project tracking.\n\n - Avoid using LLM giveaway phrases (e.g.,`streamlined`,... ), instead use more simple meaning of those words."
  }
],
````
