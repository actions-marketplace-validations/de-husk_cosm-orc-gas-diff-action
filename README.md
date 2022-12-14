# Cosm-Orc Gas Diff Github Action

Github action that posts gas usage reports from [cosm-orc](https://github.com/de-husk/cosm-orc) as Github PR comments and a Github action job summary.

If `repo_token` does not have `issues` write access, then the Github PR comment will be skipped, however the Github action job summary will still be posted.

## Usage
```yml
- uses: de-husk/cosm-orc-gas-diff-action@v1
  with:
    repo_token: ${{ secrets.GITHUB_TOKEN }}
    current_json: "./current.json"
```

## Build

```bash
$ yarn
$ yarn run build
```

## Package Prod Js Files

Actions are run from GitHub repos so we will checkin the packed dist folder. 

Then run [ncc](https://github.com/zeit/ncc) and push the results:
```bash
$ yarn run build && yarn run package
```