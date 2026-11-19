---
name: scientific-agent-judge
description: Judge scientific AI agent hackathon entries from PowerPoint decks, slides, demo recordings, or submitted results. Score Creativity, Functionality, and Usefulness from 1 to 5 each and cite the evidence behind each score.
---

# Judge scientific AI agent hackathon entries

## Review the submission

Identify the scientific task, intended user, and current workflow. Trace a representative run from input through the agent's steps to the output. Identify what the agent handles, when a person intervenes, and how the team checked the result.

For a presentation, inspect relevant diagrams, screenshots, charts, tables, and speaker notes alongside the slide text. Use the submitted demo or results if accessible. Cite slide numbers as displayed, or use their one-based positions if the slides are unnumbered. Cite timestamps for recordings when they help locate evidence.

Distinguish completed runs, team-reported results, and proposed capabilities. An architecture diagram shows the intended workflow. Demonstrated execution requires evidence of a run, such as a recording, trace, or documented input and output. State when a result comes from a team-reported evaluation. If the presentation is unavailable or unreadable, ask for a readable copy before scoring. If the presentation is readable but evidence is incomplete, score what it supports and identify the gap.

## Score each criterion independently

Use the highest anchor supported by the submission for each criterion. Assign integer scores from 1 to 5 and add them for a total out of 15. Use the same anchors for every entry.

| Score | Creativity | Functionality | Usefulness |
|---|---|---|---|
| **5** | Introduces a distinctive approach that opens up a new way to carry out the scientific task. | Completes the core workflow on a representative case, verifies key outputs with an appropriate reference or check, and shows how it handles a relevant failure or uncertainty. | Shows a substantial benefit over the current workflow on a representative task and accounts for the effort to use the agent and verify its results. |
| **4** | Adapts or combines existing methods in an inventive way that fits the task. | Completes the core workflow on a representative case and credibly checks the main outputs, with minor gaps. | Shows a clear benefit on a representative task and explains how the agent fits the intended user's workflow. |
| **3** | Adds a thoughtful, task-specific idea to a familiar approach. | Completes the main task on a straightforward case and shows a basic check of the result. | Addresses a real need for a defined user and describes a plausible benefit that remains unsubstantiated. |
| **2** | Makes a small task-specific adaptation to a standard agent pattern. | Shows working components with a key step incomplete or performed manually beyond the intended human review, or shows a complete run with no check of the result. | Addresses a recognizable task, with an unclear intended user or improvement over current practice. |
| **1** | Shows little original thinking in the problem framing or approach. | Provides no evidence of a working core task or its component steps. | Provides no clear scientific use case or practical benefit. |

- **Creativity** asks what is original about the problem framing or design and why it fits the scientific task. Credit a promising design idea even when its implementation is incomplete.
- **Functionality** asks what the agent completed and what supports the correctness of its outputs. Accept planned human checkpoints as part of the workflow. Match the verification to the task. A literature agent could show source traceability, while an analysis agent could compare results with an expected output or a reference calculation.
- **Usefulness** asks who would use the output, what they do today, and what improves after setup, review, and correction. Consider benefits such as time saved, improved accuracy, or the ability to answer a previously impractical question. Task-relevant qualitative or quantitative evidence can support a benefit.

Base scores on the work and evidence. Exclude slide polish, team reputation, and model brand from scoring.

## Return a scorecard

For each entry, give its name and total out of 15, then a table with **Criterion**, **Score**, and **Evidence and rationale**. Use one row per criterion. Cite specific submission evidence, connect it to the chosen anchor, and identify any missing evidence that affected the score. Close with the strongest point and the most consequential evidence gap or improvement, when applicable.

When ranking entries, sort by total, then by Usefulness, then by Functionality. Leave entries tied if all three comparisons are equal. When combining several judges' scores, use the mean of their totals and apply the same tie-break order to the mean criterion scores.
