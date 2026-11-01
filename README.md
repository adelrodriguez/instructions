# instructions

My global instructions for coding agents, one file per domain in `.apm/instructions/<name>.instructions.md`. The package depends on [skills](https://github.com/adelrodriguez/skills), because the instructions name those skills, so installing it installs both.

[dotagents](https://github.com/adelrodriguez/dotagents) installs this package through [APM](https://github.com/microsoft/apm). Claude Code and Grok Build get one rule file per instruction. Codex and OpenCode get every instruction merged into one `AGENTS.md`, which drops `applyTo` scoping.

## Installing

```sh
apm install --global adelrodriguez/instructions
apm compile --global
```

`apm compile --global` writes the merged `AGENTS.md` for Codex and OpenCode.

## Updating

Push the change to `main`, then run `apm update --global` in `~/.apm` to install it.
