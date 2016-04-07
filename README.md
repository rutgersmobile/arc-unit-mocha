arc-unit-mocha
==============

Arcanist unit test engine for running [mocha](http://mochajs.org/) tests with
[istanbul](https://github.com/gotwarlost/istanbul/) for coverage reports.

## Installation

1. Copy the files to your project's root directory. A convenient way to do this is by
 adding this repository as a submodule.
 
 ```console
 $ git submodule add https://github.com/rutgersmobile/arc-unit-mocha.git .arc-unit-mocha
 $ git submodule update --init
 ```
2. Load and configure the engine by adding these lines to your `.arcconfig`:
 
 ```json
    "load": [
        ".arc-unit-mocha/src/"
    ],
    
    "unit.engine": "MochaEngine",
    "unit.mocha.coverage.exclude": [
        "ignoreme.js",
        "ignoreme2.js"
    ]
 ```
