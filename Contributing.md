# 🤝 Contributing to Route Arc

First off, thank you for taking the time to contribute! 🎉
Route Arc is a self-hosted fleet-management & trip-booking system, and every improvement — whether a bug fix, feature, or doc tweak — helps make it better for everyone.

This guide explains how to get set up, our coding standards, and how to submit changes.

---

## 📋 Table of Contents

- #-code-of-conduct
- #-getting-started
- [Development Setup](#-development-setupte
- #-branching--commit-guidelines
- [Pull Request Processs
- #-coding-standards
- #-reporting-bugs
- [Suggesting Features](#-#-security

---

## 📜 Code of Conduct

Be respectful, constructive, and welcoming. Harassment, discrimination, or hostile behavior of any kind will not be tolerated. By participating, you agree to keep the community friendly and professional.

---

## 💡 How to Contribute

There are many ways to help:
- 🐛 **Fix a bug** — check the ../../issues tab for open reports.
- ✨ **Add a feature** — open a discussion/issue first so we can align on scope.
- 📚 **Improve docs** — READMEs, help-center pages, code comments.
- 🎨 **Polish UI/UX** — accessibility, dark-mode, responsiveness.
- 🧪 **Testing** — report edge cases or add test coverage.

---

## 🌿 Branching & Commit Guidelines

### Branch naming
Create a descriptive branch off `main`:
```bash
git checkout -b feature/route-eta-estimate
git checkout -b fix/driver-double-booking
git checkout -b docs/update-readme
```
Use prefixes: `feature/`, `fix/`, `docs/`, `refactor/`, `chore/`.

### Commit messages
Follow a clear, conventional style:
```
feat: add ETA estimate to route map
fix: prevent driver from accepting a second active trip
docs: clarify Docker setup steps
refactor: extract notification logic into shared service
```
Keep commits focused and atomic — one logical change per commit.

---

## 🔁 Pull Request Process

1. **Sync** your branch with the latest upstream `main`:
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```
2. **Test** your changes locally — confirm no PHP warnings/errors and that affected panels (Employee, Driver, Admin) still work.
3. **Push** to your fork and **open a Pull Request** against `main`.
4. In the PR description, include:
   - **What** changed and **why**.
   - **Screenshots / GIFs** for any UI changes.
   - **Related issue** number (e.g., `Closes #42`).
5. Be responsive to review feedback — small follow-up commits are welcome.

> ✅ PRs should be focused. Large, unrelated changes bundled together are harder to review and may be asked to split.

---

## 🐛 Reporting Bugs

Open an issue with:
- A clear, descriptive **title**.
- **Steps to reproduce**, expected vs. actual behavior.
- **Environment** (PHP version, DB, browser, OS/server).
- **Screenshots or logs** (redact any sensitive data).

---

## ✨ Suggesting Features

Open an issue labeled **enhancement** and describe:
- The **problem** you're trying to solve.
- Your **proposed solution** and any alternatives.
- Who benefits (which user role/tier).

Let's discuss and align before you invest time coding. 💬

---

## 🛡️ Security

If you discover a **security vulnerability**, please **do not** open a public issue. Instead, report it privately to the maintainer so it can be patched responsibly. Include steps to reproduce and potential impact.

---

## 📄 License

By contributing, you agree that your contributions will be licensed under the **MIT License** that covers this project.

---

<p align="center">Thanks for helping make Route Arc better! 🚗💨</p>