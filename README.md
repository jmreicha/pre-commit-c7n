# pre-commit-c7n

Add this to your [pre-commit](https://pre-commit.com/) `.pre-commit-config.yaml`
config.

You can use cloud custodian validate command flags to configure validation options. Add the required flags in the `args` field.

## Usage

### c7n-validate

Pre-commit requires the cloud custodian Python package to be installed (`pip install c7n`).

```yaml
repos:
-   repo: https://github.com/jmreicha/pre-commit-c7n.git
    rev: v0.1.0
    hooks:
    -   id: c7n-validate
        args:
          - --strict
          - --verbose
          - ./policies # last arg indicates the path/file to validate
```

### c7n-validate-docker

pre-commit will use the `cloudcustodian/c7n:0.9.38.0` docker image by default and run it inside a docker container.

```yaml
repos:
-   repo: https://github.com/jmreicha/pre-commit-c7n.git
    rev: v0.1.0
    hooks:
    -   id: c7n-validate-docker
        args:
          - --strict
          - --verbose
          - ./policies # last arg indicates the path/file to validate
```
