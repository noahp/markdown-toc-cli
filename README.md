[![GitHub](https://img.shields.io/badge/GitHub-noahp/markdown--toc--cli-8da0cb?style=for-the-badge&logo=github)](https://github.com/noahp/markdown-toc-cli)
[![PyPI
version](https://img.shields.io/pypi/v/markdown-toc-cli.svg?style=for-the-badge&logo=PyPi&logoColor=white)](https://pypi.org/project/markdown-toc-cli/)
[![PyPI
pyversions](https://img.shields.io/pypi/pyversions/markdown-toc-cli.svg?style=for-the-badge&logo=python&logoColor=white&color=ff69b4)](https://pypi.python.org/pypi/markdown-toc-cli/)
[![GitHub Workflow Status](https://img.shields.io/github/workflow/status/noahp/markdown-toc-cli/main-ci/main?logo=github-actions&logoColor=white&style=for-the-badge)](https://github.com/noahp/markdown-toc-cli/actions)

<!-- markdown-toc-cli -->

- [markdown-toc-cli](#markdown-toc-cli)
  - [Installation](#installation)
  - [Usage](#usage)
    - [pre-commit Hook](#pre-commit-hook)

<!-- markdown-toc-cli-end -->

# markdown-toc-cli

Insert a table-of-contents into a Markdown file.

Heavily inspired from this project:
https://github.com/hukkin/mdformat-toc

I'd recommend using that _unless_ you don't want to run the built-in `mdformat`
formatting. Then this tool might be suitable for a standalone version.

(For example, `prettier` formats Markdown tables to be readable when not
rendered as HTML, where `mdformat` will sometimes reflow them into a difficult-to-read
packed representation).

To use `mdformat-toc` via `mdformat` in a pre-commit hook, see here:

https://mdformat.readthedocs.io/en/stable/users/installation_and_usage.html#usage-as-a-pre-commit-hook

And add `mdformat-toc` as an `additional_dependencies:` for `mdformat`.

## Installation

```bash
pip install markdown-toc-cli
```

## Usage

Add a comment like this to the Markdown file:

```markdown
<!-- markdown-toc-cli --prefix='- ' --indentation='  ' --minlevel=1 --maxlevel=6 -->
```

All arguments are optional, with the defaults values shown above (compatible
with GitHub flavored markdown).

Then run the tool:

```bash
markdown-toc-cli README.md
```

### pre-commit Hook

Example usage of this as a pre-commit hook:

```yaml
- repo: https://github.com/noahp/markdown-toc-cli
  rev: 0.1.1
  hooks:
    - id: markdown-toc-cli
```
