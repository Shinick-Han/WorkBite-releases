# WorkBite

Work Stack organizes the work. StackBite gets it moving.

WorkBite combines Work Stack's task interface and native task authority with StackBite's agent rooms, deployment, terminal output and controls. This repository hosts downloadable binary releases; product source is maintained in a private repository.

## Install

Requires Node.js 20 or newer and Windows x64 or Linux x64 with glibc 2.28 or newer (including AlmaLinux 8). Python, Rust and Bun are bundled or compiled into the native suite.

```sh
npm install -g workbite@0.1.2
workbite install
```

Create and open a new workspace on Windows PowerShell:

```powershell
workbite open --workspace "$HOME\WorkBiteWorkspace" --init
```

On Linux:

```sh
workbite open --workspace "$HOME/WorkBiteWorkspace" --init
```

After this first setup, just run `workbite` to reopen the same workspace. Use `--workspace` to select another workspace; `--init` is only for creating one. WorkBite launches the Work Stack terminal interface with its execution dock connected to StackBite. Agents continue running when the interface closes.

Launcher 0.1.2 reuses the verified 0.1.0 native bundle; this update does not replace the running backends.

## Agents

`workbite agent status` identifies the current WorkBite workspace. The `workbite agent` commands read Task context, create Tasks, update detail/status and record checkpoints through the existing native owner. Writes require the explicit workspace path and UUID, a stable intent ID and, for updates, the current revision. They do not fall back to a separately installed Work Stack.

`workbite mcp` serves the same seven Task and context tools over standard MCP stdio. Register it with your agent's MCP client. Each server binds the selected WorkBite workspace at startup and keeps that binding until restarted.

The npm package includes the provider-neutral `skills/workbite-native/` skill. Copy that directory into your agent's supported skills directory. Existing agent sessions may need to reload their skills and MCP connections.

`workbite check` verifies the installed suite. Downloads and every installed file are checked against the release's pinned SHA-256 hashes.

WorkBite uses its own application and state folders, preserving separately installed Work Stack and StackBite. Version 0.1.0 creates new WorkBite workspaces; automatic migration of workspaces from another installation is not included. Agent deployment uses your existing provider CLI installation and login; it does not automatically approve folder trust.

## License

WorkBite's launcher and StackBite are proprietary. Work Stack retains its MIT license. Each binary bundle includes the component licenses and third-party notices in `licenses/` and `stackbite/licenses/`.
