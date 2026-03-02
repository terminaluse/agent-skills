# Interacting with an Agent

**Trigger**: User wants to test agent, run task, send message, interact with deployed agent.

**Full docs**: https://docs.terminaluse.com/introduction/using-agents.md

## Core Rule

Tasks require a filesystem.

## Steps

1. **Check for filesystems**
   ```bash
   tu fs ls
   ```
   If a suitable filesystem exists, confirm with the user and reuse it.

2. **Choose a project (or create one)**
   ```bash
   tu projects ls
   tu projects create --namespace <namespace> --name "<project-name>"
   ```

3. **Upload local files to filesystem (optional)**
   ```bash
   tu fs push <fs-id> <local-path>
   ```

4. **Create task:**
   ```bash
   tu tasks create --filesystem-id <fs-id> -m "message"   # With existing filesystem
   tu tasks create --project <project-id> -m "message"    # Auto-creates filesystem
   ```

5. **Follow-up messages:**
   ```bash
   tu tasks send <task-id> -m "message"
   ```

6. **Inspect task details (optional)**
   ```bash
   tu tasks ls <task-id>
   ```

7. **Download filesystem locally (optional)**
   ```bash
   tu fs pull <fs-id> <local-path>
   ```

Notes:
- `tu fs` is canonical. `tu filesystems` is an alias.
- There is no `tu tasks get`; use `tu tasks ls <task-id>`.
