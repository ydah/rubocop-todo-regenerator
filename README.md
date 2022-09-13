# rubocop-todo-regenerator

[Custom action](https://docs.github.com/en//actions/creating-actions/about-custom-actions) to regenerate `.rubocop_todo.yml` and create Pull Request.

## Usage

An example workflow to run rubocop-todo-regenerator via adding labels to pull requests.

```yaml
# .github/workflows/rubocop-todo-regenerator.yml
name: rubocop-todo-regenerator
on:
  workflow_dispatch:
jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - uses: ydah/rubocop-todo-regenerator@v0
```

## Inputs

### `github_token`

- GitHub access token to run another workflows from new pull request.
  - Don't forget to add `workflow` scope to this token
- optional
