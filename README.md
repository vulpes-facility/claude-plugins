# claude-plugins

Claude Code plugins for the tools of vulpes-facility.

## Install

```
claude plugin marketplace add vulpes-facility/claude-plugins
claude plugin install <plugin>@vulpes-facility
```

## Plugins

| Plugin | What it does | Source |
| --- | --- | --- |
| `gh-railyard` | Set up and change gh-railyard's Apps, agents and rails by asking Claude, instead of typing the CLI. | [`vulpes-facility/gh-railyard`](https://github.com/vulpes-facility/gh-railyard), `plugins/gh-railyard` |
| `gh-shapeup` | Run Shape Up on GitHub Issues and Projects by asking Claude: pitches and bets, scopes on the hill, cooldown work and bugs, completion reports and audits. | [`vulpes-facility/gh-shapeup`](https://github.com/vulpes-facility/gh-shapeup), `plugins/gh-shapeup` |

## Adding a plugin

- A plugin of a public repository stays in that repository, next to the tool it drives, and this marketplace points at it with a `git-subdir` source.
  The tool's own tests keep the plugin in step with it, and users get it from the repository's default branch.
- A plugin of a private repository is copied here under `plugins/<plugin>` and listed with a relative source,
  since users without access to the private repository could not fetch it.
  Only the plugin is copied, never the rest of the repository.
- The marketplace is named `vulpes-facility`, since names that look like Anthropic's own marketplaces, such as `claude-plugins-official`, are refused.

Run `claude plugin validate .` before a pull request.

## License

[MIT](LICENSE)
