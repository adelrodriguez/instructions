---
description: Use Boat sandboxes for builds, tests, untrusted code, Docker, and long jobs.
---

## Use Boat sandboxes

Run builds, tests, untrusted code, Docker, and long jobs in a Boat sandbox. Do not run those workloads on this computer.

Read the docs at https://docs.boat.dev/llms.txt. Get current prices and limits with `boat limits`.

- Create a sandbox with `id=$(boat new --ttl 3600 --json | jq -r 'select(.event == "ready") | .id')`.
- Copy a project with `boat push "$id" ./my-app`. The destination is `/home/user/my-app`. In a Git repository, ignored files are excluded.
- Run a command with `boat exec --cwd my-app "$id" -- npm test`. The default timeout is 30 seconds. Use `--timeout 0` for unlimited time.
- Run a one-shot job with `boat run --push . -- npm test`. It creates a sandbox, runs the command, reports its cost, and deletes the sandbox. It returns the command's exit code.
- Start a server with `boat exec --cwd my-app --detach "$id" -- npm run dev`. Check it with `boat exec --status <pid> "$id"`.
- Expose a port with `boat host "$id" 3000 --private`.
- Always pass the sandbox ID. The `current` alias needs interactive shell integration.
- Stop with `boat stop "$id"` to retain the disk for at least 14 days. Use `boat delete "$id" --yes` when the data is no longer needed.
