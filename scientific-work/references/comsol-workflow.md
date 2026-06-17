# COMSOL Workflow

Use this reference for COMSOL, CST, FEM, mode analysis, `.mph`, Java automation, and numerical validation tasks.

## Safety

- Do not edit original `.mph` files directly.
- Work on a copy or generate a new model.
- Keep raw simulation files separate from concise Obsidian decision notes.

## Modeling Hygiene

- Record geometry, materials, boundary conditions, mesh settings, solver settings, and swept parameters.
- Record units explicitly.
- Note what changed between simulation runs.
- Validate against analytic estimates, convergence checks, or an independent reference when possible.

## Reporting

- Distinguish observed results from hypotheses.
- Include plots or exported values only when they support a decision.
- Write conclusions as next modeling actions: what to refine, compare, sweep, or verify.

## Automation

- Prefer scripts for repeatable parameter sweeps or model generation.
- Keep generated files named by date, model variant, or parameter set so results are traceable.
