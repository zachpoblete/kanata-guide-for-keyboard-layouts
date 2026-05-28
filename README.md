# Kanata Guide for Alt Layouts

[Kanata](https://github.com/jtroo/kanata) is a keyboard remapper for Windows, Linux, and macOS. It lets you use [alternate layouts](https://layouts.wiki/guides/start/intro/) on any keyboard and supports advanced features like layers, combos, and tap-hold.

This guide shows you how to set up Kanata, run it at startup, and change your layout.

The guide also explains key concepts for reading and editing Kanata configs. See the [example configs](#example-configs) to explore what Kanata can do.

## Set up Kanata

Expand the instructions for your operating system.

<!----------------------------------------------------------------------------->
<!-- Windows -->

<details>
<summary><strong>Windows</strong></summary>
<p></p>

1.  Download Kanata:

    -   Most users: [download the x64 version](https://github.com/jtroo/kanata/releases/latest/download/windows-binaries-x64.zip).
    -   ARM users: [download the arm64 version](https://github.com/jtroo/kanata/releases/download/v1.11.0/windows-binaries-arm64.zip).

1.  Extract the downloaded zip file. It contains the Kanata executable files.

1.  [Download the example config](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/example.kbd) and put it in the same folder as the Kanata executable files.

1.  Open the folder in a terminal.

    If you don’t know how, right-click an empty space inside the folder and select **Open in Terminal**.

1.  Run Kanata with the example config:

    -   x64:

        ```cmd
        .\kanata_windows_gui_winIOv2_cmd_allowed_x64.exe --cfg example.kbd
        ```

    -   arm64:

        ```cmd
        .\kanata_windows_gui_winIOv2_cmd_allowed_arm64.exe --cfg example.kbd
        ```

Your keyboard is now using the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite). Press your `q` key&hairsp;&mdash;&hairsp;its output is now `b`. Try other letters!

To stop Kanata, press the key combination `Left Control + Space + Escape`.

</details>

<!----------------------------------------------------------------------------->
<!-- Linux -->

<details>
<summary><strong>Linux</strong></summary>
<p></p>

1.  [Download Kanata](https://github.com/jtroo/kanata/releases/latest/download/linux-binaries-x64.zip).

1.  Extract the downloaded zip file. It contains the Kanata executable files.

1.  [Download the example config](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/example.kbd) and put it in the same folder as the Kanata executable files.

1.  Open the folder in a terminal.

    If you don’t know how, right-click an empty space inside the folder and select **Open in Terminal**.

1.  Run Kanata with the example config. The `chmod` command only needs to be run the first time.

    ```shell
    chmod +x kanata_linux_cmd_allowed_x64
    sudo ./kanata_linux_cmd_allowed_x64 --cfg example.kbd
    ```

Your keyboard is now using the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite). Press your `q` key&hairsp;&mdash;&hairsp;its output is now `b`. Try other letters!

To stop Kanata, press the key combination `Left Control + Space + Escape`.

</details>

<!----------------------------------------------------------------------------->
<!-- macOS 10 and older -->

<details>
<summary><strong>macOS 10 and older</strong></summary>
<p></p>

>   **⚠️ Warning**: It’s unclear whether the latest version of Kanata works with macOS 10 and older. Support for macOS 10 was added in [Kanata v1.6.0](https://github.com/jtroo/kanata/releases/tag/v1.6.0), so you may need to start there. Kanata has been [reported to work on macOS 10.15 Catalina](https://github.com/jtroo/kanata/issues/676#issuecomment-1868389437).

1.  Install the [Karabiner kernel extension](https://github.com/pqrs-org/Karabiner-VirtualHIDDevice-archived) for macOS 10. The [Kmonad instructions](https://github.com/kmonad/kmonad/blob/master/doc/installation.md#macos) for installing the kernel extension (kext) may be helpful.

1.  [Download Kanata](https://github.com/jtroo/kanata/releases/latest/download/macos-binaries-x64.zip).

    -   Note: This is the latest version.

1.  Extract the downloaded zip file. It contains the Kanata executable files.

1.  [Download the example config](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/example.kbd) and put it in the same folder as the Kanata executable files.

1.  Open the folder in a terminal.

    If you don’t know how, right-click an empty space inside the folder and select **Services → New Terminal at Folder**.
    -   If **New Terminal at Folder** doesn’t appear, click **Finder → Services → Services Settings → Files and Folders** and enable **New Terminal at Folder**.

1.  Run Kanata with the example config. The `chmod` command only needs to be run the first time.

    ```shell
    chmod +x kanata_macos_cmd_allowed_x64
    sudo ./kanata_macos_cmd_allowed_x64 --cfg example.kbd
    ```

Your keyboard is now using the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite). Press your `q` key&hairsp;&mdash;&hairsp;its output is now `b`. Try other letters!

To stop Kanata, press the key combination `Left Control + Space + Escape`.

**Troubleshooting**: See [Kanata’s setup guide](https://github.com/jtroo/kanata/blob/main/docs/setup-macos.md#8-troubleshooting).

</details>

<!----------------------------------------------------------------------------->
<!-- macOS 11 and 12 -->

<details>
<summary><strong>macOS 11 and 12</strong></summary>
<p></p>

>   **⚠️ Warning**: There was a [report of Kanata not working on macOS 11](https://github.com/jtroo/kanata/discussions/1242). (Presumably, the user was using Kanata v1.6.1 at the time.) Ben Vallack explains [how he installed Kanata on macOS 12](https://www.youtube.com/watch?v=4yiMbP_ZySQ&t=1m23s).

To use Kanata, you first need to set up the [Karabiner driver](https://github.com/pqrs-org/Karabiner-DriverKit-VirtualHIDDevice).

### Set up the Karabiner driver

1.  [Download Karabiner driver v3.1.0](https://github.com/pqrs-org/Karabiner-DriverKit-VirtualHIDDevice/releases/download/v3.1.0/Karabiner-DriverKit-VirtualHIDDevice-3.1.0.pkg) and run the installer.

1.  Open a terminal and activate the driver:

    ```shell
    sudo /Applications/.Karabiner-VirtualHIDDevice-Manager.app/Contents/MacOS/Karabiner-VirtualHIDDevice-Manager activate
    ```

    If you previously ran the `deactivate` command, restart your computer.

1.  Enable the Karabiner system extension: open **System Preferences → General → Login Items** and enable `org.pqrs.Karabiner-DriverKit-VirtualHIDDevice`.

1.  [Download the Karabiner plist file](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/org.pqrs.Karabiner-VirtualHIDDevice-Daemon.plist) and save it in the `/Library/LaunchDaemons` folder.

1.  In the terminal, load the Karabiner daemon:

    ```shell
    sudo chown root:wheel /Library/LaunchDaemons/org.pqrs.Karabiner-VirtualHIDDevice-Daemon.plist
    sudo launchctl bootstrap system /Library/LaunchDaemons/org.pqrs.Karabiner-VirtualHIDDevice-Daemon.plist
    ```

### Set up Kanata

1.  Download Kanata v1.7.0:

    -   If you’re on an Apple Silicon Mac, [download the arm64 executable file](https://github.com/jtroo/kanata/releases/download/v1.7.0/kanata_macos_cmd_allowed_arm64).
    -   If you’re on an Intel-based Mac, [download the x86_64 executable file](https://github.com/jtroo/kanata/releases/download/v1.7.0/kanata_macos_cmd_allowed_x86_64).

1.  Enable Accessibility: open **System Preferences → Privacy & Security → Accessibility** and add the Kanata executable file.

1.  Enable Input Monitoring: open **System Preferences → Privacy & Security → Input Monitoring** and add the Kanata executable file.

1.  [Download the example config](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/example.kbd) and put it in the same folder as the Kanata executable file.

1.  Open the folder in a terminal.

    If you don’t know how, right-click an empty space inside the folder and select **Services → New Terminal at Folder**.
    -   If **New Terminal at Folder** doesn’t appear, click **Finder → Services → Services Settings → Files and Folders** and enable **New Terminal at Folder**.

1.  Run Kanata with the example config. The `chmod` command only needs to be run the first time.

    -   arm64:

        ```shell
        chmod +x kanata_macos_cmd_allowed_arm64
        sudo ./kanata_macos_cmd_allowed_arm64 --cfg example.kbd
        ```

    -   x86_64:

        ```shell
        chmod +x kanata_macos_cmd_allowed_x86_64
        sudo ./kanata_macos_cmd_allowed_x86_64 --cfg example.kbd
        ```

Your keyboard is now using the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite). Press your `q` key&hairsp;&mdash;&hairsp;its output is now `b`. Try other letters!

To stop Kanata, press the key combination `Left Control + Space + Escape`.

**Troubleshooting**: See [Kanata’s setup guide](https://github.com/jtroo/kanata/blob/main/docs/setup-macos.md#8-troubleshooting).

</details>

<!----------------------------------------------------------------------------->
<!-- macOS 13 and newer -->

<details>
<summary><strong>macOS 13 and newer</strong></summary>
<p></p>

To use Kanata, you first need to set up the [Karabiner driver](https://github.com/pqrs-org/Karabiner-DriverKit-VirtualHIDDevice).

### Set up the Karabiner driver

1.  If [Karabiner Elements](https://karabiner-elements.pqrs.org/) is installed, disable its background processes: Open **System Settings → General → Login Items & Extensions**. In the **App Background Activity** section, disable the following if you see them:

    -   Disable **Karabiner-Elements Privileged Daemons**.
    -   Disable **Karabiner-Elements Privileged Daemons v2**.

1.  [Download Karabiner driver v6.2.0](https://github.com/pqrs-org/Karabiner-DriverKit-VirtualHIDDevice/releases/download/v6.2.0/Karabiner-DriverKit-VirtualHIDDevice-6.2.0.pkg) and run the installer.

1.  Open a terminal and activate the driver:

    ```shell
    sudo /Applications/.Karabiner-VirtualHIDDevice-Manager.app/Contents/MacOS/Karabiner-VirtualHIDDevice-Manager forceActivate
    ```

    If you previously ran `deactivate`, restart your computer.

1.  Enable the Karabiner system extension: Open **System Settings → General → Login Items & Extensions**. In the **Extensions** section, enable `org.pqrs.Karabiner-DriverKit-VirtualHIDDevice`.

1.  [Download the Karabiner plist file](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/org.pqrs.Karabiner-VirtualHIDDevice-Daemon.plist) and save it in the `/Library/LaunchDaemons` folder.

1.  In the terminal, load the Karabiner daemon:

    ```shell
    sudo chown root:wheel /Library/LaunchDaemons/org.pqrs.Karabiner-VirtualHIDDevice-Daemon.plist
    sudo launchctl bootstrap system /Library/LaunchDaemons/org.pqrs.Karabiner-VirtualHIDDevice-Daemon.plist
    ```

### Set up Kanata

1.  Download Kanata:

    -   If you’re on an Apple Silicon Mac (most users), [download the arm64 version](https://github.com/jtroo/kanata/releases/latest/download/macos-binaries-arm64.zip).
    -   If you’re on an Intel-based Mac, [download the x64 version](https://github.com/jtroo/kanata/releases/latest/download/macos-binaries-x64.zip).

1.  Extract the downloaded zip file. It contains the Kanata executable files.

1.  Enable Accessibility: open **System Settings → Privacy & Security → Accessibility** and add the Kanata executable file whose filename starts with `kanata_macos_cmd_allowed_`.

1.  Enable Input Monitoring: open **System Settings → Privacy & Security → Input Monitoring** and add the same Kanata executable file.

1.  [Download the example config](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/example.kbd) and put it in the same folder as the Kanata executable files.

1.  Open the folder in a terminal.

    If you don’t know how, right-click an empty space inside the folder and select **Services → New Terminal at Folder**.
    -   If **New Terminal at Folder** doesn’t appear, click **Finder → Services → Services Settings → Files and Folders** and enable **New Terminal at Folder**.

1.  Run Kanata with the example config. The `chmod` command only needs to be run the first time.

    -   arm64:

        ```shell
        chmod +x kanata_macos_cmd_allowed_arm64
        sudo ./kanata_macos_cmd_allowed_arm64 --cfg example.kbd
        ```

    -   x64:

        ```shell
        chmod +x kanata_macos_cmd_allowed_x64
        sudo ./kanata_macos_cmd_allowed_x64 --cfg example.kbd
        ```

Your keyboard is now using the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite). Press your `q` key&hairsp;&mdash;&hairsp;its output is now `b`. Try other letters!

To stop Kanata, press the key combination `Left Control + Space + Escape`.

**Troubleshooting**: See [Kanata’s setup guide](https://github.com/jtroo/kanata/blob/main/docs/setup-macos.md#8-troubleshooting).

</details>

## Run Kanata at startup

Expand the instructions for your operating system.

<!----------------------------------------------------------------------------->
<!-- Windows -->

<details>
<summary><strong>Windows</strong></summary>
<p></p>

1.  Create a shortcut of the Kanata executable file: hold the `Alt` key and drag the file anywhere inside the folder.

1.  Move the shortcut to the startup folder: `%AppData%\Microsoft\Windows\Start Menu\Programs\Startup`.

1.  Right-click the shortcut and select **Properties**.

1.  Append the following arguments to the **Target** field:

    <pre>
     --cfg "<var>KANATA_CONFIG_PATH</var>" --nodelay
    </pre>

    Replace _`KANATA_CONFIG_PATH`_ with the path to the Kanata config file.

    The full target will look like:

    <pre>
    "<var>KANATA_EXECUTABLE_PATH</var>" --cfg "<var>KANATA_CONFIG_PATH</var>" --nodelay
    </pre>

1. Click **OK**.

Your Kanata config will now run in the background at startup.

</details>

<!----------------------------------------------------------------------------->
<!-- Linux -->

<details>
<summary><strong>Linux</strong></summary>
<p></p>

1.  [Download the Kanata service file](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/kanata.service) and save it in the `/etc/systemd/system/` folder.

1.  Open the `kanata.service` file with a text editor.

1.  Edit the `ExecStart` line:

    <pre>
    ExecStart=<var>KANATA_EXECUTABLE_PATH</var> -c <var>KANATA_CONFIG_PATH</var> --nodelay
    </pre>

    Replace the following:

    -   _`KANATA_EXECUTABLE_PATH`_: the path to the Kanata executable file
    -   _`KANATA_CONFIG_PATH`_: the path to the Kanata config file

1. Save the file.

1.  Open a terminal and enable the service:

    ```shell
    sudo systemctl enable kanata.service
    ```

Your Kanata config will now run in the background at startup.

</details>

<!----------------------------------------------------------------------------->
<!-- macOS -->

<details>
<summary><strong>macOS</strong></summary>
<p></p>

1.  [Download the Kanata plist file](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/dev.kanata.kanata.plist) and save it in the `/Library/LaunchDaemons` folder.

1.  Open the `dev.kanata.kanata.plist` file with a text editor.

1.  Edit the `ProgramArguments` key:

    <pre>
    &lt;key&gt;ProgramArguments&lt;/key&gt;
    &lt;array&gt;
        &lt;string&gt;<var>KANATA_EXECUTABLE_PATH</var>&lt;/string&gt;
        &lt;string&gt;--cfg&lt;/string&gt;
        &lt;string&gt;<var>KANATA_CONFIG_PATH</var>&lt;/string&gt;
        &lt;string&gt;--nodelay&lt;/string&gt;
    &lt;/array&gt;
    </pre>

    Replace the following:

    -   _`KANATA_EXECUTABLE_PATH`_: the path to the Kanata executable file
    -   _`KANATA_CONFIG_PATH`_: the path to the Kanata config file

1. Save the file.

1.  Open a terminal and load the Kanata daemon:

    ```shell
    sudo chown root:wheel /Library/LaunchDaemons/dev.kanata.kanata.plist
    sudo launchctl bootstrap system /Library/LaunchDaemons/dev.kanata.kanata.plist
    ```

Your Kanata config will now run in the background at startup.

</details>

## Change your layout

The `example.kbd` config consists of two parts, `defsrc` and `deflayer`:

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

-   `defsrc` defines your keyboard’s original layout. The configs in this guide use the [US keyboard](configs/us-keyboard.kbd) for `defsrc`. If you use a different keyboard, see [Non-US keyboards](https://jtroo.github.io/config.html#non-us-keyboards) and [Keyboard locales](https://github.com/jtroo/kanata/blob/main/docs/locales.adoc).

-   `deflayer` defines a keyboard layer. In the preceding config, `deflayer` creates the `gallium` layer, remapping your keyboard to the Gallium layout.

Kanata works by mapping keys from `defsrc` to `deflayer` position-by-position.

Use the [Sturdy layout](https://layouts.wiki/guides/start/recommendations/#sturdy):

1. Open the `example.kbd` config with a text editor.

1. Replace the contents with the following config:

    ```
    (defsrc
      q w e r t  y u i o p
      a s d f g  h j k l ; '
      z x c v b  n m , . /
    )

    (deflayer sturdy
      v m l c p  x f o u j
      s t r d y  . n a e i /
      z k q g w  b h ' ; ,
    )
    ```

1. Save the file.

1. Run Kanata with the `example.kbd` config again.

Press your `q` key. Its output is now `v`.

To use a different layout, edit the keys in `deflayer` (and rename the layer to match).

>   [!TIP]
>   To quickly try new layouts, use the <code>!&NoBreak;cmini view [layout]</code> command in the [Alt Keyboard Layouts Discord](https://discord.gg/4kVZu7uWdy). This returns a text version of the layout that you can copy into `deflayer`.

## More config concepts

[Change your layout](#change-your-layout) explains `defsrc` and `deflayer`.

The following concepts will help you read and edit the [example configs](#example-configs).

**Lists** make up configs.

<ul>

Most lists have the form `(command argument1 argument2 ...)`. Think of the parentheses `()` as grouping related items together.

The arguments can also be lists.

</ul>

**Comments** are prefixed with two semicolons `;;`.

<ul>

For example:

```
;; This is a comment.
;; Comments are ignored.

(defsrc
   caps a s d f  ;; This is an inline comment.
)
```

</ul>

**Actions** are what you bind to keys.

<ul>

Use the `tap-hold` action to make holding Caps Lock activate Left Control:

```
(defsrc
   caps a s d f
)

(deflayer example
  (tap-hold 200 200 caps lctl) a s d f
)
```

</ul>

**Aliases** are named shortcuts for actions.

<ul>

Defined in `defalias`, aliases are used by prefixing the alias name with `@`.

Use an alias for the `tap-hold` action from the previous example:

```
(defsrc
   caps a s d f
)

(deflayer example
  @caps a s d f
)

(defalias caps
  (tap-hold 200 200 caps lctl)
)
```

You can define multiple aliases in a single `defalias`:

```
(defalias
  a (tap-hold 200 200 a lmet)
  s (tap-hold 200 200 s lalt)
  d (tap-hold 200 200 d lsft)
  f (tap-hold 200 200 f lctl)
)
```

Similar lists items like `defvar` can also define multiple variables.

</ul>

**Variables** are named shortcuts for strings or lists.

<ul>

Defined in `defvar`, variables are used by prefixing the variable name with `$`.

Use variables for the `200 200` parameters from the previous examples:

```
(defvar
  tap-time  200
  hold-time 200
)

(defsrc
   caps a s d f
)

(deflayer example
  @caps a s d f
)

(defalias caps
  (tap-hold $tap-time $hold-time caps lctl)
)
```

</ul>

You now have a good grasp of the tools used in almost every config.

## Example configs

To learn about any Kanata feature used in a config, see the [Configuration Guide](https://jtroo.github.io/config.html).

<a name="general-configs"></a>
<strong>General configs</strong>

-   [`backtick-switches-layouts.kbd`](configs/backtick-switches-layouts.kbd)
    -   Holding the backtick `` ` `` key toggles between your alt layout and QWERTY
-   [`qwerty-shortcuts.kbd`](configs/qwerty-shortcuts.kbd)
    -   Holding the `Control`, `Alt`, or `Super` keys temporarily switches to QWERTY
-   [`home-row-mods.kbd`](configs/home-row-mods.kbd)
    -   Layout with [home row mods](https://getreuer.info/posts/keyboards/tour/index.html#home-row-mods)
-   [`qwerty-home-row-mods.kbd`](configs/qwerty-home-row-mods.kbd)
    -   Layout with home row mods that temporarily switch to QWERTY
-   [`symbol-layer.kbd`](configs/symbol-layer.kbd)
    -   Layer for symbol keys
-   [`navigation-layer.kbd`](configs/navigation-layer.kbd)
    -   Layer for navigation keys

<a name="layouts"></a>
<strong>Layouts</strong>

-   [`graphite.kbd`](configs/graphite.kbd)
    -   Layout with nonstandard shift pairs
-   [`night.kbd`](configs/night.kbd)
    -   Layout with a [thumb alpha key](https://layouts.wiki/guides/start/recommendations/#thumb-alpha)
-   [`gallium-angle.kbd`](configs/gallium-angle.kbd)
    -   Layout that has been [angle modded](https://colemakmods.github.io/ergonomic-mods/angle.html)
-   [`night-wide.kbd`](configs/night-wide.kbd)
    -   Layout that has been [wide modded](https://colemakmods.github.io/ergonomic-mods/wide.html)
-   [`night-double-wide.kbd`](configs/night-double-wide.kbd)
    -   Layout that has been double-wide modded
-   [`nokwts.kbd`](configs/nokwts.kbd)
    -   Layout that uses the [Nokwts fingermap](https://discord.com/channels/807843650717483049/1063291226243207268/1339406872666439752)

<a name="advanced-layouts"></a>
<strong>Advanced layouts</strong>

-   [`lucens.kbd`](configs/lucens.kbd)
    -   Layout with a second layer for typing German letters
-   [`compose.kbd`](configs/compose.kbd)
    -   Layout with a [compose key](https://en.wikipedia.org/wiki/Compose_key)
-   [`gallium-with-combos.kbd`](configs/gallium-with-combos.kbd)
    -   Layout with combos
-   [`2-row-gallium.kbd`](configs/2-row-gallium.kbd)
    -   Layout with only two rows
-   [`taipo.kbd`](configs/taipo.kbd)
    -   Layout that can be used one-handed
-   [`crescent.kbd`](configs/crescent.kbd)
    -   Layout with only 10 keys, one for each finger
-   [`nastic.kbd`](configs/nastic.kbd)
    -   Layout with repeated keys
-   [`whirl.kbd`](configs/whirl.kbd)
    -   Layout with a [magic key](https://layouts.wiki/reference/terminology/magic/)
-   [`afterburner.kbd`](configs/afterburner.kbd)
    -   Layout with a skip magic key
-   [`nordrassil.kbd`](configs/nordrassil.kbd)
    -   Layout with chiral magic keys
-   [`d5.kbd`](configs/d5.kbd)
    -   Layout with chiral skip magic keys
-   [`adaptive-sturdy.kbd`](configs/adaptive-sturdy.kbd)
    -   Layout with [adaptive keys](https://dario.ca/posts/2026-05-18-keyboard-layout-adaptive-swaps/)
-   [`buggy.kbd`](configs/buggy.kbd)
    -   Layout with two alpha layers
-   [`power.kbd`](configs/power.kbd)
    -   Layout with 162 layers

## Reference links

-   [Kanata Configuration Guide](https://jtroo.github.io/config.html)
-   [List of known Kanata issues](https://github.com/jtroo/kanata/blob/main/docs/platform-known-issues.adoc)
-   [Key names for `defsrc` and `deflayermap`](https://jtroo.github.io/config.html#key-names)
-   [Windows: enable Kanata in elevated windows](https://jtroo.github.io/config.html#windows-only-work-elevated)
-   [VS Code: Kanata language support](https://github.com/rszyma/vscode-kanata)

## Feedback

If anything in the guide is unclear or doesn’t work, please open an [issue](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/issues) or message me (@novachromatic) on the [Alt Keyboard Layouts Discord](https://discord.gg/4kVZu7uWdy).

Suggestions appreciated!
