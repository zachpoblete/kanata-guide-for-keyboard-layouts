# Key Names for the `defsrc` and `deflayer` Entries

The following `defsrc` entry lists key names you can use in the `defsrc` and `deflayer` entries. For a legend, see this page’s [Legend of the key names](#legend-of-the-key-names).

```
(defsrc
  esc  f1   f2   f3   f4   f5   f6   f7   f8   f9   f10  f11  f12        prtsc slck  pause
  `    1    2    3    4    5    6    7    8    9    0    -    =    bspc  ins   home  pgup   nlck kp/  kp*  kp-
  tab  q    w    e    r    t    y    u    i    o    p    [    ]    \     del   end   pgdn   kp7  kp8  kp9  kp+
  caps a    s    d    f    g    h    j    k    l    ;    '    ent                           kp4  kp5  kp6
  lsft z    x    c    v    b    n    m    ,    .    /    rsft                  ↑            kp1  kp2  kp3  kprt
  lctl lmet lalt           spc            ralt rmet menu rctl            ←     ↓     →      kp0       kp.
)
```

For other keys, see this page’s [How to get the name of a key](#how-to-get-the-name-of-a-key).

## Legend of the key names

#### In this section

-   [Alpha keys and number keys](#alpha-keys-and-number-keys)
-   [General keys](#general-keys)
-   [Modifier keys](#modifier-keys)
-   [Function keys](#function-keys)
-   [Cursor control keys](#cursor-control-keys)
-   [Numpad keys](#numpad-keys)
-   [Other keys](#other-keys)

### Alpha keys and number keys

| Key name | Key
| -        | -
| `a`&NoBreak;&hairsp;&NoBreak;&ndash;&hairsp;`z` | <kbd>A</kbd>&NoBreak;&hairsp;&NoBreak;&ndash;&hairsp;<kbd>Z</kbd>
| `0`&NoBreak;&hairsp;&NoBreak;&ndash;&hairsp;`9` | <kbd>0</kbd>&NoBreak;&hairsp;&NoBreak;&ndash;&hairsp;<kbd>9</kbd>

### General keys

| Key name | Key
| -        | -
| `spc`    | <kbd>Space</kbd>
| `bspc`   | <kbd>Backspace</kbd>
| `tab`    | <kbd>Tab</kbd>
| `ent`    | <kbd>Enter</kbd>
| `caps`   | <kbd>Caps Lock</kbd>

### Modifier keys

| Key name | Key
| -        | -
| `lsft`   | <kbd>Left Shift</kbd>
| `rsft`   | <kbd>Right Shift</kbd>
| `lctl`   | <kbd>Left Control</kbd>
| `rctl`   | <kbd>Right Control</kbd>
| `lalt`   | <kbd>Left Alt</kbd> (or <kbd>Left Option</kbd> on macOS)
| `ralt`   | <kbd>Right Alt</kbd> or <kbd>AltGr</kbd> (or <kbd>Right Option</kbd> on macOS)
| `lmet`   | <kbd>Left Windows</kbd> (or <kbd>Left Super</kbd> on Linux, or <kbd>Left Command</kbd> on macOS)
| `rmet`   | <kbd>Right Windows</kbd> (or <kbd>Right Super</kbd> on Linux, or Right Command on macOS)

### Function keys

| Key name | Key
| -        | -
| `f1`&NoBreak;&hairsp;&NoBreak;&ndash;&hairsp;`f12` | <kbd>F1</kbd>&NoBreak;&hairsp;&NoBreak;&ndash;&hairsp;<kbd>F12</kbd>

### Cursor control keys

| Key name | Key
| -        | -
| `↑`      | <kbd>↑ Up</kbd>
| `↓`      | <kbd>↓ Down</kbd>
| `←`      | <kbd>← Left</kbd>
| `→`      | <kbd>→ Right</kbd>
| `slck`   | <kbd>Scroll Lock</kbd>
| `home`   | <kbd>Home</kbd>
| `end`    | <kbd>End</kbd>
| `pgup`   | <kbd>Page Up</kbd>
| `pgdn`   | <kbd>Page Down</kbd>
| `del`    | <kbd>Delete</kbd>
| `ins`    | <kbd>Insert</kbd>

### Numpad keys

| Key name | Key
| -        | -
| `kp0`&NoBreak;&hairsp;&NoBreak;&ndash;&hairsp;`kp9` | <kbd>Numpad 0</kbd>&NoBreak;&hairsp;&NoBreak;&ndash;&hairsp;<kbd>Numpad 9</kbd>
| `kp.`    | <kbd>Numpad .</kbd>
| `nlck`   | <kbd>Num Lock</kbd>
| `kp/`    | <kbd>Numpad /</kbd>
| `kp*`    | <kbd>Numpad *</kbd>
| `kp-`    | <kbd>Numpad -</kbd>
| `kp+`    | <kbd>Numpad +</kbd>
| `kprt`   | <kbd>Numpad Enter</kbd>

### Other keys

| Key name | Key
| -        | -
| `menu`   | <kbd>Menu</kbd>
| `prtsc`  | <kbd>Print Screen</kbd>
| `pause`  | <kbd>Pause</kbd>

## How to get the name of a key

1.  Open [JavaScript Key Code Event Tool](https://www.toptal.com/developers/keycode).

1.  Press the key. **event.code** shows the key name to use in the `defsrc` and `deflayer` entries.

1.  If **event.code** is blank, see [Kanata’s `mod.rs` file](https://github.com/jtroo/kanata/blob/main/parser/src/keys/mod.rs). The functions `str_to_oscode` and `add_default_str_osc_mappings` in that file are the source of truth for all key names.
