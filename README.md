# Angular's Tour of heroes app with the configuration for Github marketplace apps examples
This repo has following Github marketplace apps installed and configured:
- Codecov
- Stale
- Imgbot

## Codecov
### Installation

1) Configure everything as described on [Codecov page](https://github.com/marketplace/codecov).

2) Configure karma coverage reports to be compatible with Codecov:
- add a reporter `{ type: 'lcovonly' }` to `coverageReporter.reporters` to generate report in the format compatible with Codecov
- change your `coverageReporter.dir` config to `require('path').join(__dirname, './coverage')` so Codecov can find it by default

3) Install codecov:
```
npm install codecov -g
```

4) Generate test coverage report with the following command(e.g. on pre-push hook):
```
npm run coverage
```

5) Find and upload the report from step 3) to Codecov by running: 
```
codecov --token=:token
```
, where `:token` is Codecov token of your repo, specified in your Codecov account (e.g. for this repo I can find my token here: https://app.codecov.io/gh/AnastasiaNRadionova/github-marketplace-apps-example)
