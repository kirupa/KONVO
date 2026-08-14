# Reports

This folder stores generated eval reports.

Typical flow:

1. Run `ruby evals/run_evals.rb run <skill>`
2. Fill in the generated JSON report
3. Validate with `ruby evals/run_evals.rb validate <report.json>`
4. Summarize with `ruby evals/run_evals.rb summarize <report.json>`

By default, `run` writes both:

- a JSON report
- a matching HTML report for browser viewing

For example:

```bash
ruby evals/run_evals.rb run konvo
```

creates:

- `evals/reports/konvo-YYYY-MM-DD.json`
- `evals/reports/konvo-YYYY-MM-DD.html`
