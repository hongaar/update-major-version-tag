# update-major-version-tag ![GitHub tag (latest SemVer)](https://img.shields.io/github/v/tag/hongaar/update-major-version-tag?label=latest%20version&sort=semver)

**This GitHub Action updates major version tags (e.g. v1, v2) when a tag is
pushed or release is created.**

For example, when a `v1.2.3` tag is pushed it updates the `v1` tag to support
the recommended
[GitHub Action versioning](https://docs.github.com/en/actions/creating-actions/about-custom-actions#using-tags-for-release-management)
release management strategy.

## Usage

### Prerequisites

Create a workflow `.yml` file in your `.github/workflows` directory. An
[example workflow](#example) is available below. For more information, reference
the GitHub Help Documentation for
[creating a workflow file](https://help.github.com/en/articles/configuring-a-workflow#creating-a-workflow-file).

## Example

```yml
# .github/workflows/update-major-version-tag.yml
name: update-major-version-tag

on:
  release:
    types: [published, edited]

jobs:
  update-major-version-tag:
    runs-on: ubuntu-latest
    steps:
      - uses: hongaar/update-major-version-tag@v1
```

## Credits

This is a fork of
[nowactions/update-majorver](https://github.com/nowactions/update-majorver) with
only a
[tiny change](https://github.com/hongaar/update-major-version-tag/commit/f772bc75ecf324c573ad680be17502d16354d00d)
in order to support the `release` trigger as well as the `push` trigger.

## Development

Install dependencies.

```bash
npm install
```

Run tests.

```bash
npm test
```

### Release

- Bump up the version in `package.json`
- Commit the changes
- Run `npm run release`
