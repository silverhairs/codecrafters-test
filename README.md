# CodeCrafters Test

## Introduction

This GitHub Action is designed to facilitate running tests on your code when working on a challenge from [CodeCrafters](https://codecrafters.io/). It uses the [CodeCrafters CLI](https://docs.codecrafters.io/cli/installation) to run tests and view test results from github.

## Prerequisites

Before using this GitHub Action, ensure you have:

- An active CodeCrafters account.
- Basic knowledge of YAML and GitHub Actions.

## Inputs

- `remote-url`: The git remote URL you get when you kick start a new challenge on [CodeCrafters.io](https://codecrafters.io/).
  It's preferable to keep this in a [secret](https://docs.github.com/en/actions/security-guides/using-secrets-in-github-actions).

## Usage

Here's how to integrate the this action into your GitHub workflow:

1. If not already present, create a workflow file (e.g. `main.yml`) in your `.github/workflows` directory.

2. Include the "Codecrafters Test" action in your workflow file. Below is an example snippet:

   ```yaml
   name: CodeCrafters Test
   on: [push, pull_request]

   jobs:
     codecrafters-test:
       runs-on: ubuntu-latest
       steps:
         - uses: actions/checkout@v2
         - name: Run Codecrafters Test
           uses: actions/codecrafters-test@v1
           with:
             remote-url: ${{ secrets.CODECRAFTERS_REMOTE }} # Replace with your remote URL
   ```

3. Ensure the `remote-url` input is correctly set in the `with` section of your workflow.

4. Save the changes to your workflow file and push them to your repository.

## Contributing

Contributions to enhance this action are always welcome. Feel free to fork the repository, make your improvements, and submit a pull request.
