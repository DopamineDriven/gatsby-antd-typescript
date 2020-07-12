# gatsby-antd-typescript

## tsconfig.json

- Module

  - Module defines the output module resolution system that is used. For example, if you would use “es2015” here, it would assume that your Javascript engine is capable of parsing es2015 import statements (e.g. this would fail in Node.js 8). If you would set this to “commonjs”, it would export the module using the exports property (and therefore would run in e.g. Node.js 8). I keep this set to “commonjs” for my purposes.

- ModuleResolution

  - This configures how the compiler tries to find your modules (resolve them). There are two strategies for doing so: classic or node. I set this to node because I am used to how node resolves modules. Node is now Typescript’s default mode of module resolution, i.e. classic is mostly present for backwards compatibility.

- Target

  - Target is related to the output of your code, i.e. the compiled code targets a specific language variant. If you specify ES5 (not to be confused with ES2015), the compiled code can be run by ES5-compliant browsers and engines like Node. If you specify ES6 (== ES2015), the compiled code cannot be run by browsers or engines that do not yet support ES6 (ES2015) features. I set this to “es2015” because I am running my compiled code on AWS Lambda, which runs Node.js 8 and supports most es2015 features.

- Lib

  - Also related to the output of your code, this tells the compiler which language features are available when the compiled code is run. In most cases this would be the same as “target”, except if you polyfilled the runtime environment. For example, you might have polyfilled the Promise class in an ES5 environment.

* Note that as opposed to Babel, Typescript does not actually down-compile all language features such as Promises. It does down-compile a few language constructs (rather than APIs), such as async/await.
