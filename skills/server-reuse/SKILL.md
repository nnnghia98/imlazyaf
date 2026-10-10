---
name: server-reuse
description: Use before running, starting, previewing, or browser-checking a local web app or dev server. Reuses the existing server instead of starting a duplicate on another port; starts one only if none is running.
---

# Server reuse

## 1. Find the expected port
User message → `package.json` dev script flags → framework config (`vite.config.*`, `next.config.*`, `.env` PORT) → framework default.

## 2. Check once before starting
`curl -sS -o /dev/null -w '%{http_code}' --max-time 3 http://localhost:<port>/`
- Any HTTP status (200, 404, 500…) → server is running. Reuse it. Do not start anything.
- Connection refused → nothing is running. Go to step 3.
- Timeout → something holds the port but is hung. Do not start or kill. Report it in your final message and continue other work.

## 3. Start only if nothing is running
- Run the project's own dev script in background mode, pinned to the expected port so a duplicate fails instead of drifting (`vite --strictPort`, `next dev -p <port>`).
- If output says `Port X is in use, trying Y` or `EADDRINUSE`: a server already exists. Stop the one you just started and use port X.
- Never start a second instance on an alternate port.
- Leave the server running after the task so it can be reused next time. Report the URL and terminal ID.

## Do not
- Kill, restart, or free a port held by a process you didn't start.
- Find processes by name or port to kill them.
- Poll background jobs (`sleep`, `ps`, `pgrep`, repeated `curl`/`lsof`). Do other work or end the reply; you'll be woken with output.
- Scan port ranges.
- Ask the user for confirmation or input about servers.
