eslint-config-braintree
===

Shared linting configuration for braintree js projects.

- [index.js](./index.js): shared configuration
- [client.js](./client.js): client side configuration
- [server.js](./server.js): server side configuration

Consuming
---

Install the eslint config

```bash
npm i -D eslint-config-braintree
```

In your project's `.eslintrc.*` (below is yaml):

__default__
```yaml
---
extends: braintree
```

__browserify__
```yaml
---
extends: braintree/client
```

__node__
```yaml
---
extends: braintree/server
```

__browserify + es6__
```yaml
---
extends:
  - braintree/client
  - braintree/es6
```

You can specify a `.eslintrc` for a subdirectory to change the rules that are enforced. For instance, in a node project you could extend from `eslint-config-braintree/server` at the top-level, and `eslint-braintree-config/client` at the `public/.eslintrc` level.

See [Configuration File Formats](https://eslint.org/docs/user-guide/configuring#configuration-file-formats) for information on all supported `.eslintrc` file formats.

To override rules, add the new config under `rules` in your rc file. Be sure to properly override any options set by the parent. See [Extending Configuration Files](https://eslint.org/docs/user-guide/configuring#extending-configuration-files) for details.

For exmaple, to change the `no-extra-parens` rule to warn instead of error:

```yaml
---
extends: braintree/server
rules:
  no-extra-parens: 1
```

In another example, to allow end of line comments, you'd override the `'no-multi-spaces': [2, {"ignoreEOLComments": true}]` rule options:

```yaml
---
extends: braintree/server
rules:
  no-multi-spaces:
    - 2
    - ignoreEOLComments: false
```

