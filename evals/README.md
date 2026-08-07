# Evals

This folder contains the evaluation suites for the `grasp` skill.

The goal of these evals is not just to check whether the skill can produce output that "looks good." The goal is to verify that the skill creates a measurable improvement over a baseline response and that it activates only when it should.

## Evaluation Layers

The skill is evaluated along three layers:

1. `trigger` evals
   These check whether the skill should be used for a given prompt.

2. `generation` evals
   These compare output quality with and without the skill on prompts where the skill should help.

3. `regression` checks
   These guard against known style failures, formatting problems, and rule drift.

## Recommended Method

For generation evals, run each prompt twice:

1. without the skill
2. with the skill

Then score both outputs using the rubric.

The skill is providing value when:

- the skill-assisted output scores higher on the core rubric dimensions
- correctness does not get worse
- prohibited style regressions do not appear

## Running Evals

The default entry point is:

```bash
ruby evals/run_evals.rb run grasp
```

That command now always produces both of these files by default:

- `evals/reports/grasp-YYYY-MM-DD.json`
- `evals/reports/grasp-YYYY-MM-DD.html`

The JSON file is the source of truth for the report data. The HTML file is the browser-ready rendered view of that same report.

If you want to choose the filename base yourself, pass an output base or a JSON path:

```bash
ruby evals/run_evals.rb run grasp evals/reports/grasp-demo
ruby evals/run_evals.rb run grasp evals/reports/grasp-demo.json
```

Both commands will create:

- `evals/reports/grasp-demo.json`
- `evals/reports/grasp-demo.html`

You can still use the lower-level commands directly:

```bash
ruby evals/run_evals.rb scaffold grasp
ruby evals/run_evals.rb validate evals/reports/grasp-YYYY-MM-DD.json
ruby evals/run_evals.rb summarize evals/reports/grasp-YYYY-MM-DD.json
```

`summarize` now regenerates the HTML report automatically, so the browser view stays in sync with the JSON report.

## Folder Layout

`evals/grasp/` contains:

- `README.md`: suite overview and evaluation philosophy
- `rubric.md`: scoring dimensions and pass criteria
- `trigger-evals.yaml`: prompts that should and should not trigger the skill
- `generation-evals.yaml`: prompts for A/B comparison
- `regression-checks.yaml`: high-priority constraints and failure modes

The evals root contains:

- `run_evals.rb`: a lightweight runner for scaffolding, validating, summarizing, and rendering reports
- `report-format.md`: documentation for the JSON and HTML reporting flow
- `reports/`: generated report artifacts
