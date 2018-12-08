A rule that disallows a rescued exception that get shadowed by a
less specific exception being rescued before a more specific
exception is rescued.

For example, this is invalid:

```
begin
  do_something
rescue Exception
  handle_exception
rescue ArgumentError
  handle_argument_error_exception
end
```

And it has to be written as follows:

```
begin
  do_something
rescue ArgumentError
  handle_argument_error_exception
rescue Exception
  handle_exception
end
```

YAML configuration example:

```
Lint/ShadowedException:
  Enabled: true
```
