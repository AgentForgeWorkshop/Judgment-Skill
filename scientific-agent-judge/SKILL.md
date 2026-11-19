---
name: scientific-agent-judge
description: Judge science and research AI agent hackathon entries using only a GitHub repository URL. Review repository code, documentation, tests, and evaluation evidence; score Creativity, Functionality, Usefulness, and Evaluation & Trustworthiness from 1 to 5 each, with cited evidence.
---

# Judge scientific AI agent hackathon entries

## Input: GitHub repository URL only

Accept a GitHub repository link in the form `https://github.com/<owner>/<repo>`. To compare or rank entries, accept one GitHub repository URL per entry. Do not request or accept slide decks, presentation files, demo recordings, or other separate submission materials. Materials already committed to the repository (such as documentation, examples, tests, traces, or evaluation reports) may be inspected as repository evidence.

Open the repository and identify its name and, when available, the commit being reviewed so the judgment is reproducible. If the URL is not a GitHub repository URL, ask for one. If the repository is inaccessible, empty, or cannot be inspected, explain the limitation and do not fabricate a score.

## Review the repository

1. Read the README, repository structure, and relevant documentation to identify the task, intended user, baseline or current workflow, and claimed capabilities. The task may support scientific or research work directly or indirectly.
2. Inspect the relevant source code, configuration, prompts, agent workflows, tool integrations, and examples. Identify what the agent actually implements, the inputs it accepts, its steps, its outputs, and any intended human checkpoints. Focus on the core workflow rather than reviewing every file equally.
3. Look for repository-backed evidence that the workflow executes: runnable entry points, tests, example inputs and outputs, saved traces, CI results, or documented runs. Distinguish **implemented in code**, **team-reported as executed**, and **independently verified**. Do not claim to have run code or verified outputs unless you actually did so.
4. Review evaluation artifacts, if present: test cases, ground truth or reference checks, evaluation metrics, error analyses, reliability tests, and limitations. Assess whether the chosen checks are suitable for that particular task.
5. Cite specific repository evidence with links to files, line ranges, tests, or evaluation reports whenever available. Prefer commit-pinned links for stable references. If evidence is missing, explicitly say so. Do not treat a claim in the README as independent verification.

Do not execute untrusted repository code by default. If execution is explicitly authorized and a suitably isolated environment is available, report exactly what was run and what happened; otherwise judge from inspectable repository evidence. An incomplete or undocumented repository can still be scored based on what is actually supported, provided it is accessible and inspectable.

## Score each criterion independently

Assign an integer **1–5** to each criterion, using the highest anchor supported by repository evidence. Sum the four scores for a **total out of 20**. Apply the same rubric to every entry, while allowing task-appropriate ways of demonstrating value and evaluating correctness.

| Score | Creativity | Functionality | Usefulness | Evaluation & Trustworthiness |
|---|---|---|---|---|
| **5** | Introduces a distinctive approach that opens up a new way to carry out the task. | Demonstrates an end-to-end core workflow on representative cases, including handling of a relevant operational failure or edge case. | Shows a substantial benefit over the current workflow on a representative task, accounting for setup, review, and correction effort. | Provides systematic, reproducible evaluation across representative cases; uses credible reference checks or ground truth; probes relevant failures or uncertainty and reports limitations. |
| **4** | Adapts or combines existing methods in an inventive way that fits the task. | Demonstrates the end-to-end core workflow on a representative case, with only minor implementation or operational gaps. | Shows a clear benefit on a representative task and explains how the agent fits the intended user's workflow. | Documents a clear evaluation method with multiple meaningful test cases and credible correctness checks, with minor coverage or reporting gaps. |
| **3** | Adds a thoughtful, task-specific idea to a familiar approach. | Demonstrates the main task on a straightforward case, but with limited evidence of broader operation or robustness. | Addresses a real need for a defined user and describes a plausible benefit that remains unsubstantiated. | Provides some actual test cases and appropriate basic checks, but evaluation coverage or analysis is limited. |
| **2** | Makes a small task-specific adaptation to a standard agent pattern. | Implements working components, but a key step is incomplete or relies on manual work beyond intended human review; or the full workflow is claimed but not demonstrated. | Addresses a recognizable task, with an unclear intended user or improvement over current practice. | Provides only minimal validation, such as one informal example, superficial checks, or unsupported claims of correctness. |
| **1** | Shows little original thinking in the problem framing or approach. | Provides no credible evidence of a working core task or its component steps. | Provides no clear use case or practical benefit. | Provides no meaningful evaluation or evidence supporting output correctness. |

### Keep the criteria distinct

- **Creativity — How original is the idea or approach?** Judge novelty in problem framing or agent design. Credit a promising design idea even if implementation is incomplete.
- **Functionality — Does the agent work?** Judge whether the intended task and workflow are implemented and demonstrated, including appropriate human checkpoints. *Do not award or deduct Functionality points based on the strength of correctness evaluation; that belongs in Evaluation & Trustworthiness.* A complete run is not the same as a correct result.
- **Usefulness — Who benefits and how much?** Judge the intended user, current alternative, practical benefit, and effort required to adopt and review the agent. Qualitative evidence can be valid; a numerical benchmark is not mandatory for every task.
- **Evaluation & Trustworthiness — How do we know the results can be trusted?** Judge the appropriateness and quality of tests, validation, evidence of correctness, reproducibility, treatment of errors and uncertainty, and disclosed limitations. Match checks to the task: for example, verify mathematical proofs with an independent checker, cross-check cited scientific claims against sources, or check itinerary facts and feasibility against references. Do not require the same metric or benchmark for every project, and do not confuse the presence of test files with proof that tests passed.

Base scores on inspectable work and evidence, not README polish, repository popularity, team reputation, or model brand. Lack of evidence should limit the relevant score; do not infer that a missing test or demonstration passed.

## Return a scorecard

For each repository, return:

- **Project name** and **GitHub URL**, plus reviewed commit if identifiable.
- **Total score: X/20**.
- A table with **Criterion**, **Score (1–5)**, and **Evidence and rationale**, with one row for each of the four criteria. Connect each score to its rubric anchor; cite relevant repository files, line ranges, or test/evaluation artifacts and identify evidence gaps.
- **Strongest point** and **most consequential gap or suggested improvement**.
- A short **verification note** stating whether the review was based on static repository inspection, team-reported run/test artifacts, or actual independent execution.

When ranking entries, sort by total score, then by Usefulness, then by Functionality, then by Evaluation & Trustworthiness. Leave entries tied if all those comparisons are equal. When combining several judges' scores, use the mean of their totals and the same tie-break order applied to mean criterion scores.
