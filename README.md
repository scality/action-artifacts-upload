This action upload files to artifacts web server

- Manage basic auth authentication
- Managed multiple files or directories as source
- Parallelize file upload

# Usage

## Inputs
- `artifacts-url` - Url to the artifacts server
- `source`  - A list of files ro directories  to publish on artifacts
- `username` - User set for basic Authentication
- `password` - Password set for basic Authentication

## Output
- `artifacts-name` - The name of the folder on artifacts where everything is stored
- `artifacts-link` - The direct link to this folder

## Basic:
```yaml
steps:
- uses: actions/checkout@master
- uses: scality/action-artifacts-upload
    with:
      artifacts-url: https://test.artifacts-url.com/path/to/artifacts
      source: './file1 ./file2 ./directory1
```

## With Basic auth:
```yaml
steps:
  - uses: actions/checkout@master
  - uses: scality/action-artifacts-upload
      with:
        artifacts-url: https://test.artifacts-url.com/path/to/artifacts
        source: ./file1 ./file2 ./directory1
        username: ${{ secrets.ARTIFACTS_USER }}
        password: ${{ secrets.ARTIFACTS_PASSWORD }}
```

# License

The scripts and documentation in this project are released under the [MIT License](LICENSE)