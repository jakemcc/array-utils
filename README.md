# array-utils

`array-utils` is inspired by Prismatic's slides on their
yet-to-be-released Flop library. Do you need the raw speed of
primitive Java doubles, but find them hard and inexpressive? Sick of
reflection and type-hints? This is for you.

Includes higher-order functions like `amap`, `asum`, and `afill!`
(in-place map). The functions require little or no manual type hinting
and support binding semantics similar to for-each.

## Usage

Pull the repo, run `lein deps`, and require `array-utils.core`. 

## Motivation

Instead of 

```clojure
(defn dot-product [^doubles ws ^doubles xs]
  (areduce xs i ret 0.0
    (+ ret (* (aget xs i)
              (aget ws i))))
```

you can write

```clojure
(defn dot-product [ws xs] (asum [x xs w ws] (* x w)))
```

See `src/array-utils/example.clj` for more.

## Documentation

See the docstrings. Generate the HTML documentation by running `lein marg`.

## License

Copyright © 2013 Emil Flakk

Distributed under the Eclipse Public License, the same as Clojure.
