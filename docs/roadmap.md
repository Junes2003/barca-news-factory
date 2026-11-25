# Project roadmap

1. Review and merge bootstrap documentation.
2. Implement Basic A: scheduled refinement, start tracking, PR tracking. Test manual agent runs.
3. Implement Basic B: runner, one active task, owner questions/resume, failure and timeout, result polling and PR creation.
4. Advanced: independently check changed files and tests; isolate the agent and evaluate permissions. Choose other extensions only after the core loop works.
5. Run at least five real tasks through the factory with issues and PRs. Record actual outcomes, interventions and test evidence.
6. Write the max-five-page report and prepare the oral demo.

## Proposed Barça News tasks (not yet created as issues)

| Task | Dependency | Acceptance example |
|---|---|---|
| Homepage layout | None | Responsive navigation and a news section |
| Sample news cards | Homepage | Cards display title, summary and category from local sample data |
| Article detail view | Cards | Clicking a card opens the matching article |
| Category filtering | Cards | Transfers, matches and club news filters work |
| Search | Cards | Case-insensitive title/summary search and empty-result state |
| Optional favorites | Cards | Favorites persist locally after reload |
| Optional combined filters | Search and categories | Search and category filters work together |

Keep the website modest; use fictional, clearly labeled sample content initially. No live API, paid service or database is assumed.

## Evaluation log

Record per run: issue link, PR link, level (A/B/Advanced), duration, refinement questions, agent outcome, human interventions, verification evidence, final decision and lessons. Record failures honestly. The bootstrap itself does not count as a factory run.
