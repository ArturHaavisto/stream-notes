# GitHub Copilot Instructions

## Project Maintenance & Specifications

- **Update spec.md**: Whenever you implement a feature, change the architecture, or modify the tech stack, you MUST review `spec.md` and update it to reflect the current state.
  - Update the "Status" column in feature tables (e.g., change "Planned" to "Implemented").
  - Add new utilized libraries to the Tech Stack tables.
  - Update the Project Structure tree if folders/files change significantly.
- **User Intent Updates**: If the user's prompt implies a change to the website plan, requirements, or features, update `spec.md` first to reflect these new requirements before implementation.

## Code Style & Standards

- **TypeScript**:
  - Use `interface` for object definitions and `type` for unions/intersections.
  - Avoid `any`; use `unknown` if necessary or create proper types.
  - Use strict type checking (no implicit any).
  - Prefer `async`/`await` over `.then()` chains.
- **React**:
  - Use functional components with hooks.
  - Prefer named exports for components (`export const Component = ...`).
  - Use strict definition for props interfaces.
  - Avoid large components; extract sub-components when logic grows.
- **Styling**:
  - Use Tailwind CSS utility classes.
  - Avoid creating custom CSS files unless necessary for complex animations or base styles not covered by Tailwind.
  - Use `clsx` or `tailwind-merge` for dynamic class names if strictly necessary (check if installed first).
- **Error Handling**: use `try/catch` blocks in async functions and ensure errors are logged or handled gracefully.

## Testing

- **Requirement**: Write unit tests for all new utilities and complex components.
- **Validation**: After modifying code, ALWAYS verify that existing tests pass and new tests cover the changes. If tests fail, fix them before finishing the task.
- **Frontend**: Use Jest and React Testing Library. Prefer `screen.getByRole` queries for accessibility testing.
- **Backend**: Use Jest and Supertest. Ensure database operations are mocked or use the in-memory server as configured.

## General Behavior

- **Conciseness**: Give short, direct answers. Avoid lengthy preambles.
- **Context**: formatting or path corrections should be self-contained (don't break existing code).
- **Security**: Never suggest committing secrets or API keys. Always use environment variables.
- **Dependencies**: when adding packages, ensure they are compatible with the current tech stack versions.

## Important Notes

- **Docs**: Keep logical documentation (like code comments) in sync with code changes.
- **Commits**: If asked to generate commit messages, use semantic commit convention (feat, fix, chore, docs).
