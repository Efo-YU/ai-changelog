# AI Auto-Changelog 🤖

Automated changelog generation using GitHub Actions and Google Gemini. On every push to `main`, this workflow analyzes the code changes and updates `CHANGELOG.md` with a structured summary and the raw diff.

## ✨ Features

- **AI Analysis**: Converts raw `git diff` into human-readable summaries using Gemini.
- **Structured Format**: Generates logs following Conventional Commits (type, scope, breaking changes).
- **Diff Tracking**: Appends the raw code changes in a collapsible `<details>` block for full traceability.
- **Loop Prevention**: Automatically tags commits with `[skip ci]` to prevent infinite workflow loops.

## 🚀 Setup

### 1. Secrets Configuration

Go to **Settings > Secrets and variables > Actions** and add the following:

| Secret Name      | Value                                                                                |
| :--------------- | :----------------------------------------------------------------------------------- |
| `GEMINI_API_KEY` | Your API key from [Google AI Studio](https://aistudio.google.com/).                  |
| `GH_PAT`         | A **Fine-grained Personal Access Token** with `Contents: Read and write` permission. |

### 2. Workflow Installation

Add the workflow file to your repository at `.github/workflows/ai-changelog.yml`.

## 📝 Example Output (`CHANGELOG.md`)

## 2025-12-07 - feat: add infinite scroll

Implemented intersection observer to load items dynamically when scrolling to the bottom.

<details>
<summary>📄 Click to view raw diff</summary>

```diff
+ const observer = new IntersectionObserver((entries) => {
+   if (entries[0].isIntersecting) loadMore();
+ });
```

</details>

## ⚠️ Notes

- **Protected Branches**: Because the workflow commits directly to `main`, the `GH_PAT` is required to bypass standard branch protection rules (or you must allow the bot user).
- **Token Limits**: Diffs sent to the AI are truncated to \~25k chars to ensure reliability, but the full diff is always saved to the log file.

<!-- end list -->
