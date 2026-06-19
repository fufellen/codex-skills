---
name: skill-authoring
description: Create, update, validate, self-improve, publish, and maintain user-owned Codex skills with the user's defaults. Use when Codex is asked to create a new skill, update an existing skill, scaffold SKILL.md/resources/agents metadata, add durable skill lessons, set up self-learning behavior, run skill validation, commit and push skill repository changes, or resolve skill repository merge conflicts.
---

# Skill Authoring

## Core Goal

Create and update Codex skills so the user does not need to repeat repository, self-learning, validation, push, and merge-conflict expectations. New user-owned skills should be born with the user's defaults already encoded.

## Required Loading

When this skill is used, also use:

- the system `skill-creator` for canonical skill anatomy, `init_skill.py`, `quick_validate.py`, and `agents/openai.yaml` rules;
- `skill-management` for the synced Google Drive skill root, GitHub mirror, corporate submodule rules, and publishing policy;
- `skill-learning` when a skill should remember durable lessons, reusable commands, preferences, failure modes, or validation checks.

Read `references/default-skill-pattern.md` before creating a new skill or adding self-improvement/publishing behavior to an existing skill.

## User Defaults

- Create user-owned skills under `C:\Users\User\Мой диск\Obsidian\.codex\skills` unless the user explicitly requests another location.
- Prefer the synced Google Drive skill copy over local bootstrap/system copies.
- Use the system `init_skill.py` for new skills; do not hand-roll the initial directory unless the generator is unavailable.
- Keep `SKILL.md` concise. Put growing guidance in `references/`, repeatable deterministic utilities in `scripts/`, and reusable templates/media in `assets/`.
- Add `agents/openai.yaml` with a clear display name, short description, and default prompt.
- Include a compact self-improvement and publishing section in every non-static user-owned skill.
- Validate changed skills when feasible, stage only relevant files, commit, and push by default unless the user explicitly says not to.

## Freshness Check

Before materially editing a user-owned skill, applying self-learning updates, or publishing changes:

1. Run `git fetch origin main` in the owning skills repository.
2. Compare local `HEAD` with `origin/main`.
3. If they match, continue.
4. If local `HEAD` is behind and the relevant working tree is clean, fast-forward with `git merge --ff-only origin/main`.
5. If the repository is dirty, ahead, or diverged, inspect the state before editing or publishing. Continue autonomously only when dirty changes are unrelated to the target skill and can be left unstaged, or when the intended integration can be determined safely.

## Creation Workflow

1. Choose a short lowercase hyphen-case skill name. Avoid names that collide with system skills; use a clearer personal wrapper name when needed.
2. Initialize the skill with `init_skill.py`, passing useful `--interface` metadata and only the resource folders the skill actually needs.
3. Replace the generated starter template with a concise domain workflow and strong frontmatter description.
4. Add the default self-improvement and publishing section from `references/default-skill-pattern.md`, adapting only the domain-specific lesson examples and protected-content list.
5. Add or update references/scripts/assets only when they remove real future repetition.
6. Validate the skill with `quick_validate.py`; test scripts that were added or changed.
7. Update `skill-management` when creating a durable user-owned skill so the synced skill inventory and routing stay current.
8. Commit and push the relevant skill files according to the publishing policy.

## Update Workflow

For existing skills, edit the synced source of truth, preserve user changes, and keep scope tight. If the update is a durable preference about how skills should be created or maintained, update this skill and `skill-management` instead of hiding the rule in a one-off domain skill.

## Merge Conflict Handling

Resolve skill repository merge conflicts autonomously when the intended final meaning can be determined from the conflicting files, nearby rules, commit history, and the user's current instruction. Preserve compatible behavior from both sides, keep confidentiality and repository hygiene rules, validate the result, commit, and push.

Stop and report only when resolving would require guessing unavailable technical meaning, choosing between incompatible user instructions, exposing protected content, discarding user work, or using unavailable repository permissions.
