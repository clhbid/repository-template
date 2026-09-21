# CLHbid repository template

Start new CLHbid repositories with the shared agent workflow already in place.

## Before the first issue

Replace this README with repository-specific documentation covering:

1. purpose and domain terminology;
2. architecture, tech stack, and project structure;
3. prerequisites and local setup;
4. exact build, typecheck, test, lint, format, and generated-file checks;
5. release and deployment workflow;
6. integrations, secrets, and operational limitations without committing credentials.

Review `AGENTS.md` and add only repository-specific workflow rules that are not discoverable from code or configuration. Shared delivery conventions belong in [`clhbid/agent-context`](https://github.com/clhbid/agent-context), not in copied local documentation.

## Shared agent skills

Install or refresh skills locally with:

```sh
./scripts/install-agent-skills.sh
```

Pass an agent name to target another client, or `'*'` to install for every detected agent. A future devcontainer should invoke this script rather than duplicate its commands.

## Creating a repository from this template

```sh
gh repo create clhbid/NEW_REPOSITORY \
  --template clhbid/repository-template \
  --private
```

Choose the visibility and license appropriate to the new repository. Repositories created from a template receive a new, unrelated Git history; later template changes are not propagated automatically.
