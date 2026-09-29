# claude-plugins

Claude Code plugins of vulpes-facility.

## Install

```
claude plugin marketplace add vulpes-facility/claude-plugins
claude plugin install <plugin>@vulpes
```

## Plugins

| Plugin | What it does | Source |
| --- | --- | --- |
| `gh-shapeup` | Run Shape Up on GitHub Issues and Projects by asking Claude: pitches and bets, scopes on the hill, cooldown work and bugs, completion reports and audits. | [`vulpes-facility/gh-shapeup`](https://github.com/vulpes-facility/gh-shapeup), `plugins/gh-shapeup` |
| `vwiki` | Wiki mechanics for OKF knowledge bundles: the `vwiki` CLI, its ruleset, and five agent skills (init, seed, flush, validate, migrate). | The build of a private repository, in [`plugins/vwiki`](plugins/vwiki) |

## Adding a plugin

- A plugin of a public repository stays in that repository, next to the tool it drives, and this marketplace points at it with a `git-subdir` source.
  The tool's own tests keep the plugin in step with it, and users get it from the repository's default branch.
- A plugin whose source is private is published here as its build, since users without access to the private repository could not fetch it.
  The private repository builds the plugin, bundling, minifying or obfuscating its code, and its release puts the build
  under `plugins/<plugin>` with a relative source, or publishes it as an `archive` pinned with `sha256` or as an `npm` package when it is large.
  Only the build is published, never the source.
- A build hides code only from a casual reader: skills, agents and commands are prompts Claude reads, so they ship as they are,
  and bundled or compiled code can still be read back. Logic that must stay private runs on a server, behind a remote MCP server.
- The marketplace is named `vulpes`, the name of the catalog it replaces, `vulpes33/claude-plugins`, so that install ids such as `vwiki@vulpes` keep working.
  Names that look like Anthropic's own marketplaces, such as `claude-plugins-official`, are refused.

Run `claude plugin validate .` before a pull request.

## License

| Path | License | Notice |
| --- | --- | --- |
| [`plugins/vwiki`](plugins/vwiki) | [Apache-2.0](plugins/vwiki/LICENSE) | [`plugins/vwiki/NOTICE`](plugins/vwiki/NOTICE) |
| Everything else | [MIT](LICENSE) | [`NOTICE`](NOTICE) |
