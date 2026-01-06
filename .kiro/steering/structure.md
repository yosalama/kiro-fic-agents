# Project Structure

## Directory Conventions

### Documentation & Notes

```
thoughts/
├── shared/           # Shared team documents
│   ├── plans/        # Implementation plans (YYYY-MM-DD-description.md)
│   ├── research/     # Research documents (YYYY-MM-DD_topic.md)
│   └── tickets/      # Ticket details (eng_XXXX.md)
├── [username]/       # User-specific notes
└── global/           # Global notes
```

### Plan File Naming

Implementation plans follow this pattern:
```
thoughts/shared/plans/YYYY-MM-DD-ENG-XXXX-description.md
```

Example: `thoughts/shared/plans/2024-01-15-ENG-1234-add-rate-limiting.md`

### Research Document Naming

Research documents follow this pattern:
```
thoughts/shared/research/YYYY-MM-DD_topic.md
```

Example: `thoughts/shared/research/2024-01-15_authentication-patterns.md`

## File Reference Format

When referencing code, use the format:
```
file_path:line_number
```

Example: `src/services/auth.ts:42`

For ranges:
```
src/services/auth.ts:42-56
```

## Success Criteria Format

Implementation plans should have two types of success criteria:

**Automated** (commands that can be run):
```markdown
- [ ] `make test` passes
- [ ] `make lint` passes
- [ ] `npm run typecheck` passes
```

**Manual** (human verification needed):
```markdown
- [ ] Login flow works with valid credentials
- [ ] Error message displays for invalid password
- [ ] Session persists after page refresh
```
