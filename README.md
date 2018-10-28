# dbc

A design-by-contract system for [zepto](https://github.com/zepto-lang/zepto).
Built for an upcoming blog post on Scheme macros. Inspired by [ds2643’s
implementation in Common Lisp](https://github.com/ds2643/dbc).

## Usage

This is an overly simple design-by-contract system expressed in a single macro.
It understands pre- and post-conditions. Its syntax looks a little like that:

```scheme
(defcontract (double xs)
  (pre (list? xs) (all? number? xs))
  (post (list? *ret*) (all? number? *ret*))
  (map (lambda (x) (* x 2)) xs))
```

The variable `*ret*` is the return value of the function, and it’s available for
all post-conditions.

For more information about what it is and how to build something like this
yourself, [stay tuned for the blog post](//blog.veitheller.de/scheme-macros)!
