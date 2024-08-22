# Repro for issue 7582

## Versions

firebase-tools: v13.15.4

## Setup

Install npm modules(run `npm i`) in `./functions` and `./ext-greet-the-world/functions`

## Steps to reproduce

1. Run `firebase ext:install ./ext-greet-the-world --project PROJECT_ID`
2. Run `firebase deploy --only extensions --project PROJECT_ID`
3. Remove the `extensions` field in `firebase.json`, or leave it as empty object `{}`
4. Run `firebase deploy --only functions --project PROJECT_ID`

- This prompts for extension deletion
- Passing the `--force` flag will bypass the prompt and delete the `greet-the-world` extension
  - `firebase deploy --only functions --project PROJECT_ID --force`
