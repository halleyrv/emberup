# emberup

Ember project creator with my default addons:

- [Build Notifications][ember-cli-build-notifications]
- [Bundle Analyzer][ember-cli-bundle-analyzer]
- [Decorators][ember-decorators]
- [Mirage][ember-cli-mirage]
- [Mocha][ember-mocha] + [Chai][ember-cli-chai] + [Sinon][ember-sinon], including [chai-dom][chai-dom] and [sinon-chai][sinon-chai] matchers
- [Simple Auth][ember-simple-auth] preconfigured for OAuth2 password grant
- [Test Selectors][ember-test-selectors]

As well as the following:

- [babel-eslint][babel-eslint]
- [CircleCI][circleci] configuration
- [eslint-config-codingitwrong][eslint-config-codingitwrong]
- [Prettier][prettier] code formatter

## Requirements

- Yarn
- Ember CLI

## Installation

Clone the repo and add `emberup/bin` to your path.

## Usage

```bash
emberup myprojectname
```

## Manual Steps

The following steps must done manually after running `emberup`; they have not yet been scripted.

In `package.json` add the following script:

```
"format": "prettier --write \"{app,config,mirage,tests}/**/*.js\"",
```

In `config/environment.js`, add the following:

```diff
   if (environment === 'development') {
     // ENV.APP.LOG_RESOLVER = true;
     // ENV.APP.LOG_ACTIVE_GENERATION = true;
     // ENV.APP.LOG_TRANSITIONS = true;
     // ENV.APP.LOG_TRANSITIONS_INTERNAL = true;
     // ENV.APP.LOG_VIEW_LOOKUPS = true;
+    ENV['ember-cli-mirage'] = {
+      enabled: false,
+    };
+
+    ENV.apiHost = 'http://url.of.your.local.api';
   }
```

And:

```diff
   if (environment === 'production') {
     // here you can enable a production-specific feature
+    ENV.apiHost = 'https://url.of.your.production.api';
   }
```

## License

Apache-2.0

[babel-eslint]: https://github.com/babel/babel-eslint#babel-eslint---
[chai-dom]: https://github.com/nathanboktae/chai-dom
[circleci]: https://circleci.com/
[ember-cli-build-notifications]: https://github.com/pdud/ember-cli-build-notifications#readme
[ember-cli-bundle-analyzer]: https://github.com/kaliber5/ember-cli-bundle-analyzer
[ember-cli-chai]: https://github.com/ember-cli/ember-cli-chai#ember-cli-chai
[ember-cli-mirage]: https://ember-cli-mirage.com
[ember-mocha]: https://github.com/emberjs/ember-mocha
[ember-decorators]: https://ember-decorators.github.io/ember-decorators/docs/index.html
[ember-simple-auth]: http://ember-simple-auth.com/
[ember-sinon]: https://github.com/csantero/ember-sinon#ember-sinon
[ember-test-selectors]: https://github.com/simplabs/ember-test-selectors
[eslint-config-codingitwrong]: https://github.com/CodingItWrong/eslint-config-codingitwrong
[prettier]: https://prettier.io/
[sinon-chai]: https://github.com/domenic/sinon-chai#sinonjs-assertions-for-chai
