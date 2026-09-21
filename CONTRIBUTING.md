# Contributing

Read `README.md` for repository setup and verification commands. Changes should be linked to a GitHub issue and delivered through a pull request.

## Agent configuration

The agent workflow, triage roles, and shared conventions are installed skills rather than committed copies. Their source is [`clhbid/agent-context`](https://github.com/clhbid/agent-context); see **Agent skills** in [`AGENTS.md`](AGENTS.md).

Install or refresh them outside a devcontainer with:

```sh
./scripts/install-agent-skills.sh
```

The default target is Claude Code. Pass another agent name, such as `copilot`, or pass `'*'` for every agent detected by the installer.

A devcontainer should call the same script from its post-create command. If network installation fails, let the container start and print the command above so the failure is visible and recoverable.
