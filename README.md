# 🤖 Open DevHub Bot

**Open DevHub Bot** is a centralized GitHub automation bot built specifically for the **Open DevHub GitHub organization**.

It helps keep repositories clean, consistent, and welcoming by automating common workflows around **issues** and **pull requests**, while encouraging good contribution practices.

## ✨ Features

### Pull Requests

- 🏷️ Automatically adds labels based on **Conventional Commit types** found in PR commits  
  (e.g. `feat`, `fix`, `docs`, `refactor`, etc.)
- ✅ Creates a **custom check run** to report whether the PR follows Conventional Commits  
  (soft check — does not block merges)
- 💬 Posts a thank-you message when a PR is opened **if at least one commit follows conventions**
- 🎉 Posts a thank-you message when a PR is **merged**

### Issues

- 🐛 Automatically adds the `bug` label when an issue title contains the word **“bug”**
  (case-insensitive)

### General

- 🤖 Runs as a **branded GitHub App (DevHub Bot)** with a custom name and avatar
- 🔁 Fully **reusable** across repositories via GitHub Actions
- ⚙️ Centralized logic — update once, applies everywhere
- 🧩 Easy to extend with new DevHub-specific automations

## 🧩 How It Works

Open DevHub Bot is implemented as:

- a **GitHub App** (identity, permissions, avatar), and
- a **reusable GitHub Actions workflow** (automation logic)

Repositories within the Open DevHub organization “call” the bot using a reusable workflow ([reuse.yml](./reuse.yml)):

```yaml
name: DevHub Bot

on:
  pull_request:
    types: [opened, synchronize, closed]
  issues:
    types: [opened]

jobs:
  devhub-bot:
    uses: open-devhub/devhub-bot/.github/workflows/bot.yml@main
    secrets:
      DEVHUB_APP_ID: ${{ secrets.DEVHUB_APP_ID }}
      DEVHUB_APP_PRIVATE_KEY: ${{ secrets.DEVHUB_APP_PRIVATE_KEY }}
```

The bot reacts to GitHub events such as:

- `pull_request.opened`
- `pull_request.synchronize`
- `pull_request.closed (merged)`
- `issues.opened`

Based on defined rules, it applies labels, posts comments, and creates check runs —
all acting as DevHub Bot.

## 🤝 Contributing

Contributions are welcome, especially improvements to:

- automation rules
- labeling strategies
- event handling
- reliability and edge cases

When contributing:

- Keep changes scoped to DevHub use cases
- Follow existing workflow and job patterns
- Use clear, descriptive commit messages (Conventional Commits encouraged)

See [CONTRIBUTING.md](./CONTRIBUTING.md) for details.

### 🧠 Maintained by DevHub

Built and maintained by DevHub Community to support and streamline internal development workflows across the Open DevHub organization.
