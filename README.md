# rollup-plugin-dmnlint

[![Build Status](https://travis-ci.com/bpmn-io/rollup-plugin-dmnlint.svg?branch=master)](https://travis-ci.com/bpmn-io/rollup-plugin-dmnlint)

Convert [dmnlint](https://github.com/bpmn-io/dmnlint) config files to consumable modules.

```javascript
import { Linter } from 'dmnlint';

import linterConfig from './.dmnlintrc';

const linter = new Linter(linterConfig);
```


## Installation

```sh
npm i rollup-plugin-dmnlint -D
```

## Usage

```js
import { rollup } from 'rollup';

import dmnlint from 'rollup-plugin-dmnlint';

import nodeResolve from 'rollup-plugin-node-resolve';
import commonjs from 'rollup-plugin-commonjs';

rollup({
  input: 'main.js',
  plugins: [
    nodeResolve(),
    commonjs(),
    dmnlint({
      // matching .dmnlintrc files per default
      include: '**/.dmnlintrc',

      // undefined per default
      exclude: [ ]
    })
  ]
});
```

## Credits

The project is based on [`rollup-plugin-bpmnlint`](https://github.com/nikku/rollup-plugin-bpmnlint) built by [nikku](https://github.com/nikku).

## License

MIT
