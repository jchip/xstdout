# xstdout

capture stdout

# Usage

Example:

```js
const xstdout = require("xstdout");

const intercept = xstdout.intercept(true);

console.log("hello, world");

intercept.restore();

expect(intercept.stdout[0]).to.equal("hello, world\n");
```

## APIs

### `xstdout.intercept(silent, [silentErr])`

Returns an object:

```js
{
  restore,
  stdout,
  stderr
}
```

-   `stdout`/`stderr` are arrays of strings that captured stdout/stderr
-   `restore` is a function that restores the original stdout/stderr

#### Params

-   `silent` - if `true`, then omit actual output to console and only capture
-   `silentErr` - if not `undefined`, then independently controls output of stderr to console
