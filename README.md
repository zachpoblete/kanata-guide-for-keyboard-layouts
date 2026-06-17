# Kanata Guide for Alt Layouts

This guide shows you how to use [Kanata](https://github.com/jtroo/kanata) to run an [alt layout](https://layouts.wiki/guides/start/intro/) on any keyboard. See the [Example configs](#example-configs) for adding features to an alt layout like QWERTY shortcuts, symbol layers, and magic keys.

You can use this guide even if you don’t have any programming experience.

### In this guide

-   [Supported platforms](#supported-platforms)
-   [Step 1: Set up Kanata](#step-1-set-up-kanata)
-   [Step 2: Run an alt layout](#step-2-run-an-alt-layout)
-   [Step 3: Change your layout](#step-3-change-your-layout)
-   [Run your layout automatically when you log in](#run-your-layout-automatically-when-you-log-in)
-   [Example configs](#example-configs)

## Supported platforms

-   Windows 11
-   Linux
-   macOS 13 or newer

Older versions of Windows and macOS are not officially supported by this guide.

## Step 1: Set up Kanata

Expand the section for your operating system.

<!----------------------------------------------------------------------------->
<!-- Windows -->

<details>
<summary><strong>Windows</strong></summary>
<p></p>

1.  Download Kanata.

    Kanata has two versions, one for x64 processors and one for arm64 processors. To check what processor your computer uses, see this guide’s [Check what processor your computer uses](#check-what-processor-your-computer-uses).

    -   If your computer uses an **x64** processor, [download the x64 version of Kanata](https://github.com/jtroo/kanata/releases/latest/download/windows-binaries-x64.zip).
    -   If your computer uses an **arm64** processor, [download the arm64 version of Kanata](https://github.com/jtroo/kanata/releases/download/v1.11.0/windows-binaries-arm64.zip).

1.  Extract the downloaded zip file. The filenames of the Kanata executable files start with `kanata_windows_`.

</details>

<!----------------------------------------------------------------------------->
<!-- Linux -->

<details>
<summary><strong>Linux</strong></summary>
<p></p>

1.  [Download Kanata](https://github.com/jtroo/kanata/releases/latest/download/linux-binaries-x64.zip).

1.  Extract the downloaded zip file. The filenames of the Kanata executable files start with `kanata_linux_`.

</details>

<!----------------------------------------------------------------------------->
<!-- macOS -->

<details>
<summary><strong>macOS</strong></summary>
<p></p>

If you encounter any issues, see [Troubleshooting](https://github.com/jtroo/kanata/blob/main/docs/setup-macos.md#8-troubleshooting).

### Step 1: Set up the Karabiner driver

To use Kanata, first set up the [Karabiner driver](https://github.com/pqrs-org/Karabiner-DriverKit-VirtualHIDDevice):

1.  If [Karabiner Elements](https://karabiner-elements.pqrs.org/) is installed, disable its background processes: Open **System Settings → General → Login Items & Extensions**. In the **App Background Activity** section, disable the following if you see them:

    -   **Karabiner-Elements Privileged Daemons**
    -   **Karabiner-Elements Privileged Daemons v2**

1.  [Download Karabiner driver v6.2.0](https://github.com/pqrs-org/Karabiner-DriverKit-VirtualHIDDevice/releases/download/v6.2.0/Karabiner-DriverKit-VirtualHIDDevice-6.2.0.pkg). You must download v6.2.0 because that is the version supported by Kanata.

1.  Run the Karabiner driver installer.

1.  Open a terminal.

    If you’re not sure how, follow these steps:

    1.  Press `Command + Space`.

    1.  In the **Spotlight Search** box that appears, enter `terminal`.

    1.  Double-click **Terminal**. The Terminal app opens.

1.  In the terminal, activate the driver.

    > If you’re not sure how to run a command from this guide, see [Run a command from this guide](#run-a-command-from-this-guide).

    ```shell
    sudo /Applications/.Karabiner-VirtualHIDDevice-Manager.app/Contents/MacOS/Karabiner-VirtualHIDDevice-Manager forceActivate
    ```

    If you previously ran the `deactivate` command, restart your computer.

1.  Enable the Karabiner system extension: Open **System Settings → General → Login Items & Extensions**. In the **Extensions** section, enable `org.pqrs.Karabiner-DriverKit-VirtualHIDDevice`.

1.  [Download the Karabiner plist file](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/org.pqrs.Karabiner-VirtualHIDDevice-Daemon.plist) and save it in the `/Library/LaunchDaemons` folder.

1.  In the terminal, register the Karabiner daemon:

    ```shell
    sudo chown root:wheel /Library/LaunchDaemons/org.pqrs.Karabiner-VirtualHIDDevice-Daemon.plist
    sudo launchctl bootstrap system /Library/LaunchDaemons/org.pqrs.Karabiner-VirtualHIDDevice-Daemon.plist
    sudo launchctl list | grep org.pqrs
    ```

    The output lists the Karabiner daemon `org.pqrs.service.daemon.Karabiner-VirtualHIDDevice-Daemon`.

### Step 2: Set up the Kanata executable file

1.  Download Kanata.

    Kanata has two versions, one for arm64 processors and one for x64 processors. To check what processor your computer uses, see this guide’s [Check what processor your computer uses](#check-what-processor-your-computer-uses).

    -   If your computer uses an **arm64** processor, [download the arm64 version of Kanata](https://github.com/jtroo/kanata/releases/latest/download/macos-binaries-arm64.zip).
    -   If your computer uses an **x64** processor, [download the x64 version of Kanata](https://github.com/jtroo/kanata/releases/latest/download/macos-binaries-x64.zip).

1.  Extract the downloaded zip file. The filenames of the Kanata executable files start with `kanata_macos_`.

1.  Enable Accessibility: open **System Settings → Privacy & Security → Accessibility** and add the Kanata executable file whose filename starts with `kanata_macos_cmd_allowed_`.

1.  Enable Input Monitoring: open **System Settings → Privacy & Security → Input Monitoring** and add the Kanata executable file whose filename starts with `kanata_macos_cmd_allowed_`.

</details>

## Step 2: Run an alt layout

Expand the section for your operating system.

<!----------------------------------------------------------------------------->
<!-- Windows -->

<details>
<summary><strong>Windows</strong></summary>
<p></p>

1.  [Download the example config](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/example-config.kbd).

1.  Move the example config to the same folder as the Kanata executable files.

1.  Open a terminal in the folder containing the Kanata executable files.

    If you’re not sure how, right-click an empty space inside the folder and select **Open in Terminal**.

1.  In the terminal, run the example config using Kanata:

    -   If your computer uses an **x64** processor, run the following command.

        >   If you’re not sure how to run a command from this guide, see [Run a command from this guide](#run-a-command-from-this-guide).

        ```cmd
        .\kanata_windows_gui_winIOv2_cmd_allowed_x64.exe --cfg example-config.kbd --nodelay
        ```

    -   If your computer uses an **arm64** processor, run the following command.

        >   If you’re not sure how to run a command from this guide, see [Run a command from this guide](#run-a-command-from-this-guide).

        ```cmd
        .\kanata_windows_gui_winIOv2_cmd_allowed_arm64.exe --cfg example-config.kbd --nodelay
        ```

Kanata is running the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite). Press your `q` key&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;it outputs `b`.

**To stop running the example config or any Kanata config**, press the key combination `Left Control + Space + Escape`. Use the physical keys in those positions&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;it doesn’t matter what you configured those keys to do.

</details>

<!----------------------------------------------------------------------------->
<!-- Linux -->

<details>
<summary><strong>Linux</strong></summary>
<p></p>

1.  [Download the example config](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/example-config.kbd).

1.  Move the example config to the same folder as the Kanata executable files.

1.  Open a terminal in the folder containing the Kanata executable files.

    If you’re not sure how, right-click an empty space inside the folder and select **Open in Terminal**.

1.  In the terminal, run the example config using Kanata. You only need to run the `chmod` command the first time you run Kanata.

    > If you’re not sure how to run a command from this guide, see [Run a command from this guide](#run-a-command-from-this-guide).

    ```shell
    chmod +x kanata_linux_cmd_allowed_x64
    sudo ./kanata_linux_cmd_allowed_x64 --cfg example-config.kbd --nodelay
    ```

Kanata is running the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite). Press your `q` key&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;it outputs `b`.

**To stop running the example config or any Kanata config**, press the key combination `Left Control + Space + Escape`. Use the physical keys in those positions&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;it doesn’t matter what you configured those keys to do.

</details>

<!----------------------------------------------------------------------------->
<!-- macOS -->

<details>
<summary><strong>macOS</strong></summary>
<p></p>

If you encounter any issues, see [Troubleshooting](https://github.com/jtroo/kanata/blob/main/docs/setup-macos.md#8-troubleshooting).

1.  [Download the example config](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/example-config.kbd).

1.  Move the example config to the same folder as the Kanata executable files.

1.  Open a terminal in the folder containing the Kanata executable files.

    If you’re not sure how, right-click an empty space inside the folder and select **Services → New Terminal at Folder**.
    -   If **New Terminal at Folder** doesn’t appear, click **Finder → Services → Services Settings → Files and Folders** and enable **New Terminal at Folder**.

1.  In the terminal, run the example config using Kanata:

    -   If your computer uses an **arm64** processor, run the following command. You only need to run the `chmod` command the first time you run Kanata.

        ```shell
        chmod +x kanata_macos_cmd_allowed_arm64
        sudo ./kanata_macos_cmd_allowed_arm64 --cfg example-config.kbd --nodelay
        ```

    -   If your computer uses an **x64** processor, run the following command. You only need to run the `chmod` command the first time you run Kanata.

        ```shell
        chmod +x kanata_macos_cmd_allowed_x64
        sudo ./kanata_macos_cmd_allowed_x64 --cfg example-config.kbd --nodelay
        ```

Kanata is running the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite). Press your `q` key&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;it outputs `b`.

**To stop running the example config or any Kanata config**, press the key combination `Left Control + Space + Escape`. Use the physical keys in those positions&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;it doesn’t matter what you configured those keys to do.

</details>

## Step 3: Change your layout

For pre-made Kanata configs of a few layouts&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;such as the [Graphite config](configs/graphite.kbd)&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;see this guide’s [Layouts](#layouts).

This section shows you how to change the layout of the [example config](configs/example-config.kbd).

### Step 1: Learn how the example config works

The example config is a text file with the following contents:

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

**How Kanata remaps your keyboard**: Kanata remaps each physical key in the `defsrc` entry to a key in the same position in the `gallium` layer. For example, Kanata remaps `q` in the `defsrc` entry to `b` in the `gallium` layer.

### Step 2: Edit the example config

1.  Open the example config with a plain text editor.

    If you’re not sure how, see this guide’s [Open a file with a plain text editor](#open-a-file-with-a-plain-text-editor).

1.  To remap keys that aren’t in the `defsrc` entry, add those keys to the `defsrc` entry. For valid key names, see this guide’s [Key names for the `defsrc` and `deflayer` entries](#key-names-for-the-defsrc-and-deflayer-entries).

1.  In the `deflayer` entry, rename the `gallium` layer to the name of your layout.

1.  In the `deflayer` entry, edit the keys to match your layout&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;to avoid manually changing most keys, see this guide’s [Copy your layout into a `deflayer` entry](#copy-your-layout-into-a-deflayer-entry).

1.  To match the number of keys in the `deflayer` entry to the number of keys in the `defsrc` entry, add or remove keys as needed.

1.  Optional: To align the keys in the `deflayer` entry to the keys in the `defsrc` entry, add or remove space characters.

1.  Save the file.

### Step 3: Run your layout

The following steps are based on this guide’s [Run an alt layout](#step-2-run-an-alt-layout):

1.  Open a terminal in the folder containing the Kanata executable files.

1.  In the terminal, run the example config using Kanata. For example, on Linux, run the following command:

```shell
sudo ./kanata_linux_cmd_allowed_x64 --cfg example-config.kbd --nodelay
```

## Run your layout automatically when you log in

Expand the section for your operating system.

<!----------------------------------------------------------------------------->
<!-- Windows -->

<details>
<summary><strong>Windows</strong></summary>
<p></p>

1.  Open the startup folder.

    If you’re not sure how, follow these steps:

    1.  Press `Windows + R`. The **Run** dialog appears.

    1.  In the **Open** box, enter the following path:

        ```
        %AppData%\Microsoft\Windows\Start Menu\Programs\Startup
        ```

    1.  Click **OK**. The startup folder opens.

1.  Create a shortcut of the Kanata executable file you ran in the last step of this guide’s [Run an alt layout](#step-2-run-an-alt-layout).

    If you’re not sure how: in the folder of the Kanata executable file, hold the `Alt` key and drag the file anywhere inside the folder.

1.  Move the shortcut of the Kanata executable to the startup folder.

1.  Right-click the shortcut and select **Properties**.

1.  In the **Properties** dialog that appears, add the following arguments to the end of the **Target** field:

    ```
     --cfg "KANATA_CONFIG_PATH" --nodelay
    ```

    Replace `KANATA_CONFIG_PATH` with the path to your Kanata config file&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example, `C:\Users\username\Documents\Kanata\example-config.kbd`.

    The full target is similar to the following:

    <pre>
    "KANATA_EXECUTABLE_PATH" --cfg "KANATA_CONFIG_PATH" --nodelay
    </pre>

    `KANATA_EXECUTABLE_PATH` is the path to the Kanata executable file&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example, `C:\Program Files\Kanata\kanata_windows_gui_winIOv2_cmd_allowed_x64.exe`.

1. In the **Properties** dialog, click **OK**.

1. To verify the shortcut runs properly, double-click the shortcut and test a remapped key.

Kanata will run your config in the background when you log in to your computer.

</details>

<!----------------------------------------------------------------------------->
<!-- Linux -->

<details>
<summary><strong>Linux</strong></summary>
<p></p>

1.  [Download the Kanata service file](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/kanata.service) and save it in the `/etc/systemd/system/` folder.

1.  Open the Kanata service file with a plain text editor.

1.  Edit the following line:

    <pre>
    ExecStart=KANATA_EXECUTABLE_PATH --cfg KANATA_CONFIG_PATH --nodelay
    </pre>

    Replace the following:

    -   `KANATA_EXECUTABLE_PATH`: the path to the Kanata executable file&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example, `/usr/local/bin/kanata_linux_cmd_allowed_x64`
    -   `KANATA_CONFIG_PATH`: the path to the Kanata config file&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example, `/home/username/Documents/Kanata/example-config.kbd`

1. Save the file.

1.  Open a terminal and enable the service:

    ```shell
    sudo systemctl enable kanata.service
    ```

Kanata will run your config in the background when you log in to your computer.

</details>

<!----------------------------------------------------------------------------->
<!-- macOS -->

<details>
<summary><strong>macOS</strong></summary>
<p></p>

1.  [Download the Kanata plist file](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/dev.kanata.kanata.plist) and save it in the `/Library/LaunchDaemons` folder. Don’t change the filename.

1.  Open the Kanata plist file with a plain text editor.

1.  Edit the `ProgramArguments` key:

    <pre>
        &lt;key&gt;ProgramArguments&lt;/key&gt;
        &lt;array&gt;
            &lt;string&gt;KANATA_EXECUTABLE_PATH&lt;/string&gt;
            &lt;string&gt;--cfg&lt;/string&gt;
            &lt;string&gt;KANATA_CONFIG_PATH&lt;/string&gt;
            &lt;string&gt;--nodelay&lt;/string&gt;
        &lt;/array&gt;
    </pre>

    Replace the following:

    -   `KANATA_EXECUTABLE_PATH`: the path to the Kanata executable file&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example, `/usr/local/bin/kanata_macos_cmd_allowed_arm64`
    -   `KANATA_CONFIG_PATH`: the path to the Kanata config file&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example, `/Users/username/Documents/Kanata/example-config.kbd`

1. Save the file.

1.  Open a terminal and register the Kanata daemon:

    ```shell
    sudo chown root:wheel /Library/LaunchDaemons/dev.kanata.kanata.plist
    sudo launchctl bootstrap system /Library/LaunchDaemons/dev.kanata.kanata.plist
    launchctl list | grep dev.kanata
    ```

    The output lists the Kanata daemon `dev.kanata.kanata`.

Kanata will run your config in the background when you log in to your computer.

</details>

## Example configs

To run one of the example configs, see this guide’s [Run one of the example configs](#run-one-of-the-example-configs).

To learn about any Kanata feature used in a config, see this guide’s [Basics of a Kanata config](#basics-of-a-kanata-config) and the [Kanata Configuration Guide](https://jtroo.github.io/config.html).

### General configs

-   [`hold-backtick-to-switch-layouts.kbd`](configs/hold-backtick-to-switch-layouts.kbd)
    -   Toggles between your alt layout and QWERTY when you hold the backtick `` ` `` key
-   [`gallium-with-qwerty-shortcuts.kbd`](configs/gallium-with-qwerty-shortcuts.kbd)
    -   Uses QWERTY shortcuts when you hold any modifier key, such as `Control`
-   [`gallium-with-home-row-mods.kbd`](configs/gallium-with-home-row-mods.kbd)
    -   Layout with [home row mods](https://getreuer.info/posts/keyboards/tour/index.html#home-row-mods)
-   [`gallium-with-qwerty-home-row-mods.kbd`](configs/gallium-with-qwerty-home-row-mods.kbd)
    -   Layout with home row mods that use QWERTY
-   [`gallium-with-symbol-layer.kbd`](configs/gallium-with-symbol-layer.kbd)
    -   Layout with a 2nd layer for symbol keys
-   [`gallium-with-navigation-layer.kbd`](configs/gallium-with-navigation-layer.kbd)
    -   Layout with a 2nd layer for navigation keys

### Layouts

-   [`graphite.kbd`](configs/graphite.kbd)
    -   Layout with custom shift pairs
-   [`night.kbd`](configs/night.kbd)
    -   Layout with a [thumb alpha key](https://layouts.wiki/guides/start/recommendations/#thumb-alpha)
-   [`gallium-angle.kbd`](configs/gallium-angle.kbd)
    -   Layout with [angle mod](https://colemakmods.github.io/ergonomic-mods/angle.html)
-   [`night-wide.kbd`](configs/night-wide.kbd)
    -   Layout with [wide mod](https://colemakmods.github.io/ergonomic-mods/wide.html)
-   [`night-double-wide.kbd`](configs/night-double-wide.kbd)
    -   Layout with wide mod applied twice
-   [`nokwts.kbd`](configs/nokwts.kbd)
    -   Layout with the [Nokwts fingermap](https://discord.com/channels/807843650717483049/1063291226243207268/1339406872666439752)

### Advanced layouts

-   [`lucens.kbd`](configs/lucens.kbd)
    -   Layout with a 2nd layer for German letters
-   [`gallium-with-compose.kbd`](configs/gallium-with-compose.kbd)
    -   Layout with a [compose key](https://en.wikipedia.org/wiki/Compose_key)
-   [`gallium-with-combos.kbd`](configs/gallium-with-combos.kbd)
    -   Layout with combos
-   [`2-row-gallium.kbd`](configs/2-row-gallium.kbd)
    -   Layout with only 2 rows
-   [`taipo.kbd`](configs/taipo.kbd)
    -   Layout that can be used with 1 hand
-   [`crescent.kbd`](configs/crescent.kbd)
    -   Layout with only 10 keys, one for each finger
-   [`nastic.kbd`](configs/nastic.kbd)
    -   Layout with duplicate keys
-   [`whirl.kbd`](configs/whirl.kbd)
    -   Layout with a [magic key](https://layouts.wiki/reference/terminology/magic/)
-   [`afterburner.kbd`](configs/afterburner.kbd)
    -   Layout with a skip magic key
-   [`nordrassil.kbd`](configs/nordrassil.kbd)
    -   Layout with [chiral magic keys](https://github.com/zachpoblete/alt-layout-glossary#chiral-magic-keys)
-   [`d5.kbd`](configs/d5.kbd)
    -   Layout with chiral skip magic keys
-   [`adaptive-sturdy.kbd`](configs/adaptive-sturdy.kbd)
    -   Layout with [adaptive swaps](https://dario.ca/posts/2026-05-18-keyboard-layout-adaptive-swaps/)
-   [`buggy.kbd`](configs/buggy.kbd)
    -   Layout with 2 alpha layers
-   [`power.kbd`](configs/power.kbd)
    -   Layout with 162 layers

## Basics of a Kanata config

To learn about the two required entries of a Kanata config&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;`defsrc` and `deflayer`&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;see this guide’s [Learn how the example config works](#step-1-learn-how-the-example-config-works).

The following concepts help you read and edit the configs in this guide’s [Example configs](#example-configs).

### Comments

Kanata ignores comments.

Comments are prefixed with two semicolons `;;`&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example:

```
;; This is a comment.

(defsrc
  caps a s d f  ;; Comments can be added to the end of a line.
)
```

### Lists

Configs are made of lists.

Lists have the form `(item1 item2 item3 ...)`. The parentheses `()` group related items together. Items are separated by whitespace.

Usually, the first item is a command and the rest are arguments, such as in the `defsrc` and `deflayer` entries.

### Actions

Actions let you go beyond remapping a key to a different key.

The following example maps `Caps Lock` to the [`tap-hold` action](https://jtroo.github.io/config.html#tap-hold), letting you activate `Left Control` by holding `Caps Lock`:

```
(defsrc
  caps a s d f
)

(deflayer example
  (tap-hold 200 200 caps lctl) a s d f
)
```

### Aliases

Aliases are named shortcuts for actions.

Aliases are defined in a `defalias` entry:

```
(defalias
  alias1-name alias1-action
  alias2-name alias2-action
  ...
)
```

Each line is a pair&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;an alias name followed by an action the alias maps to. An alias is used by prefixing the alias name with `@`.

The following example uses an alias for the `tap-hold` action:

```
(defalias
  caps (tap-hold 200 200 caps lctl)
)

(deflayer example
  @caps a s d f
)
```

### Variables

Variables are named shortcuts for strings or lists.

Variables are defined in a `defvar` entry:

```
(defvar
  variable1-name variable1-value
  variable2-name variable2-value
  ...
)
```

Each line is a pair&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;a variable name followed by the value the variable maps to. A variable is used by prefixing the variable name with `$`.

The following example uses variables for the numbers in the `tap-hold` action:

```
(defvar
  tap-time  200
  hold-time 200
)

(defalias
  caps (tap-hold $tap-time $hold-time caps lctl)
)
```

## Key names for the `defsrc` and `deflayer` entries

To find valid key names for the `defsrc` and `deflayer` entries, see the following references:

-   For common keys, see the [60% US keyboard config](configs/us-keyboard.kbd).
-   For other keys, see [Key names](https://jtroo.github.io/config.html#key-names).
-   For keys not found on the US keyboard, see [Non-US keyboards](https://jtroo.github.io/config.html#non-us-keyboards) and [Keyboard locales](https://github.com/jtroo/kanata/blob/main/docs/locales.adoc).

## Mini guides

### Check what processor your computer uses

Expand the section for your operating system.

<details>
<summary><strong>Windows</strong></summary>
<p></p>

1.  Open the **Settings** app.

    If you’re not sure how, right-click the **Start** menu and select **Settings**.

1.  In the navigation panel, click **System**.

1.  Scroll to the end of the page and click **About**.

1.  In the **Device info** section, look for the **System type** item:

    -   If it says **64-bit operating system, _x64_-based processor**, your computer uses an **x64** processor.
    -   If it says **64-bit operating system, _ARM_-based processor**, your computer uses an **arm64** processor.

</details>

<details>
<summary><strong>macOS</strong></summary>
<p></p>

1.  Click the **Apple icon** menu and select **About This Mac**.

1.  In the window that appears, look for either a **Chip** or **Processor** item:

    -   **Chip** means your computer uses an **arm64** processor.
    -   **Processor** means your computer uses an **x64** processor.

</details>

### Run a command from this guide

1.  To copy the command, click **Copy code to clipboard**.

1.  Click in the terminal window.

1.  Paste the command:

    -   Windows: Press `Control + V`&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;if that doesn’t work, right-click.
    -   Linux: Press `Control + Shift + V`&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;if that doesn’t work, right-click.
    -   macOS: Press `Command + V`.

1.  To run the command, press `Enter`.

### Open a file with a plain text editor

1.  Right-click the file and select **Open with**.

1.  Select your default text editor:

    -   Windows: **Notepad**
    -   Linux: **gedit**, or whichever text editor came preinstalled
    -   macOS: **TextEdit**

### Copy your layout into a `deflayer` entry

1.  Open the [cmini browser](https://cminibrowser.com/) website.

1.  In the **Search** box, enter the name of your layout.

1.  Click the row of your layout.

1.  To copy your layout, click the graphic of your layout that appears.

    ![](images/cmini-browser-copy-layout-as-text-screenshot.png)

1.  Open your config with a plain text editor.

1.  Paste the layout into a `deflayer` entry.

### Run one of the example configs

The following steps are based on this guide’s [Run an alt layout](#step-2-run-an-alt-layout).

1.  Download one of the configs from this guide’s [Example configs](#example-configs).

    If you’re not sure how, follow these steps:

    1.  Open the link of the config you want to download&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example, [`hold-backtick-to-switch-layouts.kbd`](configs/hold-backtick-to-switch-layouts.kbd).

    1.  To download the config, click <picture><source media="(prefers-color-scheme: dark)" srcset="images\github-download-raw-file-icon-light.svg"><img alt="Download raw file" src="images\github-download-raw-file-icon-dark.svg"></picture>.

        <picture>
            <source media="(prefers-color-scheme: dark)" srcset="images\github-download-raw-file-screenshot.png">
            <img alt="" src="images\github-download-raw-file-screenshot-with-drop-shadow.png">
        </picture>

1.  Move the config to the same folder as the Kanata executable files.

1.  Open a terminal in the folder containing the Kanata executable files.

1.  Copy the command from the last step of [Run an alt layout](#step-2-run-an-alt-layout) into the terminal.

1.  In the command, replace `example-config.kbd` with the filename of the config you downloaded. For example, to run the [`hold-backtick-to-switch-layouts.kbd`](configs/hold-backtick-to-switch-layouts.kbd) config on Linux, run the following command:

    ```shell
    sudo ./kanata_linux_cmd_allowed_x64 --cfg hold-backtick-to-switch-layouts.kbd --nodelay
    ```

## Feedback

Found an issue or have a question? [Open an issue](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/issues) or reach out on the [Alt Keyboard Layouts Discord](https://discord.gg/4kVZu7uWdy)&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;feel free to mention @novachromatic, the owner of this guide.
