# server-reuse

Reuse an existing local development server before starting another instance.

The skill checks the expected port once, starts the project's dev script only when no server is running, and prevents fallback to an alternate port. It leaves the server running for future tasks.

See [SKILL.md](SKILL.md) for the instructions. This folder is a showcase copy; install it separately in your agent's skill directory to use it.
