# Chrome Browser Automation

> Controls a real Chrome browser from an AI agent — navigate, click, fill forms, screenshot, read page content, capture network traffic, manage bookmarks/history/tabs.

The bundle is large (**121.7 MB**), above GitHub's git limit, so it is published as a **GitHub Release asset** — download it from the latest [Release](../../releases).

This repository is part of the **Forjinn-Desk** MCP bundle collection. An MCP bundle is a self-contained server that a host application launches and communicates with over the MCP (Model Context Protocol) protocol.

## Repo metadata

| Field | Value |
| --- | --- |
| Registry ID | `dc035ead-b102-4975-8f93-e2115f2a42db` |
| Status in registry | inactive |
| Bundle size | 121.7 MB |
| Distribution | GitHub Release asset |

## Environment variables

| Variable | Value / note |
| --- | --- |
| _(none)_ | _no required environment variables_ |

## MCP launch configuration

The host replaces `__INSTALL_DIR__` (install dir) and `__PYTHON__` (bundled Python) at runtime.

```json
{
  "command": "__INSTALL_DIR__\\node.exe",
  "args": [
    "__INSTALL_DIR__\\node_modules\\mcp-chrome-bridge\\dist\\mcp\\mcp-server-stdio.js"
  ]
}
```

## Setup / usage notes

REQUIRES A ONE-TIME MANUAL SETUP before it works: (1) Open chrome://extensions, enable Developer mode, click 'Load unpacked', and select the bundle's chrome-extension folder. (2) Run register.bat once from the install folder — this registers the native-messaging bridge Chrome uses to talk to this MCP server. Both steps happen once per machine. After that, it runs entirely locally (extension <-> local bridge <-> this MCP server) with no cloud calls.


## Install / usage

1. Get the bundle:
   - download the latest release asset from the Releases tab.
2. Extract to your target installation directory (config paths expect contents at the install-dir root).
3. Set the environment variables listed above.
4. Launch using the MCP config JSON (or let a host client manage it automatically).

> Bundles may include vendored runtimes (bundled Python, Node, or native executables). Builds are Windows x64.
