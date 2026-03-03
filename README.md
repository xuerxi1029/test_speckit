# test_speckit

## Spec Kit (Specify CLI)

This workspace uses GitHub's Spec Kit via the `specify` CLI.

### Prereqs

- Python 3.11+ (this dev container has Python 3.12)
- `git`
- `uv` (Astral)

### Install

1) Install `uv` (if you don't already have it):

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
export PATH="$HOME/.local/bin:$PATH"
```

2) Install the `specify` CLI from Spec Kit:

```bash
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
```

3) Verify:

```bash
specify version
specify check
```

### Next step (optional)

Initialize Spec Kit templates in this repo:

```bash
specify init --here --ai copilot
```