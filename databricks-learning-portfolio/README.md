# Databricks Learning Portfolio

A central home for my Databricks learning journey, hands-on exercises, notes, and portfolio projects.

This repository is designed to grow over time. Each project should be understandable on its own, reproducible where possible, and documented clearly enough for someone else to follow.

## Repository map

```text
databricks-learning-portfolio/
├── README.md
├── .gitignore
├── LICENSE
├── notes/
│   ├── README.md
│   ├── learning-log.md
│   ├── concepts.md
│   ├── spark-sql.md
│   ├── pyspark.md
│   ├── delta-lake.md
│   ├── databricks-platform.md
│   └── troubleshooting.md
├── learning-path/
│   └── README.md
├── projects/
│   ├── README.md
│   └── project-template/
│       ├── README.md
│       ├── notebooks/
│       ├── src/
│       ├── data/
│       │   ├── raw/
│       │   └── processed/
│       ├── outputs/
│       └── docs/
└── resources/
    └── README.md
```

## How to use this repository

1. Keep general Databricks and data-engineering notes in `notes/`.
2. Record each study session in `notes/learning-log.md`.
3. Follow `learning-path/README.md` to track topics you have studied.
4. For every substantial exercise or project, copy `projects/project-template/` and rename the copy.
5. Give each project its own README explaining the problem, dataset, tools, steps, results, and how to reproduce the work.
6. Keep credentials, tokens, workspace URLs containing sensitive information, and private datasets out of Git.

## Suggested project naming

Use lowercase kebab-case, for example:

- `retail-sales-etl`
- `nyc-taxi-data-analysis`
- `ecommerce-delta-lake`
- `streaming-events-pipeline`

## Publishing Databricks notebooks

Databricks notebooks can be exported or synced to Git depending on your workspace setup. When committing notebooks, include a short explanation of their purpose and any required input data. If a notebook export contains a large amount of output, consider clearing outputs before committing.

## Data and privacy rules

- Do not commit passwords, access tokens, API keys, client secrets, or `.env` files.
- Do not commit private/company/university data unless you have permission.
- Prefer small public sample datasets or documented download instructions.
- Add large datasets and generated artifacts to `.gitignore` or use an appropriate data-storage solution.
- Review `git status` and the staged diff before every push.

## Project quality checklist

- [ ] Project has a clear problem statement and objective.
- [ ] Dataset source and licence/usage terms are documented.
- [ ] Data quality checks are included.
- [ ] Transformations are explained.
- [ ] Results are supported by outputs, charts, or queries.
- [ ] README includes setup/reproduction instructions.
- [ ] No secrets or restricted data are committed.
- [ ] Limitations and possible improvements are documented.

## Notes

This is a learning portfolio, so it is fine for early projects to be small. Prioritise clear explanations, correct work, and visible progress over making every project look advanced.
