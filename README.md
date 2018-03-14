# Case Commons Javascript lint config

Configuration for [ESLint](http://eslint.org/) per Case Commons style guide.

## Usage

Add to dev dependencies in your project:

```
npm install --save-dev https://github.com/Casecommons/lint-config-javascript.git
```

Then use [`extends`](http://eslint.org/docs/user-guide/configuring#using-a-shareable-configuration-package) to include the appropriate lints into `.eslintrc` in your own project. For example:

```javascript
// .eslintrc

{
  extends: [
    "eslint-config-cc/eslintrc-modern",
  ],
}
```

There are various configurations available:

- `eslint-config-cc/eslintrc-base`: Base configuration applicable to any ECMAScript.
- `eslint-config-cc/eslintrc-test`: Extension of base configuration for test code.
- `eslint-config-cc/eslintrc-modern`: Extension of base configuration for modern (2015+) ECMAScript.
- `eslint-config-cc/eslintrc-test-modern`: Extension of modern configuration for test code.

## Development

Docker should be used for simpler dev setup. To do so:

1. `cp .env.sample .env` and set values in `.env` accordingly.
2. `docker-compose build`
3. Prefix the usual `yarn`, etc., commands with `docker-compose exec app`/`docker-compose run --rm app` or similar.

### Packaging

Run `yarn pack` which will emit a tarball in the package root directory. This is useful for testing the client in another project without having to perform a release (see [package.json local paths](https://docs.npmjs.com/files/package.json#local-paths)).

### Releasing

Run `bin/release`.
