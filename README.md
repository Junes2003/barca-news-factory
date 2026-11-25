# Barça News Factory

An individual exam project: a human-controlled software factory that transforms GitHub issues into reviewed pull requests. Barça News is an unofficial FC Barcelona fan-news website used to evaluate the factory, not the factory itself.

## Repository layout

- `app/`: website built through the factory.
- `factory/workflows/`: exported n8n workflow JSON files.
- `factory/runner/`: local runner for Basic B.
- `factory/prompts/`: task specification and AI refinement prompt.
- `docs/`: architecture, evaluation and project plan.

## Workflow

Create an issue with Ideas → Refining → Ready for approval. The owner approves it. n8n moves it to Building; in Basic A the owner starts the coding agent manually, and in Basic B the runner starts it. The agent works on branch issue-N. Questions and failures are handled by the owner; completed work is reviewed via a pull request (Your QA → Done). No automatic merges.

See [architecture](docs/architecture.md), [roadmap](docs/roadmap.md), [specification template](factory/prompts/specification-template.md) and [refinement prompt](factory/prompts/refinement-prompt.md).

## Current status

Bootstrap documentation only. The n8n workflows, runner, website and tests are not implemented yet. This bootstrap PR is not evidence of a completed factory run.

Never commit credentials, API keys or real .env files. Review all changes before merging. Use fictional sample news or properly licensed content during development.
