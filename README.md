# 🚀 Open a GitHub Issue

A simple custom GitHub Action to **create a new issue** in the current
repository.

![coverage](./badges/coverage.svg)  
Author: [Alexandru Marinescu](https://github.com/amscu-dev)

---

## 📝 Description

This action allows you to programmatically **open a new GitHub issue** with a
title, body, and optional assignees. It's useful in workflows where you'd like
to notify maintainers or log something automatically.

## 📦 Example Usage

```yaml
name: Create Issue Example
on:
  push:
    branches: [main]

jobs:
  create-issue:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Open a GitHub Issue
        uses: your-username/open-github-issue-action@v1
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
          title: 'Bug Report: Something went wrong'
          body: |
            This issue was automatically created by the workflow.
            Please investigate the logs.
          assignees: |
            octocat
            alexmarinescu
```

## 📥 Inputs (`action.yml`)

| Input       | Required | Description                                                              |
| ----------- | -------- | ------------------------------------------------------------------------ |
| `token`     | ✅ Yes   | GitHub Token used for authentication. Use `${{ secrets.GITHUB_TOKEN }}`. |
| `title`     | ✅ Yes   | The title of the issue to be created.                                    |
| `body`      | ❌ No    | The content/body of the issue.                                           |
| `assignees` | ❌ No    | GitHub usernames to assign the issue to (one per line).                  |
