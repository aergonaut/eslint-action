# `eslint-problem-matchers`

Problem Matchers for GitHub Actions supporting various ESLint output formats.

The currently supported formats are:

* [visualstudio](https://eslint.org/docs/user-guide/formatters/#visualstudio)

This action only setups the matchers to parse output and create annotations. _It
does not run ESLint!_ You must make sure ESLint runs in another step in your
workflow, after this action has run.

## Usage

Add it to your workflow file:

```yml
jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v1
        with:
          node-version: 12
      - uses: aergonaut/eslint-problem-matchers@v1
      - runs: |
          npx eslint --format visualstudio
```

You must ensure ESLint runs _after_ this action in your workflow file. This
action does not run ESLint for you.

## License

MIT.