# Interacting with an Agent

**Trigger**: User wants to test agent, run task, send message, interact with deployed agent.

**Full docs**: https://docs.terminaluse.com/introduction/using-agents.md

## Core Rule

Tasks require a filesystem.

## Steps

1. **Check for filesystems (list them)**
   If exists → confirm use with user → skip to step 3

2. **Create project if needed or ask user which project to use**

3. **Ask user if they would like to upload local folder to the filesystem**

4. **Create task:**
   ```bash
   tu tasks create --filesystem <fs-id> -m "message"      # With filesystem
   tu tasks create --project <project-id> -m "message"    # Auto-creates filesystem
   ```

5. **Follow-up messages:**
   ```bash
   tu tasks send <task-id> -m "message"
   ```

6. **Ask user if they would like to download filesystem locally**