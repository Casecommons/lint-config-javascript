# Case Commons JavaScript lint config

Configuration for [ESLint](http://eslint.org/) per Case Commons style guide. For TypeScript linting, see [lint-config-typescript](https://github.com/Casecommons/lint-config-typescript).

## Usage

Add to dev dependencies in your project:

```
yarn add --dev @casecommons/eslint-config
```

Be sure to add ESLint as a dependency in your project and set it up to run as part of the project’s test suite.

Use [`extends`](http://eslint.org/docs/user-guide/configuring#using-a-shareable-configuration-package) to include the appropriate lints into `.eslintrc` in your own project. For example:

```javascript
// .eslintrc

{
  extends: [
    "@casecommons/eslint-config/eslintrc-modern",
  ],
}
```

There are various configurations available:

- `@casecommons/eslint-config/eslintrc-base`: Base configuration applicable to any ECMAScript.
- `@casecommons/eslint-config/eslintrc-test`: Extension of base configuration for test code.
- `@casecommons/eslint-config/eslintrc-modern`: Extension of base configuration for modern (2015+) ECMAScript.
- `@casecommons/eslint-config/eslintrc-test-modern`: Extension of modern configuration for test code.

## Development

Docker should be used for simpler dev setup. To do so:

1. `cp .env.sample .env` and set values in `.env` accordingly.
2. `docker-compose build`
3. Prefix the usual `yarn`, etc., commands with `docker-compose exec app`/`docker-compose run --rm app` or similar.

### Packaging

Run `yarn pack` which will emit a tarball in the package root directory. This is useful for testing the client in another project without having to perform a release (see [package.json local paths](https://docs.npmjs.com/files/package.json#local-paths)).

### Releasing

Run `bin/release`.
