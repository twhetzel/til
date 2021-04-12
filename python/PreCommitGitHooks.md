# Pre-commit Hooks

## Description
Pre-commit hooks are a subset of Git hooks. Git hooks in general run automatically each time a Git event occurs. A pre-commit hook runs for a commit event. A pre-commit hook can be configured to run locally, which can save development time by not needing to wait for a CI/CD pipeline to run, find and fix errors, commit updates, and then wait for another round of the CI/CD to complete.

## Getting Started
- Install pre-commit:\
`pip install pre-commit`

- Create a "pre-commit-config.yaml" YAML file to configure which pre-commit hooks to run:\
`touch .pre-commit-config.yaml`

- Create YAML file with hooks

#### Example YAML File
```
repos:
    - repo: https://github.com/pre-commit/pre-commit-hooks
      rev: v3.2.0
      hooks:
        - id: trailing-whitespace
        - id: mixed-line-ending
        - id: check-added-large-files
    - repo: https://github.com/psf/black
      rev: 19.10b0
      hooks:
        - id: black
    - repo: https://github.com/asottile/blacken-docs
      rev: v1.8.0
      hooks:
      - id: blacken-docs  # Apply black formatting to code-strings in docstrings
        additional_dependencies: [black==20.8b1]
    - repo: https://github.com/pre-commit/mirrors-prettier
      rev: v2.2.1 # Use the sha or tag you want to point at
      hooks:
      - id: prettier  # Lint JavaScript and JSON files
      - types: [javascript]
    - repo: https://github.com/asottile/seed-isort-config
      rev: v2.2.0
      hooks:
      - id: seed-isort-config  # Sort imports
    - repo: https://github.com/pre-commit/mirrors-isort
      rev: v5.4.2
      hooks:
      - id: isort. # Sort imports
 ``` 
 
- Initialize the Git hooks for the repository:  
`pre-commit install`\
`> pre-commit installed at .git/hooks/pre-commit`

- After installing pre-commit and setting up the configuration file, run check on all files in repo to get started (usually `pre-commit` will only run on the changed files during git hooks):\
`pre-commit run --all-files`

- To run individual hooks use:   
`pre-commit run <hook_id>`

- NOTE: Git commits can still be run without using "pre-commit" as:  
 `git commit --no-verify`

 
 # References
 - https://towardsdatascience.com/getting-started-with-python-pre-commit-hooks-28be2b2d09d5
 - https://towardsdatascience.com/pre-commit-hooks-you-must-know-ff247f5feb7e


 
