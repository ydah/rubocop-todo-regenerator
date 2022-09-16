# rubocop-todo-regenerator

[Custom action](https://docs.github.com/en//actions/creating-actions/about-custom-actions) to regenerate `.rubocop_todo.yml` and create Pull Request.

## Usage

An example workflow to run rubocop-todo-regenerator via adding labels to pull requests.

```yaml
# .github/workflows/rubocop-todo-regenerator.yml
name: rubocop-todo-regenerator
on:
  pull_request:
    types: [labeled]
jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - uses: ydah/rubocop-todo-regenerator@main
        with:
          github_token: ${{ secrets.WRITABLE_GITHUB_TOKEN }}
```

## Inputs

### `github_token`

- GitHub access token to run another workflows from new pull request.
  - Don't forget to add `workflow` scope to this token
- optional

### `triggered_label`

- Specify the label to be triggered.
- default: `rubocop-todo-regenerate`
- optional

### `preparation_command`

- Specify the label to be triggered.
- default: `""` (empty string means no op)
- optional
