# Agent rules

These rules apply to every agent that builds a demo in this repo.

## Scope

- Only add or modify files under `apps/<kebab-slug>/` for the demo you were asked to build.
- Edit `tracking/seen-bookmarks.json` only when explicitly told to. Otherwise leave it alone.
- Never touch other apps.

## Plan before code

Before coding, follow `skills/project-planning/SKILL.md` and write `apps/<slug>/PLAN.md` with:

- goal
- MVP and explicit outs
- task list
- stack, with a one-line rationale for each choice
- deferred items

## Each app is self-contained

There is no root workspace. From inside the app folder:

- Use Bun as the runtime and package manager.
- Ship the app's own `package.json`.
- Before any install, add a `bunfig.toml` with:

```toml
[install]
minimumReleaseAge = 259200
```

- `bun install && bun run dev` must work from inside the app folder.
- Start from an official `bunx create-*` scaffold.
- For UI, use shadcn/ui with a minimalist preset.

## README

Each app has a short README: what the tech is, a source link, and how to run it.

## Pull request

- Open exactly one PR per demo.
- The PR must include both at least one screenshot and at least one video (screen recording) of the running app as validation artifacts. This is not optional.
- Never create a new GitHub repository.
