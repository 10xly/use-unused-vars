# use-unused-vars
Ever had a variable that ESLint or your code editor says is unused and yaps at you but it really isn't because you use it in some `eval`? To fix this, you might find this solution:
```js
function foo(bar) {
  bar // use bar
  eval("return bar + 1") // usage eslint doesnt realize
}
```
However, this is weird. Now, just use an npm package!
```js
const use = require("use-unused-vars")
function foo(bar) {
  use(bar)
  eval("return bar + 1")
}
```