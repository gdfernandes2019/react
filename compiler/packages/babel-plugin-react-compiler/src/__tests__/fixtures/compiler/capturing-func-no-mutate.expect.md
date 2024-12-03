
## Input

```javascript
function Component({a, b}) {
  let z = {a};
  let y = {b};
  let x = function () {
    z.a = 2;
    return Math.max(y.b, 0);
  };
  x();
  return z;
}

export const FIXTURE_ENTRYPOINT = {
  fn: Component,
  params: [{a: 2, b: 3}],
  sequentialRenders: [
    {a: 2, b: 3},
    {a: 2, b: 3},
    {a: 4, b: 3},
    {a: 4, b: 5},
  ],
};

```

## Code

```javascript
import { c as _c } from "react/compiler-runtime";
function Component(t0) {
  const $ = _c(3);
  const { a, b } = t0;
  let z;
  if ($[0] !== a || $[1] !== b) {
    z = { a };
    const y = { b };
    const x = function () {
      z.a = 2;
      return Math.max(y.b, 0);
    };

    x();
    $[0] = a;
    $[1] = b;
    $[2] = z;
  } else {
    z = $[2];
  }
  return z;
}

export const FIXTURE_ENTRYPOINT = {
  fn: Component,
  params: [{ a: 2, b: 3 }],
  sequentialRenders: [
    { a: 2, b: 3 },
    { a: 2, b: 3 },
    { a: 4, b: 3 },
    { a: 4, b: 5 },
  ],
};

```
      
### Eval output
(kind: ok) {"a":2}
{"a":2}
{"a":2}
{"a":2}