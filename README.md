# RoboChart Python testsuite

This repository holds a testsuite for the RoboChart-to-Python translator: the
ExpressionTests cases, each recorded with the result that the translated
Python produced, together with the RoboTool project generated from them and
the verification results.

The translator is the system under test. For each RoboChart expression or
statement, a test case records the input values and the result that the
translated Python produced. RoboTool and FDR are the oracle: they check
whether the recorded result agrees with RoboChart's semantics. The Python
results are supplied via `data/cases.csv`.
A refuted observation is evidence of a translator
defect; a verdict applies only to the supplied inputs, value domains and
helper equations.

## What is here

| Path | Contents |
| --- | --- |
| `data/cases.csv` | The 548 expression cases. |
| `data/statement_cases.csv` | Statement cases: these are currently dummy testing cases. |
| `data/supplementary_expression_cases.csv` | Three further expression examples, generated separately. |
| `data/shared_fixtures.json` | Fixed declarations for expression cases that name context their row does not declare. |
| `testsuite-project/` | The RoboTool Modeling Project generated from `data/`, with its diagrams and results. |
| `check` | The script that regenerates the project and compares it with the committed copy. |

We also have the generated RoboChart project `testsuite-project/`: This contains,

- `cases/`: one RoboChart `.rct` model per case that could be represented;
- `representations.aird`: the native RoboChart diagrams of those models;
- `case-index.csv`: each case ID with its model, diagram name and expected status;
- `generation-failures.csv`: the cases that could not be represented, with a category and reason;
- `source-data/`: a snapshot of the input rows used to build the project;
- `verification-results.csv` and `verification-results.md`: the verdict for every case;
- `verification-logs/`: RoboTool's and FDR's output for each case.

The generated CSP (`csp-gen/`, `src-gen/`) is not tracked by Git.

## Install the generation tools

The testsuite project is produced and checked by two tools, `testsuite-generator`
and `testsuite-runner`, from
<https://github.com/twright/robochart-testsuite-generator>. Install them from
a checkout of that repository:

```sh
git clone https://github.com/twright/robochart-testsuite-generator
cd robochart-testsuite-generator
cargo install --locked --path crates/testsuite-generator
cargo install --locked --path crates/testsuite-runner
```

Its [README](https://github.com/twright/robochart-testsuite-generator#readme)
lists the prerequisites (Rust, RoboTool 1.2.2026062401, Java and an activated
FDR), includes troubleshooting advice, and describes the input format of the
files in `data/`. RoboTool 1.2.2026062401 is the version used to generate the
committed diagrams and results.

`testsuite-runner` finds RoboTool and FDR through two settings, each given as
an environment variable or an option (the option wins):

| Environment variable | Option | Value |
| --- | --- | --- |
| `ROBOTOOL_HOME` | `--robotool-home DIR` | The RoboTool installation directory. |
| `FDR_REFINES` | `--fdr-refines FILE` | FDR's `refines` executable. |

If the two programs are not on `PATH`, `check` uses the programs named by
`TESTSUITE_GENERATOR` and `TESTSUITE_RUNNER`.

## Open the RoboChart models

1. In RoboTool 1.2.2026062401, choose **File → Import → General → Existing
   Projects into Workspace** and select this repository's `testsuite-project/`
   directory.
2. Leave **Copy projects into workspace** unchecked, so that RoboTool shows
   the files that the generator writes. This imports one project named
   `testsuite-project`.
3. Open `representations.aird` in Model Explorer and expand **RoboChart →
   Package** in the Representations pane to choose a diagram. The diagram
   names match the `diagram` column of `case-index.csv`, for example
   `expression_add_000`; the corresponding models are under `cases/`.

The generator keeps an existing `representations.aird` but does not draw
diagrams. After regenerating the project, use the RoboTool start-up plug-in
described in the generator repository's README (section on adding and
refreshing diagrams) to create the diagrams of new cases and to refresh those
of changed models. Its `-Dtestsuitegenerator.project` property takes the
absolute path of `testsuite-project/`; `-Dtestsuitegenerator.refresh=all`, or
a comma-separated list of diagram names, refreshes existing diagrams. After
regenerating, select the project in RoboTool and press F5 to refresh it.

## Regenerate the project

From the repository root:

```sh
testsuite-generator data testsuite-project
```

This should report `Generated 496 models and recorded 80 generation failures`.
It rewrites the models, `case-index.csv`, `generation-failures.csv` and
`source-data/`, and preserves `representations.aird`. It does not delete the
models of cases that are no longer in `data/`; remove them by hand.

## Check the suite

```sh
./check                          # full check, in place
./check --jobs 8                 # full check, eight test cases at a time
./check --no-verify              # regeneration only
./check add/000 assignment/pass  # quick check of chosen cases, in a temporary copy
```

**A full check compiles every test case with RoboTool and verifies it with FDR,
so it takes a while:** about five minutes with `--jobs 8` on a desktop machine,
and far longer one test case at a time. `--jobs` defaults to the number of
processors. The full check:

1. regenerates `testsuite-project/` from `data/`;
2. runs `testsuite-runner verify testsuite-project`, which rewrites
   `verification-results.{csv,md}` and `verification-logs/`;
3. fails if any tracked file differs from the commit, or if a new file
   appears that Git does not ignore.

`testsuite-project/verification-logs/` is rewritten but not compared: it
contains RoboTool's raw output, which carries timestamps. The log file names,
and the verdict of every case, are still compared through
`verification-results.csv`. Commit regenerated or reverified files if you mean
to change the suite; the check then tests that the commit is reproducible.

With case IDs, `check` works in a temporary directory and changes nothing in
the repository. It generates and verifies only the listed cases and compares
each one's model, its row in `case-index.csv` and its row in
`verification-results.csv` (without the log file name, which depends on the
numbering within a run) with the committed ones. Pass `--robotool-home` and
`--fdr-refines`, or set the environment variables, so that the checks can run.

## Current results

`testsuite-project/verification-results.csv` records 576 cases:

| Status | Cases | Meaning |
| --- | ---: | --- |
| `pass` | 401 | FDR's result matched the case's expected status. Expression cases are confirmed; statement cases marked `mismatch` are refuted, as intended. |
| `translator_defect` | 6 | FDR refutes the recorded Python observation of a case that RoboTool translates: evidence of a translator defect. |
| `unsupported_robotool` | 93 | Valid RoboChart, but a reproduced RoboTool defect or the integer-valued reals limitation prevents a verdict. |
| `unsupported_case` | 76 | The expression is not valid RoboChart, so it cannot be checked; probably an error in the case specification. |
| `failure` | 0 | No verdict and no evidence for the above, such as a timeout or a missing tool. |

`verification-results.md` gives the same results with a breakdown by category
and links to each model, and the generator repository's documentation of
RoboTool findings explains how each status is decided.
