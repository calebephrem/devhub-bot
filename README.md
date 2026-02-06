# 🤖 Open DevHub Bot

Open DevHub Bot is a GitHub automation bot built for the **DevHub GitHub organization**.

It helps keep repositories clean, consistent, and welcoming by automating
common workflow tasks around issues and pull requests.

## ✨ Features

- 🏷️ Automatically adds labels when issues are opened
- 🏷️ Automatically labels pull requests based on rules
- 🎉 Posts a thank-you message when pull requests are merged or closed
- 📋 Encourages consistent contribution workflows
- ⚙️ Easy to extend with new DevHub-specific automations

## 🧩 How It Works

Open DevHub Bot listens to GitHub webhook events such as:

- `issues.opened`
- `pull_request.opened`
- `pull_request.closed`

Based on configurable rules, it applies labels, posts comments,
or triggers other automation actions.

The bot is designed to run as a **GitHub App or bot service**
connected to DevHub repositories.

## 🤝 Contributing

Contributions are welcome, especially improvements to:

- automation rules
- label strategies
- event handling
- reliability and performance

If you’re contributing:

- keep changes scoped to DevHub use cases
- follow existing patterns
- write clear commit messages

See [`CONTRIBUTING`](./CONTRIBUTING.md) for more info

## 📜 License

This project uses MIT License.
See the [`LICENSE`](./LICENSE) file for details.

## 🧠 Maintained by DevHub

Built and maintained by **DevHub** to support internal development workflows
