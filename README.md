# Kanata Guide for Keyboard Layouts

[Kanata](https://github.com/jtroo/kanata) is software for remapping any keyboard on Windows, Linux, and macOS. This guide shows you how to use Kanata to set up a [keyboard layout](https://layouts.wiki/guides/start/intro/) and add features to it.

Kanata remaps your keyboard using a file called a _config_. This guide contains pre-made configs that add features to a layout. These features include the following:

-   Toggling to QWERTY
-   QWERTY shortcuts
-   Symbol and navigation layers
-   Magic keys and adaptive swaps

You can use this guide even if you don’t have any programming experience.

### In this guide

-   [Why use Kanata for keyboard layouts?](#why-use-kanata-for-keyboard-layouts)
-   [Supported platforms](#supported-platforms)
-   [Step 1: Set up Kanata](#step-1-set-up-kanata)
-   [Step 2: Run Kanata](#step-2-run-kanata)
-   [Change your layout](#change-your-layout)
-   [Automatically start Kanata](#automatically-start-kanata)
-   [Pre-made configs](#pre-made-configs)
-   [Get help](#Get-help)

## Why use Kanata for keyboard layouts?

-   Kanata and all its features are completely free to use.
-   Kanata is open source&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;anyone can view exactly how it works.
-   Kanata works on any keyboard, including laptop keyboards and non-US keyboards.
-   Kanata lets you add features to a layout. See this guide’s [Pre-made configs](#pre-made-configs).
-   Kanata lets you use the same config on Windows, Linux, and macOS.
-   Kanata has an active community on the [Alt Keyboard Layouts Discord](https://discord.gg/4kVZu7uWdy) that can answer any question you have.

## Supported platforms

-   Windows 10 or newer
-   Linux
-   macOS 13 or newer

## Step 1: Set up Kanata

Expand the section for your platform.

<details>
<summary><strong>Windows</strong></summary>
<p></p>

1.  Download Kanata:

    -   [x64 download](https://github.com/jtroo/kanata/releases/latest/download/windows-binaries-x64.zip)
    -   [arm64 download](https://github.com/jtroo/kanata/releases/latest/download/windows-binaries-arm64.zip)

    <blockquote>
    <p>

    If you’re not sure which to download, see [Windows: Check if your computer is x64 or arm64](docs/reference-guides.md#windows-check-if-your-computer-is-x64-or-arm64).

    </p>
    </blockquote>

1.  Extract the downloaded zip file.

    The folder you extracted the zip file to contains multiple Kanata executable files. The filenames of the executable files start with `kanata_windows_`. This guide will show you the executable file you need to use.

1.  [Download the example config](https://github.com/zachpoblete/kanata-guide-for-keyboard-layouts/releases/download/download/example-config.kbd). It will remap your keyboard to the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite).

1.  Save the example config to the folder containing the Kanata executable files.

</details>

<details>
<summary><strong>Linux</strong></summary>
<p></p>

1.  [Download Kanata](https://github.com/jtroo/kanata/releases/latest/download/linux-binaries-x64.zip).

1.  Extract the downloaded zip file.

    The folder you extracted the zip file to contains multiple Kanata executable files. The filenames of the executable files start with `kanata_linux_`. This guide will show you the executable file you need to use.

1.  [Download the example config](https://github.com/zachpoblete/kanata-guide-for-keyboard-layouts/releases/download/download/example-config.kbd). It will remap your keyboard to the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite).

1.  Save the example config to the folder containing the Kanata executable files.

</details>

<details>
<summary><strong>macOS</strong></summary>
<p></p>

### Step 1.1: Set up the Karabiner driver

To use Kanata, first set up the [Karabiner driver](https://github.com/pqrs-org/Karabiner-DriverKit-VirtualHIDDevice):

1.  If you have [Karabiner Elements](https://karabiner-elements.pqrs.org/) installed, see [macOS: Disable Karabiner Elements Privileged Daemons](docs/reference-guides.md#macos-disable-karabiner-elements-privileged-daemons).

    **Note:** It isn’t possible to run both Kanata and Karabiner Elements at the same time.

1.  [Download Karabiner driver v6.2.0](https://github.com/pqrs-org/Karabiner-DriverKit-VirtualHIDDevice/releases/download/v6.2.0/Karabiner-DriverKit-VirtualHIDDevice-6.2.0.pkg). You must download v6.2.0 because that is the version supported by Kanata.

1.  Run the Karabiner driver installer.

1.  Open a terminal.

    >   If you’re not sure how, see [macOS: Open a terminal](docs/reference-guides.md#macos-open-a-terminal).

1.  In the terminal, activate the Karabiner driver:

    ```shell
    sudo /Applications/.Karabiner-VirtualHIDDevice-Manager.app/Contents/MacOS/Karabiner-VirtualHIDDevice-Manager forceActivate
    ```

    >   If you’re not sure how to run a terminal command, see [Run a command from this guide](docs/reference-guides.md#run-a-command-from-this-guide).

1.  If you have Karabiner Elements installed, restart your computer to use the new Karabiner driver.

### Step 1.2: Enable the Karabiner system extension

1.  Open the **System Settings** app.

1.  Click **General > Login Items & Extensions**.

1.  In **Extensions**, enable **.Karabiner-VirtualHIDDevice-Manager**.

### Step 1.3: Set up the Karabiner daemon

1.  [Download the Karabiner plist file](https://github.com/zachpoblete/kanata-guide-for-keyboard-layouts/releases/download/download/org.pqrs.Karabiner-VirtualHIDDevice-Daemon.plist).

1.  Save the Karabiner plist file to the `/Library/LaunchDaemons` folder.

1.  In the terminal, register the Karabiner daemon:

    ```shell
    sudo chown root:wheel /Library/LaunchDaemons/org.pqrs.Karabiner-VirtualHIDDevice-Daemon.plist
    sudo launchctl bootstrap system /Library/LaunchDaemons/org.pqrs.Karabiner-VirtualHIDDevice-Daemon.plist
    sudo launchctl list | grep org.pqrs
    ```

    The output lists the Karabiner daemon `org.pqrs.service.daemon.Karabiner-VirtualHIDDevice-Daemon`.

### Step 1.4: Set up the Kanata executable file

1.  Download Kanata:

    -   [arm64 download](https://github.com/jtroo/kanata/releases/latest/download/macos-binaries-arm64.zip)
    -   [x64 download](https://github.com/jtroo/kanata/releases/latest/download/macos-binaries-x64.zip)

    <blockquote>
    <p>

    If you’re not sure which to download, see [macOS: Check if your computer is arm64 or x64](docs/reference-guides.md#macos-check-if-your-computer-is-arm64-or-x64).

    </p>
    </blockquote>

1.  Extract the downloaded zip file.

    The folder you extracted the zip file to contains multiple Kanata executable files. The filenames of the executable files start with `kanata_macos_`. This guide will show you the executable file you need to use.

### Step 1.5: Enable Accessibility

1.  Open the **System Settings** app.

1.  Click **Privacy & Security > Accessibility**.

<ol start="3">
<li><a name="step-15-add-kanata"></a>Add Kanata:

1.  Click **+**.

1.  Search for the folder containing the Kanata executable files.

1.  Select the executable file whose filename starts with `kanata_macos_cmd_allowed_`.

1.  Click **Open**.

</li>
</ol>

<ol start="4">
<li><a name="step-15-add-your-terminal"></a>If you use the native <strong>Terminal</strong> and it isn’t in the list of apps, or you use a third-party terminal and it isn’t in the list of apps, follow these steps:

1.  Click **+**.

1.  Search for your terminal.

1.  Select your terminal.

1.  Click **Open**.

</li>
</ol>

### Step 1.6: Enable Input Monitoring

1.  In the **System Settings** app, click **Privacy & Security > Input Monitoring**.

1.  [Add Kanata as you did in the Enable Accessibility step](#step-15-add-kanata).

1.  If your terminal isn’t in the list of apps, [add your terminal as you did in the Enable Accessibility step](#step-15-add-your-terminal).

### Step 1.7: Set up the example config

1.  [Download the example config](https://github.com/zachpoblete/kanata-guide-for-keyboard-layouts/releases/download/download/example-config.kbd). It will remap your keyboard to the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite).

1.  Save the example config to the folder containing the Kanata executable files.

</details>

## Step 2: Run Kanata

Kanata runs from the terminal. To automatically start Kanata in the background, see this guide’s [Automatically start Kanata](#automatically-start-kanata).

Expand the section for your platform.

<details>
<summary><strong>Windows</strong></summary>
<p></p>

1.  Open a terminal in the folder containing the Kanata executable files.

    >   If you’re not sure how, right-click an empty space inside the folder and select **Open in Terminal**.

1.  In the terminal, run the example config:

    ```cmd
    .\kanata_windows_gui_winIOv2_cmd_allowed_x64 --cfg example-config.kbd --nodelay
    ```

    If your computer is arm64, replace `x64` with `arm64`.

    <blockquote>
    <p>

    If you’re not sure how to run a terminal command, see [Run a command from this guide](docs/reference-guides.md#run-a-command-from-this-guide).

    </p>
    </blockquote>

Kanata is running the Gallium layout. Press your `q` key&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;it outputs `b`.

**To stop running Kanata**, press the key combination `Left Control + Space + Escape`. Even if you remap those keys, press the original keys for `Left Control`, `Space`, and `Escape`.

</details>

<details>
<summary><strong>Linux</strong></summary>
<p></p>

1.  Open a terminal in the folder containing the Kanata executable files.

    >   If you’re not sure how, right-click an empty space inside the folder and select **Open in Terminal**.

1.  In the terminal, run the example config. You only need to run the `chmod` command the first time you run Kanata.

    ```shell
    chmod +x kanata_linux_cmd_allowed_x64
    sudo ./kanata_linux_cmd_allowed_x64 --cfg example-config.kbd --nodelay
    ```

    >   If you’re not sure how to run a terminal command, see [Run a command from this guide](docs/reference-guides.md#run-a-command-from-this-guide).

Kanata is running the Gallium layout. Press your `q` key&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;it outputs `b`.

**To stop running Kanata**, press the key combination `Left Control + Space + Escape`. Even if you remap those keys, press the original keys for `Left Control`, `Space`, and `Escape`.

</details>

<details>
<summary><strong>macOS</strong></summary>
<p></p>

If you encounter any issues, see [Troubleshooting](https://github.com/jtroo/kanata/blob/main/docs/setup-macos.md#8-troubleshooting).

1.  Open a terminal in the folder containing the Kanata executable files.

    >   If you’re not sure how, see [macOS: Open a folder in a terminal](docs/reference-guides.md#macos-open-a-folder-in-a-terminal).

1.  In the terminal, run the example config. You only need to run the `chmod` command the first time you run Kanata.

    ```shell
    chmod +x kanata_macos_cmd_allowed_arm64
    sudo ./kanata_macos_cmd_allowed_arm64 --cfg example-config.kbd --nodelay
    ```

    If your computer is x64, replace `arm64` with `x64`.

Kanata is running the Gallium layout. Press your `q` key&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;it outputs `b`.

**To stop running Kanata**, press the key combination `Left Control + Space + Escape`. Even if you remap those keys, press the original keys for `Left Control`, `Space`, and `Escape`.

</details>

## Change your layout

In this section, you will change the layout of the example config.

### Step 1: Learn how the example config works

-   To learn how the example config works, see [The `defsrc` and `deflayer` entries](docs/config-basics.md#the-defsrc-and-deflayer-entries).

### Step 2: Edit the example config

For key names you can use, see [Key Names for the `defsrc` and `deflayer` Entries](docs/key-names.md).

1.  Open the example config with a plain text editor.

    >   If you’re not sure how, see [Open a file with a plain text editor](docs/reference-guides.md#open-a-file-with-a-plain-text-editor).

1.  To remap keys that aren’t in the `defsrc` entry, add those keys to the `defsrc` entry.

1.  In the `deflayer` entry, rename the `gallium` layer to the name of your layout.

1.  In the `deflayer` entry, edit the keys to match your layout:

    1.  If your layout already exists, see [Copy an existing layout into a `deflayer` entry](docs/reference-guides.md#copy-an-existing-layout-into-a-deflayer-entry).

    1.  If you layout has characters that aren’t on your keyboard, see [Remap a key to a Unicode character](docs/reference-guides.md#remap-a-key-to-a-unicode-character).

1.  If the number of keys of the `defsrc` and `deflayer` entries don’t match, add or remove keys as needed.

1.  Optional: To align the keys in the `deflayer` entry to the keys in the `defsrc` entry, add or remove space characters.

1.  Save the file.

### Step 3: Run the example config

1.  [Run the example config as you did in the Run Kanata step](#step-2-run-kanata).

1.  If Kanata isn’t remapping a key, the name of the key might be incorrect. See [How to get the name of a key](docs/key-names.md#how-to-get-the-name-of-a-key).

Kanata is running your layout.

## Automatically start Kanata

Expand the section for your platform.

<details>
<summary><strong>Windows</strong></summary>
<p></p>

1.  Open the startup folder.

    >   If you’re not sure how, see [Windows: Open the startup folder](docs/reference-guides.md#windows-open-the-startup-folder).

1.  Create a shortcut of a Kanata executable file.

    >   If you’re not sure how: in the folder containing the Kanata executable file, hold the `Alt` key and drag the file anywhere inside the folder.

1.  Move the shortcut of the Kanata executable file to the startup folder.

1.  Right-click the shortcut and select **Properties**.

1.  In **Target**, add the following arguments:

    ```
     --cfg "KANATA_CONFIG_PATH" --nodelay
    ```

    Replace `KANATA_CONFIG_PATH` with the path to your Kanata config file&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example, `C:\Users\username\.config\kanata\config.kbd`.

    The full **Target** is similar to the following:

    <pre>
    "KANATA_EXECUTABLE_PATH" --cfg "KANATA_CONFIG_PATH" --nodelay
    </pre>

    `KANATA_EXECUTABLE_PATH` is the path to the Kanata executable file&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example, `C:\Users\username\kanata\kanata_windows_gui_winIOv2_cmd_allowed_x64.exe`.

1.  Click **OK**.

1.  To verify the shortcut runs properly, double-click the shortcut and test a remapped key.

</details>

<details>
<summary><strong>Linux</strong></summary>
<p></p>

1.  [Download the Kanata service file](https://github.com/zachpoblete/kanata-guide-for-keyboard-layouts/releases/download/download/kanata.service).

1.  Save the Kanata service file to the `/etc/systemd/system/` folder.

1.  Open the Kanata service file with a plain text editor.

1.  Edit the following line:

    <pre>
    ExecStart=KANATA_EXECUTABLE_PATH --cfg KANATA_CONFIG_PATH --nodelay --quiet
    </pre>

    Replace the following:

    -   `KANATA_EXECUTABLE_PATH`: the path to a Kanata executable file&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example, `/usr/local/bin/kanata_linux_cmd_allowed_x64`
    -   `KANATA_CONFIG_PATH`: the path to your Kanata config file&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example, `/home/username/.config/kanata/config.kbd`

1.  Save the file.

1.  Open a terminal.

    >   If you’re not sure how, press `Control + Alt + T`.

1.  In the terminal, enable the Kanata service:

    ```shell
    sudo systemctl enable kanata.service
    ```

</details>

<details>
<summary><strong>macOS</strong></summary>
<p></p>

1.  [Download the Kanata plist file](https://github.com/zachpoblete/kanata-guide-for-keyboard-layouts/releases/download/download/dev.kanata.kanata.plist).

1.  Save the Kanata plist file to the `/Library/LaunchDaemons` folder.

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

    -   `KANATA_EXECUTABLE_PATH`: the path to a Kanata executable file&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example, `/usr/local/bin/kanata_macos_cmd_allowed_arm64`
    -   `KANATA_CONFIG_PATH`: the path to your Kanata config file&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;for example, `/Users/username/.config/kanata/config.kbd`

1.  Save the file.

1.  Open a terminal.

1.  In the terminal, register the Kanata daemon:

    ```shell
    sudo chown root:wheel /Library/LaunchDaemons/dev.kanata.kanata.plist
    sudo launchctl bootstrap system /Library/LaunchDaemons/dev.kanata.kanata.plist
    launchctl list | grep dev.kanata
    ```

    The output lists the Kanata daemon `dev.kanata.kanata`.

</details>

## Pre-made configs

The following resources help you use and customize a pre-made config:

-   To run a config, see [Run a pre-made config](docs/reference-guides.md#run-a-pre-made-config).
-   To learn how to change the layout of a config, see this guide’s [Change your layout](#change-your-layout).
-   To customize a config, see [Basics of a Kanata Config](docs/config-basics.md).
-   To learn about any Kanata feature a config uses, see the [Kanata Configuration Guide](https://jtroo.github.io/config.html).

#### In this section

-   [General features](#general-features)
-   [Home row mods](#home-row-mods)
-   [Symbol and navigation layers](#symbol-and-navigation-layers)
-   [Layouts](#layouts)
-   [Small layouts](#small-layouts)
-   [Chorded layouts](#chorded-layouts)
-   [Layouts with multiple alpha layers](#layouts-with-multiple-alpha-layers)
-   [Magic keys and adaptive swaps](#magic-keys-and-adaptive-swaps)

### General features

-   [`hold-caps-to-switch-layouts.kbd`](configs/hold-caps-to-switch-layouts.kbd)
    -   Toggles between your layout and QWERTY when you hold `Caps Lock`
-   [`gallium-with-qwerty-shortcuts.kbd`](configs/gallium-with-qwerty-shortcuts.kbd)
    -   Uses QWERTY shortcuts while you hold any modifier key, such as `Control`
-   [`qwerty-while-space-held.kbd`](configs/qwerty-while-space-held.kbd)
    -   Uses QWERTY while you hold `Space`
-   [`gallium-with-compose.kbd`](configs/gallium-with-compose.kbd)
    -   Layout with a [compose key](https://en.wikipedia.org/wiki/Compose_key)

### Home row mods

-   [`gallium-with-home-row-mods.kbd`](configs/gallium-with-home-row-mods.kbd)
    -   Layout with [home row mods](https://getreuer.info/posts/keyboards/tour/index.html#home-row-mods)
-   [`gallium-with-qwerty-home-row-mods.kbd`](configs/gallium-with-qwerty-home-row-mods.kbd)
    -   Layout with home row mods that use QWERTY

### Symbol and navigation layers

These layers often use [transparent keys](https://jtroo.github.io/config.html#transparent-key).

-   [`gallium-with-symbol-layer.kbd`](configs/gallium-with-symbol-layer.kbd)
    -   Layout with a 2nd layer for symbol keys
-   [`gallium-with-navigation-layer.kbd`](configs/gallium-with-navigation-layer.kbd)
    -   Layout with a 2nd layer for navigation keys

### Layouts

-   [`graphite.kbd`](configs/graphite.kbd)
    -   Layout with custom shift pairs
-   [`lucens-german-only.kbd`](configs/lucens-german-only.kbd)
    -   Layout that has characters that aren’t on the [US keyboard](https://commons.wikimedia.org/wiki/File:Qwerty.svg#/media/File:Qwerty.svg)
-   [`night.kbd`](configs/night.kbd)
    -   Layout with a [thumb alpha key](https://layouts.wiki/guides/start/recommendations/#thumb-alpha)
-   [`night-wide.kbd`](configs/night-wide.kbd)
    -   Layout with [wide mod](https://colemakmods.github.io/ergonomic-mods/wide.html)
-   [`night-double-wide.kbd`](configs/night-double-wide.kbd)
    -   Layout with wide mod applied twice
-   [`nastic.kbd`](configs/nastic.kbd)
    -   Layout with duplicate keys

### Small layouts

-   [`taipo.kbd`](configs/taipo.kbd)
    -   Layout that can be used with 1 hand
-   [`buggy.kbd`](configs/buggy.kbd)
    -   Layout with 2 alpha layers
-   [`2-row-gallium.kbd`](configs/2-row-gallium.kbd)
    -   Layout with only 2 rows
-   [`crescent.kbd`](configs/crescent.kbd)
    -   Layout with only 10 keys, one for each finger

### Chorded layouts

-   [`gallium-with-combos.kbd`](configs/gallium-with-combos.kbd)
    -   Layout with combos
-   [`taipo.kbd`](configs/taipo.kbd)
    -   Layout that can be used with 1 hand

### Layouts with multiple alpha layers

-   [`lucens.kbd`](configs/lucens.kbd)
    -   Layout with a 2nd layer for German letters
-   [`buggy.kbd`](configs/buggy.kbd)
    -   Layout with 2 alpha layers
-   [`power.kbd`](configs/power.kbd)
    -   Layout with 162 layers

### Magic keys and adaptive swaps

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

## Get help

Need help using Kanata? [Ask on the Alt Keyboard Layouts Discord](https://discord.gg/4kVZu7uWdy)&NoBreak;&hairsp;&NoBreak;&mdash;&hairsp;see the #help channel or the questions forum.

Prefer GitHub? [Open a Q&A discussion](https://github.com/zachpoblete/kanata-guide-for-keyboard-layouts/discussions/categories/q-a).

## Feedback

Found an issue? [Open an issue on GitHub](https://github.com/zachpoblete/kanata-guide-for-keyboard-layouts/issues) or mention @novachromatic on the [Alt Keyboard Layouts Discord](https://discord.gg/4kVZu7uWdy).

Have a suggestion? [Open an Ideas discussion on GitHub](https://github.com/zachpoblete/kanata-guide-for-keyboard-layouts/discussions/categories/ideas) or mention @novachromatic on the [Alt Keyboard Layouts Discord](https://discord.gg/4kVZu7uWdy).
