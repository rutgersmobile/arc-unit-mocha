arc-unit-mocha
==============

Arcanist unit test engine for running [Mocha](http://mochajs.org/) tests with
[Istanbul](https://github.com/gotwarlost/istanbul/) for coverage reports.

## Installation

1. Copy the library to your project's root directory. A convenient way to do this is by
 adding this repository as a submodule.

 ```console
 $ git submodule add https://github.com/rutgersmobile/arc-unit-mocha.git .arc-unit-mocha
 $ git submodule update --init
 ```

2. Load the library and set the test engine by adding these lines to your `.arcconfig`:
 ```json
 "load": [
     ".arc-unit-mocha/src/"
 ],

 "unit.engine": "MochaEngine"
 ```

3. Run `arc unit` to run tests.

## Configuration

The following options can be set in `.arcconfig`:

| Key                             | Default value                          | Description                                                   |
| ------------------------------- | -------------------------------------- | ------------------------------------------------------------- |
| `unit.mocha.bin.mocha`          | `"./node_modules/mocha/bin/mocha"`     | Path used to invoke `mocha`.                                  |
| `unit.mocha.bin._mocha`         | `"./node_modules/mocha/bin/_mocha"`    | Path used to invoke `_mocha` (used by `istanbul`).            |
| `unit.mocha.bin.istanbul`       | `"./node_modules/istanbul/lib/cli.js"` | Path used to invoke `istanbul`.                               |
| `unit.mocha.coverage.reportdir` | `"./coverage"`                         | Path to the directory where `istanbul` should output reports. |
| `unit.mocha.coverage.exclude`   | `null`                                 | An array of paths to exclude from coverage reports.           |
| `unit.mocha.include`            | `null`                                 | An array of paths to include for the mocha tests.             |

Example values for `unit.mocha.coverage.exclude`:
```json
"unit.mocha.coverage.exclude": [
  "ignoreme.js",
  "submodules/**"
]
```
