# Initial Context

In the initial context, key-value bindings are mutable.

## Primitive Function

- `not`: .bit.not
- `and`: .bit.and
- `or`: .bit.or
- `xor`: .bit.xor
- `imply`: .bit.imply
- `+`: .integer.add
- `-`: .integer.subtract
- `*`: .integer.multiply
- `/`: .integer.divide
- `<`: .integer.less
- `<=`: .integer.less_equal
- `>`: .integer.greater
- `>=`: .integer.greater_equal
- `<>`: .integer.less_greater
- `+.`: .decimal.add
- `-.`: .decimal.subtract
- `*.`: .decimal.multiply
- `/.`: .decimal.divide
- `<.`: .decimal.less
- `<=.`: .decimal.less_equal
- `>.`: .decimal.greater
- `>=.`: .decimal.greater_equal
- `<>.`: .decimal.less_greater
- `quote`: .quote.make
- `call`: .call.make
- `solve`: .solve.make
- `fact`: .fact.make
- `exist`: .config.exist
- `import`: .config.import
- `export`: .config.export
- `with`: .config.with
- `function`: .function.make
- `get`: .context.get
- `take`: .context.take
- `set`: .context.set
- `is`: .context.is
- `let`: .context.let
- `do`: .control.do
- `then`: .control.then
- `branch`: .control.branch
- `match`: .control.match
- `loop`: .control.loop
- `each`: .control.each
- `=`: .value.equal
- `abort`: .error.abort,
- `assert`: .error.assert,
- `eval`: .language.semantics.eval

## Composite Function

- `type`: .value.get_type.context.let

## Other

- `empty : key''`
- `return : .(.)`
- `continue : .(.)`
- `break : .(.(.))`
