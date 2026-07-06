# Basics of a Kanata Config

This page covers what you need to know to edit a Kanata config.

### On this page

-   [The `defsrc` and `deflayer` entries](#the-defsrc-and-deflayer-entries)
-   [Comments](#comments)
-   [Lists](#lists)
-   [Actions](#actions)
-   [Aliases](#aliases)
-   [Variables](#variables)
-   [Layers](#layers)

## The `defsrc` and `deflayer` entries

The [example config](../configs/example-config.kbd) shows the two required entries of a config, `defsrc` and `deflayer`:

```
(defsrc
  q w e r t  y u i o p
  a s d f g  h j k l ; '
  z x c v b  n m , . /
)

(deflayer gallium
  b l d c v  j f o u ,
  n r t s g  y h a e i /
  x q m w z  k p ' ; .
)
```

The `defsrc` entry lists the physical keys of your keyboard.

The `deflayer` entry creates a keyboard layer named `gallium`.

**How Kanata remaps your keyboard**: Kanata remaps each physical key in the `defsrc` entry to a key or action in the same position in the `gallium` layer. For example, Kanata remaps `q` in the `defsrc` entry to `b` in the `gallium` layer.

## Comments

Kanata ignores comments.

Comments are prefixed with two semicolons `;;`&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example:

```
;; This is a comment.

(defsrc
  caps a s d f  ;; Comments can be added to the end of a line.
)
```

## Lists

A config is made of lists.

Lists have the form `(item1 item2 item3 ...)`. The parentheses `()` group related items together. Items are separated by whitespace.

Usually, the 1st item is a command and the rest are arguments, such as in the `defsrc` and `deflayer` entries.

## Actions

An action lets you go beyond remapping a key to a different key.

The following example maps `Caps Lock` to the [`tap-hold` action](https://jtroo.github.io/config.html#tap-hold), letting you activate `Left Control` by holding `Caps Lock`:

```
(defsrc
  caps a s d f
)

(deflayer example
  (tap-hold 200 200 caps lctl) a s d f
)
```

## Aliases

An alias is a named shortcut for an action.

Aliases are defined in a `defalias` entry:

```
(defalias
  alias1-name alias1-action
  alias2-name alias2-action
  ...
)
```

A `defalias` entry is made of consecutive pairs of items. The 1st item in a pair is the name of an alias and the 2nd item is the action the alias maps to.

To use an alias, prefix the alias name with `@`.

The following example uses an alias for the `tap-hold` action:

```
(defalias caps
  (tap-hold 200 200 caps lctl)
)

(deflayer example
  @caps a s d f
)
```

Aliases let you visually align the `defsrc` and `deflayer` entries, making your config easier to read and maintain. The following example uses an alias to align the `defsrc` and `deflayer` entries:

```
(defsrc
   caps a s d f
)

(deflayer example
  @caps a s d f
)
```

## Variables

A variable is a named shortcut for a string or list.

Variables are defined in a `defvar` entry:

```
(defvar
  variable1-name variable1-value
  variable2-name variable2-value
  ...
)
```

A `defvar` entry is made of consecutive pairs of items. The 1st item in a pair is the name of a variable and the 2nd item is the value the variable maps to.

To use a variable, prefix the variable name with `$`.

The following example uses variables for the numbers in the `tap-hold` action:

```
(defvar
  tap-time  200
  hold-time 200
)

(defalias caps
  (tap-hold $tap-time $hold-time caps lctl)
)
```

## Layers

A layer is a keyboard layout that you can activate. The first layer that you define is the starting layer.

To change the active layer, use the [`layer-switch` action](https://jtroo.github.io/config.html#layer-switch) or the [`layer-while-held` action](https://jtroo.github.io/config.html#layer-while-held).

The [`deflayer` entry](#the-defsrc-and-deflayer-entries) is one way to define a layer. An alternative is the [`deflayermap` entry](https://github.com/jtroo/kanata/blob/main/docs/config.adoc#deflayermap).
