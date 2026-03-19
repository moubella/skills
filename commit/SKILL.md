---
name: commit
description: Create a git commit with an emoji-prefixed, active-voice message based on staged changes. Use when the user asks to commit code or says /commit.
user_invocable: true
---

# Commit Message Skill

## Workflow

1. Run `git diff --cached` to see staged changes. If nothing is staged, run `git diff` and `git status` to see what could be staged, then ask the user what to stage.
2. Run `git log --oneline -10` to see recent commit style and patterns in this repo.
3. Based on the diff, pick the most appropriate emoji and write a commit message following the rules below.
4. Show the proposed message to the user for confirmation before committing.
5. Once confirmed, create the commit. Do NOT add a Co-Authored-By trailer or any other trailer to the commit message.
6. After a successful commit, push to the remote (using `git push`, or `git push -u origin <branch>` if no upstream is set).

## Format

```
<emoji> <Active-voice sentence, max 15 words>
```

## Rules

1. Start with a single emoji from the approved list below
2. First word after the emoji is a **verb in active voice**, with its **first letter capitalized**
3. The message is **one sentence**, max **15 words**
4. No period at the end
5. The message must accurately reflect the staged changes
6. Follow the tone and patterns of recent commits in the repo

## Emoji Guide

| Category | Emoji | When to use |
|---|---|---|
| Feature | ✨ | New feature or capability |
| Bug fix | 🐛 | Fix a bug |
| Critical fix | 🚑️ | Urgent hotfix |
| Docs | 📝 | Documentation changes |
| Performance | ⏱️ | Performance improvement |
| Config | ⚙️ | Settings/config file change |
| Refactor | ♻️ | Code restructuring without behavior change |
| Format | 🎨 | Code formatting, style (not refactoring) |
| Dependencies | 📦️ | Update/add/remove dependencies |
| Release | 🔖 | Release or version tag |
| Deploy | 🚚 | Deploy-related changes |
| Tests | 🧪 | Add or update tests |
| Build | 🔨 | Build system or tooling changes |
| Chore | 🔧 | Miscellaneous chores |
| Clean | 🧹 | Clean up code or files |
| Dead code | 🗑️ | Remove dead code |
| Security | 🔒 | Security fix or improvement |
| Revert | ⏪ | Revert a previous change |
| Merge | 🔀 | Merge branches |
| Database | 🗃️ | Database-related changes |
| WIP | 🚧 | Work in progress |
| Typo | ✏️ | Fix typo |
| Generate | 📄 | Auto-generated files |

## Examples

- `✨ Add user authentication via OAuth2 provider`
- `🐛 Fix null pointer crash when session token expires`
- `♻️ Extract payment logic into dedicated service module`
- `🧪 Add integration tests for order cancellation flow`
- `⏱️ Cache database queries to reduce API response time`
- `📝 Document the new webhook retry configuration options`
- `🎨 Reformat controller files to match project style guide`
- `📦️ Upgrade React to v19 and update peer dependencies`
- `⚙️ Update CI pipeline to run tests in parallel`
