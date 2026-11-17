# adp-plugin-dima

Agent Discord Presence integration for dima (Dim Rust alpha). Reports session
activity, approval waits, failures, and completed replies. Native summaries use
dima's auxiliary-model service; custom models and OpenAI-compatible services are
also supported.

## Install

Requires an ADP build with external Agent plugins and GitHub installation support.

```sh
adp plugin install github:weiuou/adp-plugin-dima
```

Then run the `dima plugin install` command printed by ADP and reload or restart
dima. The package contains ready-to-run JavaScript and needs no build or npm
dependencies.

In the desktop client, open **Agents → Install from GitHub…** and enter
`github:weiuou/adp-plugin-dima`. Use **DimAgent → Setup → Manual configuration**
for the dima installation command and event options. ADP installation alone does
not load the plugin into dima.

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
