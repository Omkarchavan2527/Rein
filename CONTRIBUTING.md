# Contributing to Rein

⭐ First off, thank you for considering contributing to Rein! ⭐

Hey there! Thanks for checking out **Rein** and considering contributing 🙌  
Whether you're fixing a bug, improving the UI, tweaking input handling, or suggesting a new idea — you're more than welcome here.

Please be respectful and constructive in discussions and reviews. Let's keep things friendly and helpful.

We welcome contributions from everyone. By participating in this project, you agree to abide by our Code of Conduct.

## 🔔 IMPORTANT: Discord Communication is Mandatory

**All project communication MUST happen on Discord. We do not pay attention to GitHub notifications.**

- Join our [Discord server](https://discord.gg/hjUhu33uAn) before starting any work
- Post your PR/issue updates in the relevant Discord channel (**MANDATORY**)
- All discussions, questions, and updates should be on Discord
- GitHub is for code only — Discord is for communication

**PRs without Discord updates will not be reviewed or may face delays.**

## 📋 Table of Contents
- [How Can I Contribute?](#-how-can-i-contribute)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [Development Workflow](#-development-workflow)
- [Testing](#-testing)
- [Testing Remote Control Features](#-testing-remote-control-features)
- [Pull Request Guidelines](#-pull-request-guidelines)
- [Code Style Guidelines](#-code-style-guidelines)
- [Community Guidelines](#-community-guidelines)
- [Issue Assignment](#-issue-assignment)

## 🤝 How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check existing issues to avoid duplicates. When creating a bug report:

- Use the **Bug Report** issue template
- Include a clear and descriptive title
- Steps to reproduce the issue
- Expected behavior vs actual behavior
- Screenshots/Video (if applicable)
- Environment details (OS, browser, versions, etc.)

### Suggesting Features

Feature suggestions are welcome! Please:

- Use the **Feature Request** issue template
- Check if the feature has already been suggested
- Provide a clear description of the feature and why it would be useful
- Include examples of how it would work

### Contributing Code

1. **Submit an Issue First**: For features, bugs, or enhancements, create an issue first
2. **Get Assigned**: Wait to be assigned before starting work (preferable)
3. **Submit Your PR**: Once assigned, create a PR addressing the issue
4. **Unrelated PRs**: Pull requests unrelated to issues may be closed or take longer to review

## 🚀 Getting Started

Rein is a **Node.js** project and works on **Windows, macOS, and Linux**.

### Prerequisites

- **Node.js** (latest LTS recommended)
- **npm**

### Setup

1. **Fork the Repository**
   - Click the "Fork" button at the top right of the [repository](https://github.com/imxade/rein)

2. **Clone Your Fork**
   ```bash
   git clone https://github.com/YOUR_USERNAME/rein.git
   cd rein
   ```

3. **Add Upstream Remote**
   ```bash
   git remote add upstream https://github.com/imxade/rein.git
   ```

4. **Install Dependencies**
   ```bash
   npm install
   ```

5. **Run the Project**
   ```bash
   npm run dev
   ```

   Open [http://localhost:3000](http://localhost:3000) in your browser. The dev server uses `--host --open`, so it may open automatically.

**Common commands:**

| Command           | Description                |
| ----------------- | -------------------------- |
| `npm run dev`     | Start development server   |
| `npm run build`   | Production build          |
| `npm run preview` | Preview production build  |
| `npm run test`    | Run tests                 |

The app runs on **port 3000** (configurable in `src/server-config.json`), used for both the frontend and WebSocket/input control.

## 📁 Project Structure

All app code lives under **`src/`**:

| Folder / File              | What it does                              |
| -------------------------- | ----------------------------------------- |
| `src/routes/`              | App routes and pages                      |
| `src/components/Trackpad/` | Trackpad, gestures, and input UI          |
| `src/hooks/`               | Custom React hooks                        |
| `src/server/`              | WebSocket server + input simulation logic |
| `src/utils/`               | Shared helpers and utilities              |
| config files (root)        | App, build, and tool configuration        |

Frontend UI, WebSocket communication, and desktop input handling are kept separate to make things easier to work on.

## 🔄 Development Workflow

### 1. Create a Feature Branch

Always work on a new branch, never on `main`:

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/your-bug-fix
```

### 2. Make Your Changes

- Write clean, readable code
- Follow the project's code style (see [Code Style Guidelines](#code-style-guidelines))
- Add comments where necessary
- Update documentation if needed

### 3. Test Your Changes

Run tests and Biome before committing:

```bash
npm run test
npx biome check --write .
```

### 4. Commit Your Changes

Write clear, concise commit messages using conventional commits:

```bash
git add .
git commit -m "feat: add user authentication"
# or
git commit -m "fix: resolve navigation bug"
```

**Commit message format:**

- `feat:` for new features
- `fix:` for bug fixes
- `docs:` for documentation changes
- `style:` for formatting changes
- `refactor:` for code refactoring
- `test:` for adding tests
- `chore:` for maintenance tasks

### 5. Keep Your Branch Updated

```bash
git fetch upstream
git rebase upstream/main
```

### 6. Push Your Changes

```bash
git push origin feature/your-feature-name
```

## 🧪 Testing

- Tests use **Vitest** and **React Testing Library**
- Run all tests: `npm run test`
- Adding tests for new features or bug fixes is encouraged 👍

## 📱 Testing Remote Control Features

To test Rein using a phone or tablet:

1. Allow incoming connections on **port 3000** on your computer.

   **Linux (UFW):**
   ```bash
   sudo ufw allow 3000/tcp
   ```

2. Ensure your phone and computer are on the **same Wi-Fi network**.

3. On your computer, open: [http://localhost:3000/settings](http://localhost:3000/settings)

4. Scan the QR code or manually open `http://<YOUR_PC_IP>:3000` (use `/trackpad` for the remote control screen).

## 📤 Pull Request Guidelines

- Target the default branch (`main`)
- Use a clear, descriptive PR title
- Explain **what** you changed and **why**
- Link related issues if applicable
- Keep PRs focused on one change
- Make sure all checks pass before requesting review

### Before Submitting

- [ ] Your code follows the project's style guidelines (Biome)
- [ ] You've run `npm run test` and `npx biome check --write .`
- [ ] You've updated relevant documentation
- [ ] Your commits are clean and follow the commit message format
- [ ] You've rebased with the latest upstream changes

### Submitting a Pull Request

1. Go to the [repository](https://github.com/imxade/rein) on GitHub
2. Click "New Pull Request"
3. Select your fork and branch
4. Fill out the PR description (see template below)
5. **Post your PR in the project's Discord channel** for visibility (**IMPORTANT**)

### PR Description Template

```markdown
## Description
Brief description of what this PR does

## Related Issue
Closes #issue_number

## Screenshots/Video (if applicable)
Add screenshots here

## Testing (if applicable)
Steps to test the changes

## Checklist
- [ ] Code follows style guidelines (Biome)
- [ ] Self-review completed
- [ ] Documentation updated
- [ ] Tests added/updated
```

### After Submission

- Post your PR in the project's Discord channel (**MANDATORY**)
- Respond to review comments promptly
- Make requested changes in new commits
- Be patient — maintainers will review when available

## 📝 Code Style Guidelines

Rein uses:

- **TypeScript**
- **TanStack Start**
- **Tailwind CSS** for styling
- **@nut-tree-fork/nut-js** for desktop input handling
- **Biome** for formatting and linting

Before opening a PR, run:

```bash
npx biome check --write .
```

### General Guidelines

- Use meaningful variable and function names
- Keep functions small and focused
- Add comments for complex logic
- Remove `console.log`s before committing
- Avoid code duplication

### TypeScript

- Use ES6+ syntax
- Prefer `const` over `let`, avoid `var`
- Use arrow functions where appropriate
- Follow Biome rules (see `biome.json`)

## 🌟 Community Guidelines

### Communication

- Be respectful and inclusive
- Provide constructive feedback
- Help others when you can
- Ask questions — no question is too small!

### Progress Updates

- If your work is taking longer than expected, post updates on Discord
- If you can no longer work on an issue, let maintainers know on Discord
- Tag maintainers on Discord if your PR is unattended for 1–2 weeks

### Getting Help

- Check existing documentation first
- Search closed issues for similar problems
- Ask in Discord
- Check the [Project Structure](#project-structure) section to find the right place in the codebase

## 🎯 Issue Assignment

- One contributor per issue (unless specified otherwise)
- Wait for assignment before starting work
- Issues may be reassigned if inactive for extended periods
- Check for existing PRs before starting to avoid duplication

---

Thanks for contributing to **Rein** 💙  
Your efforts help make this project better for everyone. If you find the project useful, don't forget to leave a ⭐ 🚀
