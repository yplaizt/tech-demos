# tech-demos

A sticky monorepo for small daily tech demos. Each weekday an assistant picks one new library or tool from the owner's X bookmarks. After approval, a cloud agent builds a single-user MVP under `apps/<kebab-slug>/`. Every demo stays in this repo.

## Layout

- `apps/<kebab-slug>/` — one self-contained demo. See [apps/README.md](apps/README.md).
- `skills/project-planning/SKILL.md` — planning skill every demo agent follows before coding.
- `AGENTS.md` — rules for demo agents (scope, Bun, shadcn/ui, one PR with a screenshot and a video).
- `tracking/seen-bookmarks.json` — bookmarks already proposed, approved, skipped, or built.

## Workflow

1. Pick a bookmark that is not already in `tracking/seen-bookmarks.json`.
2. Add it to `proposed`.
3. On approval, move it to `approved`. To pass on it, move it to `skipped`.
4. A cloud agent builds the approved demo under `apps/<kebab-slug>/` and opens one pull request in this repo.
5. When the demo lands, move the entry to `built`.

## Bookmark entries

Every item in `proposed`, `approved`, `skipped`, and `built` uses this shape:

```json
{ "id": "bookmark-id", "title": "Library or tool name", "url": "https://example.com", "date": "YYYY-MM-DD" }
```

- `id` — stable bookmark id
- `title` — short display name
- `url` — source link
- `date` — `YYYY-MM-DD` when the entry was recorded
