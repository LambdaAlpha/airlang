# Initial Context

In the initial context, key-value bindings are mutable.

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
- `move`: .map.move
- `quote`: .quote.make
- `call`: .call.make
- `exist`: .config.exist
- `import`: .config.import
- `export`: .config.export
- `with`: .config.with
- `function`: .function.make
- `get`: .context.get
- `set`: .context.set
- `represent`: .context.represent
- `which`: .context.which
- `do`: .control.do
- `test`: .control.test
- `switch`: .control.switch
- `match`: .control.match
- `loop`: .control.loop
- `iterate`: .control.iterate
- `get_type`: .value.get_type
- `=`: .value.equal
- `abort`: .error.abort,
- `assert`: .error.assert,
- `eval`: .language.semantics.eval

## Other

- `empty : ''`
- `return : .(.)`
- `continue : .(.)`
- `break : .(.(.))`
