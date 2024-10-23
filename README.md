# Overview

`setup-task` is a simple GitHub Action to setup [Taskfile](https://taskfile.dev/)
and add it to `$GITHUB_PATH` for the remainder of the Workflow job.

# Usage

Example:

```yaml
name: Demo

on: push

jobs:
  demo:
    name: Demo
    runs-on: ubuntu-latest
    steps:
      - name: Setup Task
        uses: illbjorn/setup-task@main
```

## Inputs

| Input          | Description                                                                  | Required | Default                                     |
| -------------- | ---------------------------------------------------------------------------- | -------- | ------------------------------------------- |
| `task_version` | If a specific release version of task is desired - provide its Git tag here. | `false`  | `v3.38.0`                                   |
| `bin_dir`      | The path to store the retrieved Task binary.                                 | `false`  | `${{ github.workspace }}/.local/share/task` |
| `token`        | The GitHub token for the `gh` CLI's usage.                                   | `false`  | `${{ github.token }}`                       |
