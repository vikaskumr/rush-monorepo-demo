# rush-monorepo-demo
# Enterprise Key Connect (EKC)

Make use of existing key infrastructure in Energy Web products and services.

## Quick Start

>note: not publshed yet!

```
npm install @energyweb/ekc
```

## Example Integrations

See [examples](./examples)

## API

TODO

## Development

```
git clone git@github.com:energywebfoundation/ekc-monorepo.git
```

Before anything else, install [Rush](https://rushjs.io) globally:
```
npm i -g @microsoft/rush
```

You will interact with the repo and packages via `rush` only. There are two
different types of commands: "bulk" and "project". Do not use `npm` or `yarn`
or it will mess with dependencies. Note that the demos in the `examples`
directory are not managed by Rush.

Developer primer: https://rushjs.io/pages/developer/new_developer/

## Bulk commands

These are used to setup the repo and can also run the same command in
every project/package (for example building and testing).

### Updating dependencies

If you want to fetch the latest deps (e.g. on new `git pull`, `package.json`
changes), run the update command:
```
rush update
```

This can be used for every project, or even if only one package's dependencies
change.

### Checking dependencies

Run the check command to make sure dependencies match across projects:
```
rush check
```

### Build all projects

```
rush build
```

### Custom commands

These are configured in `common/config/rush/command-line.json`.

Run all tests:
```
rush test
```

Run all linters:
```
rush lint
```

## Project commands

These are used in an individual project (package), e.g. installing a new
dependency or running the project's tests.

### Install new dependency

```
cd <your_package>
rush add [--dev] -p <package_name>
```

### Run `package.json` scripts

Use `rushx` (included with Rush install) to run the scripts. For example, if you
have a `test:unit` script in your `package.json`, simply run:
```
cd <your_package>
rushx test:unit
```
