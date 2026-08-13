# pre-commit Hooks for LaTeX

`pre-commit-latex-hooks` is a set of [pre-commit](https://github.com/pre-commit/pre-commit) hooks that catch common LaTeX writing mistakes before they land in a commit — inconsistent spelling, missing `\label`s, broken `\cite` spacing, and more.

[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit) [![pre-commit.ci status](https://results.pre-commit.ci/badge/github/jonasbb/pre-commit-latex-hooks/master.svg)](https://results.pre-commit.ci/latest/github/jonasbb/pre-commit-latex-hooks/master)

- **Repository:** [github.com/jonasbb/pre-commit-latex-hooks](https://github.com/jonasbb/pre-commit-latex-hooks)
- **License:** Apache-2.0 OR MIT, at your option
- **Author:** [Jonas Bushart](https://www.bushart.org)

## Quick start

Add this to your project's `.pre-commit-config.yaml`:

```yaml
repos:
  - repo: https://github.com/jonasbb/pre-commit-latex-hooks
    rev: v1.4.0
    hooks:
      - id: american-eg-ie
      - id: cleveref-capitalization
      - id: consistent-spelling
        args:
            [
              "--emph=et al.",
              "--emph=a priori",
              "--emph=a posteriori",
              '--regex=naive=\bna(i|\"i)ve',
            ]
      - id: csquotes
      - id: ensure-labels-for-sections
      - id: no-space-in-cite
      - id: tilde-cite
      - id: unique-labels
      - id: cleveref-instead-of-autoref
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v3.3.0
    hooks:
      - id: check-merge-conflict
      - id: check-yaml
      - id: trailing-whitespace
        files: ".*\\.(?:tex|py)$"
```

Then run `pre-commit install` in your LaTeX project as usual. See the full list of available hooks and what each one checks in [Hooks reference](/hooks).

## Contributing

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the work is dual-licensed as above, without any additional terms or conditions.
