# Agents

**Read `README.md` first.** It is the source of truth for this repository's architecture, tech stack, project structure, local setup, and exact verification commands.

This file contains agent-specific workflow guidance. Keep repository-specific engineering rules in the README or beside the code they govern; keep shared delivery conventions in the installed skills.

## Before starting work

1. Install dependencies using the command documented in `README.md`.
2. Read the README sections relevant to the requested area and inspect existing helpers, tests, and patterns before adding new ones.
3. Assign the issue to yourself — or to the person you are operating as — if it is unclaimed, then set its CLHbid Delivery `Status` to `In progress`. Use the `issue-tracker` skill.
4. Work from the issue's agent brief. If its acceptance criteria leave a consequential decision unresolved, stop and ask one specific question rather than guessing.

## Before finishing work

1. Review the change for clarity, maintainability, fitness for purpose, and unnecessary duplication.
2. Add or update tests for changed behaviour.
3. Run every build, typecheck, test, lint, format, and generated-file check documented in `README.md`. Fix failures introduced by the change.
4. Push the branch and open or update a pull request that references the issue. Use the `open-pr` skill.
5. Request review from a human maintainer and end the run in exactly one state below.

## How a run ends

Passing tests is not finishing. Every run ends in exactly one of these states:

| State | Status | What to do |
| --- | --- | --- |
| **Complete** | `Ready for Human` | Open the pull request ready for review. Use this only when checks pass and every acceptance criterion is addressed. |
| **Blocked** | `Waiting on input` | Leave the pull request as a draft and comment with the specific question or action needed, plus the steps to resolve it. |
| **Error** | `Ready for Human` | Leave the pull request as a draft and comment with what failed and, when known, how to recover. |

Setting `Status` hands the work back. Stay assigned in every state and request human review even when blocked or failed; a review request means the run stopped, not necessarily that it succeeded.

## Agent skills

Shared CLHbid conventions are installed rather than copied into each repository. Their source of truth is [`clhbid/agent-context`](https://github.com/clhbid/agent-context):

| Skill | Use it for |
| --- | --- |
| `issue-tracker` | Issues, project status, cycles, epics, decomposition, labels, and commit conventions |
| `afk-loop` | Preparing agent briefs, dispatching AFK work, reviewing runs, and handling failures |
| `cycle-review` | Recurring business-update cycles |
| `open-pr` | Opening and updating pull requests |

Install or refresh the shared skills with:

```sh
./scripts/install-agent-skills.sh
```

Pass an agent name to install elsewhere, for example `./scripts/install-agent-skills.sh copilot`, or `'*'` for every agent detected by the installer.

If the skills are unavailable, the issue's agent brief, the verification contract in `README.md`, and the run-ending table above remain sufficient to complete and hand back the work. Mention any missing reusable guidance in the pull request so it can be added to the shared source instead of duplicated here.

## Improving the agent experience

At the end of a run, leave agent-experience feedback on the pull request only when it is actionable and specific: identify what slowed the work, what source of truth was missing, or what reusable improvement should be made.
