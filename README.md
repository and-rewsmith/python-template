# Your title

## Relevant Links

## Dev Guide

This is designed to work with venv and be ran as a module. **Please use python 3.xx.**

Setup:
```
poetry install
source .venv/bin/activate
python -m neuromorphic_optimized_llms.<path>
```

There are various scripts that support devops checkin-gates and utilities:
```
# Runs all analysis python files and rebuilds the results dir at `artifacts/`.
./scripts/analysis/rebuild_analysis.sh 

# Linting that runs in the checkin-gate before PR merge. You can run it locally
# here. I also recommend setting up autopep8 in vscode.
./scripts/devops/mypy.sh
./scripts/devops/pep8.sh

# Unit tests that run in the checkin-gate before PR merge. You can run it locally
# here.
./scripts/devops/unit.sh

# This will run after a PR is merged. It is meant for longer running tests. 
./scripts/devops/smoke.sh
```

## Repo Structure

#### Top-level module
The `neuromorphic_optimized_llms` dir is the top level module. This internally contains these subgroups:
<TODO>

#### Scripts
The `./scripts` dir contains the same scripts that run all the checkin / CI automation to facilitate running locally. As well as other utilities.

#### Playground
The `./play` dir is a place to run and checkin files where the checkin rules don't apply.

#### Artifacts
The `./artifacts` dir contains all analysis plots. **Ideally this should be rebuilt and committed every time there is a source change.**. Recommend using `scripts/analysis/rebuild_analysis.sh` this to do that in one shot.

#### Docs
The `./docs` dir contains all relevant documentation.

## PRs

To merge anything your contribution must pass checkin pipelines which ensure:
1. Passing tests
2. Conformance to pep8
3. Conformance to mypy
