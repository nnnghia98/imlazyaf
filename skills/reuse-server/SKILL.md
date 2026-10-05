---
name: reuse-server
description: Preserve user-managed servers and reuse known URLs or ports when developing or verifying a local app, preview, or watcher. Use when verifying UI changes, running e2e or HTTP checks, or when a dev server may already be running.
---

# Reuse Server

Prefer an existing user-managed server when its URL or port is known. Do not assume it is running; verify with a bounded, read-only check when needed.

## Ownership and authorization

- Do not start a development server, preview server, watcher, polling loop, or background daemon (including databases, containers, and tunnels) for a project unless the user explicitly asks.
- Do not stop, restart, kill, replace, or free a user-managed project process or port unless the user explicitly asks.
- Authorization already given in the current conversation remains valid. Do not ask again for the same action within its authorized scope.
- A process is assistant-created only if this session started it (under user authorization, or as a one-off build or test command) and you hold its session ID or verified process ID. Stop such processes when the task no longer needs them; this cleanup does not require another permission request.
- If process ownership is unclear, treat it as user-managed and leave it alone. Never use broad process-name kills.

## Reusing a server

- Infer the URL or port from the user's message, existing context, or project configuration (such as `package.json` scripts, framework config, or `.env`). Ask only when it cannot be inferred and is needed to continue.
- Reuse the existing URL or port for browser verification and HTTP checks.
- Do not create a second server on a nearby or alternate port when the expected server is unavailable. Inspect project configuration or logs already available first.
- If starting a server would help but has not been authorized, explain which server is needed and request the missing server state or authorization.

## Verification

- Allow bounded, one-off, read-only checks against a known URL or port, such as a curl request with a timeout or browser navigation.
- Avoid port scans, watch mode, repeated polling, and commands that stay attached to the server. Exception: after a user-authorized start, a bounded number of readiness retries is fine.
- If the existing server is not responding, report the failed check and ask the user to confirm its state or authorize a restart. Continue independent work where possible.
