# adp-plugin-dima

Agent Discord Presence integration for dima (Dim Rust alpha). Reports session
activity, approval waits, failures, and completed replies. Native summaries use
dima's auxiliary-model service; custom models and OpenAI-compatible services are
also supported.

## Install

### npm

Use an ADP build that supports global npm plugin discovery.

```sh
npm install -g adp-plugin-dima
```

ADP discovers the globally installed package. To import it explicitly, open
**Agents → Install from GitHub or npm…** and enter `npm:adp-plugin-dima`.
To update, run `npm install -g adp-plugin-dima@latest`, refresh **Agents**, and
follow the dima setup steps below for the updated copy.

### GitHub

```sh
adp plugin install github:weiuou/adp-plugin-dima
```

In the desktop client, use the GitHub or npm installer and enter
`github:weiuou/adp-plugin-dima`.

### Set up dima

Run the `dima plugin install` command shown in **DimAgent → Setup → Manual
configuration** or printed by the ADP CLI, then reload or restart dima. The
package contains ready-to-run JavaScript and needs no build or npm dependencies.

The Agent ID remains `dimagent`, preserving existing settings. The installed copy
uses ADP's generated `.adp-runtime.json`; loading this checkout directly in dima
is unsupported. Reload dima after changing event options.

## Development

Point the tests at a built, plugin-capable ADP checkout:

```sh
npm run check
ADP_SOURCE_DIR=../agent-discord-presence npm test
```

Extracted from [weiuou/adp-plugins](https://github.com/weiuou/adp-plugins/tree/977172b4db8b7a3caf8f6d6664a42efd0a01566d/plugins/dima).
The original MIT license is retained.
