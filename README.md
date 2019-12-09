## action-update-file

Update (i.e. commit and push) a given file on GitHub.

## Usage

The action requires GitHub token; no username or e-mail are required.

```yml
name: Resources
on: repository_dispatch
jobs:
  resources:
    name: Update resources
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v1
    - uses: actions/setup-node@v1
    - name: Update resources
      uses: alexesprit/action-update-file@v0.1.0
      with:
        file-path: path/to/file
        commit-msg: Update resources
        github-token: ${{ secrets.GITHUB_TOKEN }}
```

## Inputs

### Required inputs

- `commit-msg`: a text used as a commit message
- `file-path`: a path to file to be updated
- `github-token`: GitHub token

### Optional inputs

- `branch`: branch to push changes (`master` by default)
- `allow-removing`: allow to remove file if local copy is missing
  (`false` by default)

Note that the action will produce an error iflocal copy is missing,
and the `allow-removing` flag is `false`.

## License

See the [license file][License].

[License]: https://github.com/alexesprit/action-update-file/blob/master/LICENSE.md
