# MinVer Calculate

Uses the the [MinVer tool](https://github.com/codebeltnet/dotnet-tool-install-minver) to calculate the version of your projects that should rely on Codebelt methodology.

Aside outputting the calculated version, this action also provides a `MINVERVERSIONOVERRIDE` environment variable that can be used as part of your job.

This ensures a smooth and consistent way to setup your CI/CD pipeline as well as structuring your repository.

## Usage

To use this action in your GitHub repository, you can follow these steps:

```yaml
uses: codebeltnet/minver-calculate@main
```

### Inputs

```yaml
with:
  # Sets the verbosity level of the command.
  # Allowed values are e[rror], w[arn], i[nfo], d[ebug] and t[race]. 
  # The default is info.
  level: 'info'
```

### Outputs

```yaml
outputs:
  # The calculated version in SEMVER format.
  version: X.Y.Z # where X is MAJOR, Y is MINOR and Z is PATCH
```

Further information about the format can be found at [Semantic Versioning 2.0.0](https://semver.org/).

## Examples

### Calculate current version

```yaml
outputs:
  version: ${{ steps.minver-calculate.outputs.version }}

steps:
  - id: minver-calculate
  - name: Calculate Version
    uses: codebeltnet/minver-calculate@main
```

## Contributing to MinVer Calculate

Contributions are welcome! 
Feel free to submit issues, feature requests, or pull requests to help improve this action.

### License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
