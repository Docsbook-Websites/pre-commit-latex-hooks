# Hooks reference

Each hook targets one specific, mechanical LaTeX mistake. Descriptions below are taken verbatim from the project's [`.pre-commit-hooks.yaml`](https://github.com/jonasbb/pre-commit-latex-hooks/blob/master/.pre-commit-hooks.yaml).

| Hook ID | What it checks |
|---|---|
| `american-eg-ie` | US English requires a comma after "e.g." and "i.e." |
| `cleveref-capitalization` | Ensures that `\Cref` at a sentence start is capitalized, and nowhere else in the sentence. |
| `consistent-spelling` | Ensures that all spelling variants (specified by regex) are written the same way throughout the document. |
| `csquotes` | Ensures the use of LaTeX `csquotes` and prohibits manual quotation marks. |
| `ensure-labels-for-sections` | Ensures each section has a matching `\label`. |
| `no-space-in-cite` | Ensures there are no whitespace characters inside a `\cite{...}` command. |
| `tilde-cite` | Each `\cite` needs a preceding `~` — line breaks should never occur right before a citation, so it must be protected with a non-breaking space. |
| `unique-labels` | Ensures each `\label` is only defined once. |
| `cleveref-instead-of-autoref` | Suggests replacing `\autoref` with `\Cref` or `\cref`. |

All hooks run against `.tex` files via `pygrep`, `python`, or `rust` entry points — see the [source](https://github.com/jonasbb/pre-commit-latex-hooks) for implementation details.

> Note: the repository's hook manifest also lists a `cispa-syssec-forbidden-words` hook (checks for "blacklist"/"whitelist"). It isn't part of the example configuration above — check the [source](https://github.com/jonasbb/pre-commit-latex-hooks/blob/master/.pre-commit-hooks.yaml) if you want to enable it too.

## Installation

```yaml
repos:
  - repo: https://github.com/jonasbb/pre-commit-latex-hooks
    rev: v1.4.0
    hooks:
      - id: american-eg-ie
      # ...add the hooks you want from the table above
```

Run `pre-commit install` afterwards so the hooks run on every commit.
