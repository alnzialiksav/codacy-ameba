A rule that disallows comparison to booleans.

For example, these are considered invalid:

```
foo == true
bar != false
false === baz
```

This is because these expressions evaluate to `true` or `false`, so you
could get the same result by using either the variable directly,
or negating the variable.

YAML configuration example:

```
Lint/ComparisonToBoolean:
  Enabled: true
```
