# AI refinement evaluation — Issue #2

**Date:** 25 November 2026  
**Model:** Ollama (`llama3.2:latest`)  
**Workflow:** `01 - Refine Task`  
**Test case:** [Create Barça News homepage](https://github.com/Junes2003/barca-news-factory/issues/2)

## 1. Initial refinement

The original issue requested a homepage with FC Barcelona colors, a navigation bar and a latest news section. The AI generated a specification using the seven-section template.

| Test | Observed result |
|---|---|
| Before prompt adjustment | Assumed an existing CMS, database, logo and brand guidelines. Added a minimum of three articles without approval. |
| After prompt adjustment | Removed the assumptions about existing infrastructure, proposed local sample data and retained the original homepage features. Some acceptance criteria remained vague, and the AI still asked about a logo. |

The following instructions were appended to the initial refinement prompt:

```text
The project is currently being built from scratch.
Do not assume that a CMS, database, framework, logo,
API or existing functionality is available.
Use simple local sample data where appropriate.
Ask the owner if technical requirements are unclear.
```

The [second output](https://github.com/Junes2003/barca-news-factory/issues/2#issuecomment-7160463709) was posted to GitHub, and the issue moved to Ready for approval.

## 2. Owner clarification and re-refinement

The workflow was extended to retrieve comments and identify owner replies after the latest AI specification. The AI comment marker (`<!-- factory-ai -->`) distinguishes future specification comments from owner replies because both use the same GitHub account. The original unmarked comment was handled using its known ID.

The [owner's clarification](https://github.com/Junes2003/barca-news-factory/issues/2#issuecomment-7161095003) specified HTML, CSS and JavaScript, local fictional news instead of a database or external API, blue and red colors, no required official logo, and mobile and desktop support.

Manual testing confirmed that the reply detector returned no items before the clarification and one item afterward. The issue was moved back to Refining, and AI Re-Refinement received the original description and the owner's reply.

| Test | Observed result |
|---|---|
| First re-refinement | Included most clarifications but omitted HTML, CSS and JavaScript. Introduced an unrequested loading time under three seconds and article dates. Added a Status section and closing note. |
| Second re-refinement | Included all explicit owner requirements and followed the requested seven-section structure. Still introduced a three-second loading target, at least three articles with images, example events/shop navigation and physical-device/virtual-machine testing. |

The following instructions were appended to the re-refinement prompt between these two tests:

```text
Preserve every explicit requirement from the owner's clarification, including the chosen programming languages and technologies.

Do not introduce new performance targets, features, or technical requirements unless explicitly requested by the owner.

Before returning the specification, check that every owner requirement is included.

Return only the requested specification sections.
```

## 3. Evaluation

Providing project context reduced unsupported infrastructure assumptions. Explicit requirement-preservation instructions improved coverage and output structure, but did not eliminate invented requirements. For example, the three-second loading target appeared in both re-refinement outputs despite the second prompt explicitly prohibiting new performance targets.

The owner must therefore review and correct the specification before approval. AI output is a proposal, not authorization to expand the task.

These are qualitative observations from four manually tested outputs for one issue, not a controlled benchmark. The second re-refinement output has been generated but its publication and return to Ready for approval have not yet been verified. Scheduled operation, repeated clarification rounds, failure recovery and coding-agent implementation are not demonstrated by these tests.

*The output descriptions above are summaries, not verbatim transcripts. The full initial outputs remain available in the document's earlier Git history.*
