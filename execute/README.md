# Execute template

Adds a template for each `execute` sub-command, letting you drop the leading `execute` keyword and attach a `{ ... }` block directly, without needing to write `run` yourself.

## Installing

Add the `execute.mcbt` file to your `src` folder.

## Usage

Each sub-command can be called like a normal command, ending in `run <command>`:

```mcb
align xyz run say hello
```

```mcb
# Equivalent to
execute align xyz run say hello
```

Or with a `{ ... }` block, in which case `run` is optional and will be added automatically:

```mcb
align xyz {
	say hello
}

# Equivalent to
align xyz run {
	say hello
}
```

Since the arguments are passed through as raw text, sub-commands can be chained together just like vanilla `execute`:

```mcb
if score #check0 v matches 0 \
	if score #check1 v matches 0 \
	align xyz positioned ~.5 ~ ~.5 \
	facing entity @s eyes \
run {
	say "Hello, World!"
}
```

## Supported sub-commands

- `align <axes>`
- `anchored <anchor>`
- `as <targets>`
- `at <targets>`
- `facing ...`
- `in <dimension>`
- `on <relation>`
- `positioned ...`
- `rotated ...`
- `summon <entity>`
- `if ...`
- `unless ...`
- `store ...`

Each behaves exactly like its vanilla `execute` counterpart, e.g.:

```mcb
if entity @s {
	say I exist!
}

as @a[tag=test] at @s {
	say Hello!
}
```
