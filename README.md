# Buildtools Buildkite Plugin 

A [Buildkite plugin](https://buildkite.com/docs/agent/v3/plugins) for running pipeline steps using [buildtools](https://buildtools.io/).

## Example

```yml
steps:
  - command: "build"
    plugins:
      - buildtool/buildtools:
```

If  you want to source environment variables from a file in S3
```yml
steps:
  - command: "build"
    plugins:
      - buildtool/buildtools:
          config: "s3://my-buildkite-secrets/configs/test"
```

## Configuration

### Required

### `command` (required, string)

The command to run.

Example: `build --version`

### Optional

### `config` (optional, string)

A configuration file to source located in S3, should set `env` variables to be used by buildtools like `BUILDTOOLS_CONTENT` and `KUBECONFIG_CONTENT_BASE64`

Example: `s3://my-buildkite-secrets/configs/test`

### Optional

### `version` (optional, string)

The version of buildtools to use, defaults to `latest`

Example: `0.0.27`