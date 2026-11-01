<div align="center">
  <h1 align="center">📜 <code>instructions</code></h1>

  <p align="center">
    <strong>The global instructions I give every coding agent</strong>
  </p>
</div>

These instructions set how my agents work in every project: how they write code, name things, handle bugs, verify results, and write to me. Each topic is one file in `.apm/instructions/<name>.instructions.md`.

The instructions name skills from [adelrodriguez/skills](https://github.com/adelrodriguez/skills), and installing this package installs those skills too.

## Contents

- [Install the instructions](#install-the-instructions)
- [Requirements](#requirements)
- [Where each agent reads them](#where-each-agent-reads-them)
- [License](#license)

## Install the instructions

Install the package at user scope with [APM](https://github.com/microsoft/apm), then compile the merged `AGENTS.md` files:

```sh
apm install --global adelrodriguez/instructions
apm compile --global
```

The install also adds the skills that the instructions name, and the skills those call: `codebase-design`, `issue`, `testing`, `unslop`, and `upload`.

Each file is plain Markdown with a `description` in its front matter, so you can also copy one into your agent's rules or `AGENTS.md` by hand.

## Requirements

- **APM.** The install commands run [APM](https://github.com/microsoft/apm). I use version 0.35.
- **The skills' requirements.** `issue` needs the GitHub CLI, and `upload` needs a public file bucket. See [Requirements](https://github.com/adelrodriguez/skills#requirements) in the skills repo.

## Where each agent reads them

| Agent | Instructions |
|---|---|
| Claude Code | `~/.claude/rules/<name>.md` |
| Codex | `~/.codex/AGENTS.md` |
| OpenCode | `~/.config/opencode/AGENTS.md` |
| Grok Build | `~/.grok/rules/` |

`apm compile --global` writes the `AGENTS.md` files. It merges every instruction into one file and drops their `applyTo` scoping, so every instruction applies everywhere in Codex and OpenCode.

## License

[MIT](LICENSE)
