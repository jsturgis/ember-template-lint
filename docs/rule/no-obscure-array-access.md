# no-obscure-array-access

Using obscure expressions `{{list.[1].name}}` is discouraged and is likely to be deprecated soon.

This rule recommends the use of Ember's `get` helper as an alternative for accessing array values.

## Examples

This rule **forbids** the following:

```hbs
{{foo bar=list.[0]}}
```

```hbs
{{foo bar @list.[1]}}
```

```hbs
<Foo @bar={{list.[0]}} />
```

This rule **allows** the following:

```hbs
{{foo bar=(get list '0'}}
```

```hbs
{{foo bar (get @list '1')}}
```

```hbs
<Foo @bar={{get list '0'}} />
```

## References

- [Ember discord discussion in ember-cli channel on 02/06/19](https://discord.com/channels/480462759797063690/486548111221719040)