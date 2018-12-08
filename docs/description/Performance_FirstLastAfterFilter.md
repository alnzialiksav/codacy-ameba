This rule is used to identify usage of `first/last/first?/last?` calls that follow filters.

For example, this is considered inefficient:

```
[-1, 0, 1, 2].select { |e| e > 0 }.first?
[-1, 0, 1, 2].select { |e| e > 0 }.last?
```

And can be written as this:

```
[-1, 0, 1, 2].find { |e| e > 0 }
[-1, 0, 1, 2].reverse_each.find { |e| e > 0 }
```

YAML configuration example:

```
Performance/FirstLastAfterFilter
  Enabled: true
  FilterNames:
    - select
```
