# WorkBite

Work Stack organizes the work. StackBite gets it moving.

WorkBite combines Work Stack's task interface and native task authority with StackBite's agent rooms, deployment, terminal output and controls. This repository hosts downloadable binary releases; product source is maintained in a private repository.

## Install

Requires Node.js 20 or newer and Windows x64 or Linux x64 with glibc 2.28 or newer (including AlmaLinux 8). Python, Rust and Bun are bundled or compiled into the native suite.

```sh
npm install -g workbite@0.1.0
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

Reopen the same workspace without `--init`. WorkBite launches the Work Stack terminal interface with its execution dock connected to StackBite. Agents continue running when the interface closes.

`workbite check` verifies the installed suite. Downloads and every installed file are checked against the release's pinned SHA-256 hashes.

WorkBite uses its own application and state folders, preserving separately installed Work Stack and StackBite. Version 0.1.0 creates new WorkBite workspaces; automatic migration of workspaces from another installation is not included. Agent deployment uses your existing provider CLI installation and login; it does not automatically approve folder trust.

## License

WorkBite's launcher and StackBite are proprietary. Work Stack retains its MIT license. Each binary bundle includes the component licenses and third-party notices in `licenses/` and `stackbite/licenses/`.
