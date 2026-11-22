# my-skills

My skill set for Claude Code. External skills are pulled in as git submodules;
my own skills live directly under `skills/`.

## Getting started

Clone with submodules:

    git clone --recurse-submodules https://github.com/versluisant/my-skills

If you already cloned without them:

    git submodule update --init --recursive

## Layout

- `skills/` — all skills, one folder per skill (`SKILL.md` inside)
- `.gitmodules` — list of external skills and where they come from
- `.github/workflows/check-upstream.yml` — weekly check for upstream changes;
  opens a PR when a submodule has moved

## Updating an external skill

Upstream changes arrive as a PR once a week. Review and merge, or:

    git submodule update --remote skills/<name>
    git commit -am "bump <name>"