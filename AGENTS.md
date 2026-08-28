# Repository Guidelines

- Keep each self-authored skill in a top-level directory with a `SKILL.md` file.
- Keep `README.md` synchronized when adding, removing, or renaming skills.
- List third-party skills in `README.md` with their upstream repository links; do not vendor them unless explicitly requested.
- Preserve existing skill content and structure unless the task explicitly asks for changes.

## Commit Messages

- Follow Conventional Commits: `type(scope): summary`.
- Use `feat`, `fix`, `docs`, `refactor`, `test`, or `chore` as the type.
- Use the skill name as the scope; use `repo` or `readme` for repository-wide changes.
- Keep the summary imperative, concise, and without a trailing period.

Examples:

- `feat(grill-me): add decision-focused questions`
- `docs(readme): list third-party skills`
- `chore(repo): add contribution guidelines`
