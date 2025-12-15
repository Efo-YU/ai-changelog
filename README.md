# AI Auto-Changelog 🤖

Automated changelog generation using GitHub Actions and Google Gemini. On every push to `main`, this workflow analyzes the code changes and updates `CHANGELOG.md` with a structured summary and the raw diff.

## ✨ Features

- **AI Analysis**: Converts raw `git diff` into human-readable summaries using Gemini.
- **Structured Format**: Generates logs following Conventional Commits (type, scope, breaking changes).
- **Diff Tracking**: Appends the raw code changes in a collapsible `<details>` block for full traceability.
- **Smart Filtering**: Automatically hides binaries, heavy assets, and lockfiles from the log to keep it clean (configurable via `.logignore`).
- **Loop Prevention**: Automatically tags commits with `[skip ci]` to prevent infinite workflow loops.

## 🚀 Setup

### 1. Secrets Configuration

Go to **Settings > Secrets and variables > Actions** and add the following:

| Secret Name      | Value                                                                                |
| :--------------- | :----------------------------------------------------------------------------------- |
| `GEMINI_API_KEY` | Your API key from [Google AI Studio](https://aistudio.google.com/).                  |
| `GH_PAT`         | A **Fine-grained Personal Access Token** with `Contents: Read and write` permission. |

### 2. Workflow Installation

Add [the workflow file](.github/workflows/ai-changelog.yml) to your repository at `.github/workflows/ai-changelog.yml`.

### 3. (Optional) Custom Ignore Rules

To prevent large files (videos, images, lockfiles) from cluttering your changelog or consuming AI tokens, add a `.logignore` file to your root directory.

**Example `.logignore`:**

```text
# Lockfiles
package-lock.json
yarn.lock

# Assets
*.png
*.jpg
*.mp4
*.pdf
```

## ⚠️ Notes

- **Protected Branches**: Because the workflow commits directly to `main`, the `GH_PAT` is required to bypass standard branch protection rules (or you must allow the bot user).
- **Token Limits**: Diffs are intelligently filtered using `.logignore` and then truncated to \~25k chars to ensure reliability.

## 📝 Example Output (`CHANGELOG.md`)

## 2025-12-07 - feat: add infinite scroll

Implemented intersection observer to load items dynamically when scrolling to the bottom.

<details>
<summary>📄 Click to view raw diff</summary>

```diff
+ const observer = new IntersectionObserver((entries) => {
+   if (entries[0].isIntersecting) loadMore();
+ });

# -------------------------------------------------
# The following files were changed but content is hidden:
# (See .logignore for exclusion rules)
# -------------------------------------------------
M       src/assets/demo-video.mp4
M       package-lock.json
```

</details>
