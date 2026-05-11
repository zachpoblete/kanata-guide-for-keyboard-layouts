# Kanata Guide for Alt Layouts

[Kanata](https://github.com/jtroo/kanata) is a keyboard remapper for Windows, Linux, and macOS. It lets you use [alternate layouts](https://layouts.wiki/guides/start/intro/) on any keyboard and supports advanced features like layers, tap-hold, and combos.

This guide shows you how to set up an alternate layout with Kanata, edit the layout, and run Kanata on startup.

## Set up a layout with Kanata

<!----------------------------------------------------------------------------->
<!-- Windows -->


<details>
<summary><strong>Windows</strong></summary>
<p></p>

1.  Download Kanata:

    -   Most people should download the [`x64` version](https://github.com/jtroo/kanata/releases/latest/download/windows-binaries-x64.zip).
    -   If you’re using Windows on ARM, download the [`arm64` version](https://github.com/jtroo/kanata/releases/download/v1.11.0/windows-binaries-arm64.zip).

1.  Extract the downloaded zip file.

1.  Download [`example.kbd`](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/example.kbd) and put it in the same folder as the Kanata executable (looks like `kanata_windows_gui_winIOv2_cmd_allowed_...` in the extracted zip).

1.  Open the folder in a terminal.

    -   If you don’t know how: Right-click an empty space inside the folder and select **Open in Terminal**.

1.  Run Kanata:

    **x64**

    ```cmd
    .\kanata_windows_gui_winIOv2_cmd_allowed_x64.exe --cfg example.kbd
    ```

    **arm64**

    ```cmd
    .\kanata_windows_gui_winIOv2_cmd_allowed_arm64.exe --cfg example.kbd
    ```

Your keyboard is now using the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite). Press your `q` key&thinsp;&mdash;&thinsp;its output is now `b`. Try other letters!

Stop Kanata by holding: `Left Control + Space + Escape`.

</details>

<!----------------------------------------------------------------------------->
<!-- Linux -->

<details>
<summary><strong>Linux</strong></summary>
<p></p>

1.  Download [Kanata](https://github.com/jtroo/kanata/releases/latest/download/linux-binaries-x64.zip).

1.  Extract the downloaded zip file.

1.  Download [`example.kbd`](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/example.kbd) and put it in the same folder as the Kanata executable (named `kanata_linux_cmd_allowed_x64` in the extracted zip).

1.  Open the folder in a terminal.

    -   If you don’t know how: Right-click an empty space inside the folder and select **Open in Terminal**.

1.  Run Kanata:

    ```shell
    chmod +x kanata_linux_cmd_allowed_x64  # Make Kanata runnable.
    sudo ./kanata_linux_cmd_allowed_x64 --cfg example.kbd
    ```

Your keyboard is now using the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite). Press your `q` key&thinsp;&mdash;&thinsp;its output is now `b`. Try other letters!

Stop Kanata by holding: `Left Control + Space + Escape`.

</details>

<!----------------------------------------------------------------------------->
<!-- macOS 10 and older -->

<details>
<summary><strong>macOS 10 and older</strong></summary>
<p></p>

>   **⚠️ Warning:**
>   It is unclear whether the latest version of Kanata works with macOS 10 and older. Support for macOS 10 was added to Kanata in [v1.6.0](https://github.com/jtroo/kanata/releases/tag/v1.6.0), so you may need to start there. Kanata has been reported to [work on macOS Catalina (v10.15)](https://github.com/jtroo/kanata/issues/676#issuecomment-1868389437).

If Karabiner Elements is installed: Open **System Settings → General → Login Items & Extensions** and disable **Karabiner-Elements Privileged Daemons v2**.

1.  Install the [Karabiner kernel extension](https://github.com/pqrs-org/Karabiner-VirtualHIDDevice-archived) for macOS 10. The [Kmonad instructions](https://github.com/kmonad/kmonad/blob/master/doc/installation.md#macos) for installing the kernel extension (kext) may be helpful.

1.  Download [Kanata](https://github.com/jtroo/kanata/releases/latest/download/macos-binaries-x64.zip).

    -   Note: This is the latest version.

1.  Extract the downloaded zip file.

1.  Download [`example.kbd`](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/example.kbd) and put it in the same folder as the Kanata executable (named `kanata_macos_cmd_allowed_x64` in the extracted zip).

1.  Open the folder in a terminal.

    If you don’t know how: Right-click an empty space inside the folder and select **Services → New Terminal at Folder**.

    -   If that option doesn’t appear: Go to **Finder → Services → Services Settings... → Files and Folders** and enable **New Terminal at Folder**.

1.  Run Kanata:

    ```shell
    chmod +x kanata_macos_cmd_allowed_x64  # Make Kanata runnable.
    sudo ./kanata_macos_cmd_allowed_x64 --cfg example.kbd
    ```

Your keyboard is now using the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite). Press your `q` key&thinsp;&mdash;&thinsp;its output is now `b`. Try other letters!

Stop Kanata by holding: `Left Control + Space + Escape`.

**Troubleshooting:** See [Kanata’s setup guide](https://github.com/jtroo/kanata/blob/main/docs/setup-macos.md#8-troubleshooting).

</details>

<!----------------------------------------------------------------------------->
<!-- macOS 11 and 12 -->

<details>
<summary><strong>macOS 11 and 12</strong></summary>
<p></p>

>   **⚠️ Warning:**
>   There was a report of Kanata [not working on macOS 11](https://github.com/jtroo/kanata/discussions/1242). (Presumably, the user was using Kanata v1.6.1 at the time.) Ben Vallack was able to [run Kanata on macOS 12](https://www.youtube.com/watch?v=4yiMbP_ZySQ&t=1m23s).

If Karabiner Elements is installed: Open **System Settings → General → Login Items & Extensions** and disable **Karabiner-Elements Privileged Daemons v2**.

1.  Download the [Karabiner driver (v3.1.0)](https://github.com/pqrs-org/Karabiner-DriverKit-VirtualHIDDevice/releases/download/v3.1.0/Karabiner-DriverKit-VirtualHIDDevice-3.1.0.pkg) and run the installer.

1.  Open a terminal and activate the driver:

    ```shell
    sudo /Applications/.Karabiner-VirtualHIDDevice-Manager.app/Contents/MacOS/Karabiner-VirtualHIDDevice-Manager activate
    ```

1.  Open **System Settings → General → Login Items & Extensions → Driver Extensions** and toggle on the entry for `org.pqrs.Karabiner-DriverKit-VirtualHIDDevice`.

    -   If you previously ran `deactivate`, restart your computer.

1.  Download Kanata v1.7.0:

    -   Most people should download the [`arm64` version](https://github.com/jtroo/kanata/releases/download/v1.7.0/kanata_macos_cmd_allowed_arm64).
    -   If you’re using an Intel Mac, download the [`x86_64` version](https://github.com/jtroo/kanata/releases/download/v1.7.0/kanata_macos_cmd_allowed_x86_64).

1.  Open **System Settings → Privacy & Security → Input Monitoring** and add the Kanata executable (looks like `kanata_macos_cmd_allowed_...`).

1.  Open **System Settings → Privacy & Security → Accessibility** and add the Kanata executable.

1.  Download [`example.kbd`](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/example.kbd) and put it in the same folder as the Kanata executable.

1.  Open the folder in a terminal.

    If you don’t know how: Right-click an empty space inside the folder and select **Services → New Terminal at Folder**.
    -   If that option doesn’t appear: Go to **Finder → Services → Services Settings... → Files and Folders** and enable **New Terminal at Folder**.

1.  Run Kanata:

    **arm64**

    ```shell
    chmod +x kanata_macos_cmd_allowed_arm64  # Make Kanata runnable.
    sudo ./kanata_macos_cmd_allowed_arm64 --cfg example.kbd
    ```

    **x64**

    ```shell
    chmod +x kanata_macos_cmd_allowed_x64  # Make Kanata runnable.
    sudo ./kanata_macos_cmd_allowed_x64 --cfg example.kbd
    ```

Your keyboard is now using the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite). Press your `q` key&thinsp;&mdash;&thinsp;its output is now `b`. Try other letters!

Stop Kanata by holding: `Left Control + Space + Escape`.

**Troubleshooting:** See [Kanata’s setup guide](https://github.com/jtroo/kanata/blob/main/docs/setup-macos.md#8-troubleshooting).

</details>

<!----------------------------------------------------------------------------->
<!-- macOS 13 and newer -->

<details>
<summary><strong>macOS 13 and newer</strong></summary>
<p></p>

If Karabiner Elements is installed: Open **System Settings → General → Login Items & Extensions** and disable **Karabiner-Elements Privileged Daemons v2**.

1.  Download the [Karabiner driver (v6.2.0)](https://github.com/pqrs-org/Karabiner-DriverKit-VirtualHIDDevice/releases/download/v6.2.0/Karabiner-DriverKit-VirtualHIDDevice-6.2.0.pkg) and run the installer.

1.  Open a terminal and activate the driver:

    ```shell
    sudo /Applications/.Karabiner-VirtualHIDDevice-Manager.app/Contents/MacOS/Karabiner-VirtualHIDDevice-Manager forceActivate
    ```

1.  Open **System Settings → General → Login Items & Extensions → Driver Extensions** and toggle on the entry for `org.pqrs.Karabiner-DriverKit-VirtualHIDDevice`.

    -   If you previously ran `deactivate`, restart your computer.

1.  Download Kanata:

    -   Most people should download the [`arm64` version](https://github.com/jtroo/kanata/releases/latest/download/macos-binaries-arm64.zip).
    -   If you’re using an Intel Mac, download the [`x64` version](https://github.com/jtroo/kanata/releases/latest/download/macos-binaries-x64.zip).

1.  Extract the downloaded zip file.

1.  Open **System Settings → Privacy & Security → Input Monitoring** and add the Kanata executable (looks like `kanata_macos_cmd_allowed_...` in the extracted zip).

1.  Open **System Settings → Privacy & Security → Accessibility** and add the Kanata executable.

1.  Download [`example.kbd`](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/example.kbd) and put it in the same folder as the Kanata executable.

1.  Open the folder in a terminal.

    If you don’t know how: Right-click an empty space inside the folder and select **Services → New Terminal at Folder**.
    -   If that option doesn’t appear: Go to **Finder → Services → Services Settings... → Files and Folders** and enable **New Terminal at Folder**.

1.  Run Kanata:

    **arm64**

    ```shell
    chmod +x kanata_macos_cmd_allowed_arm64  # Make Kanata runnable.
    sudo ./kanata_macos_cmd_allowed_arm64 --cfg example.kbd
    ```

    **x64**

    ```shell
    chmod +x kanata_macos_cmd_allowed_x64  # Make Kanata runnable.
    sudo ./kanata_macos_cmd_allowed_x64 --cfg example.kbd
    ```

Your keyboard is now using the [Gallium layout](https://layouts.wiki/guides/start/recommendations/#gallium-and-graphite). Press your `q` key&thinsp;&mdash;&thinsp;its output is now `b`. Try other letters!

Stop Kanata by holding: `Left Control + Space + Escape`.

**Troubleshooting:** See [Kanata’s setup guide](https://github.com/jtroo/kanata/blob/main/docs/setup-macos.md#8-troubleshooting).

</details>

## Edit the layout

`example.kbd` consists of two parts, `defsrc` and `deflayer`:

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

-   `defsrc` is your keyboard’s original layout (QWERTY).
-   `deflayer` remaps it to Gallium.

Kanata works by mapping keys from `defsrc` to `deflayer` position-by-position.

Replace the contents of `example.kbd` with this, then run Kanata again:

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

You’re using the [Sturdy layout](https://layouts.wiki/guides/start/recommendations/#sturdy). Press your `q` key&thinsp;&mdash;&thinsp;its output is now `v`.

Using a different layout is just a matter of editing the keys in `deflayer` (and renaming the layer to match).

>   [!TIP]
>   To quickly try new layouts, use the `!cmini view [layout]` command in the [Alt Keyboard Layouts Discord](https://discord.gg/4kVZu7uWdy). This returns a text version of the layout that you can copy into a Kanata config file.

## Run Kanata on startup

<!----------------------------------------------------------------------------->
<!-- Windows -->

<details>
<summary><strong>Windows</strong></summary>
<p></p>

1.  Make a shortcut of the Kanata executable.

1.  Open the shortcut’s properties.

1.  Edit **Target** by appending `--cfg "path\to\kanata-config.kbd" --nodelay`. The full target should look like:

    ```
    "path\to\kanata.exe" --cfg "path\to\kanata-config.kbd" --nodelay
    ```

1.  Move the shortcut to the startup folder: `%APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup`.

    -   If you want to use your alt layout immediately after startup: Move the shortcut to the Desktop and double click the shortcut upon signing in.

</details>

<!----------------------------------------------------------------------------->
<!-- Linux -->

<details>
<summary><strong>Linux</strong></summary>
<p></p>

1. Download [`kanata.service`](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/kanata.service) and save it in `/etc/systemd/system/`.

1. Edit this line in `kanata.service` accordingly:

    ```
    ExecStart=/path/to/kanata-executable -c /path/to/kanata-config.kbd
    ```

1. Open a terminal and enable `kanata.service` on startup:

    ```shell
    sudo systemctl enable kanata.service
    ```

</details>

<!----------------------------------------------------------------------------->
<!-- macOS -->

<details>
<summary><strong>macOS</strong></summary>
<p></p>

1. Download [`dev.kanata.kanata.plist`](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/releases/download/download/dev.kanata.kanata.plist) (don’t change the filename) and save it in `/Library/LaunchDaemons`.

1. Open `dev.kanata.kanata.plist` and edit `/path/to/kanata-executable` and `/path/to/kanata-config.kbd` under `ProgramArguments`:

    ```xml
    <key>ProgramArguments</key>
    <array>
        <string>/path/to/kanata-executable</string>
        <string>--cfg</string>
        <string>/path/to/kanata-config.kbd</string>
    </array>
    ```

1. Open a terminal and run Kanata as a Launch Daemon background process:

    ```shell
    sudo chown root:wheel /Library/LaunchDaemons/dev.kanata.kanata.plist
    sudo launchctl bootstrap system /Library/LaunchDaemons/dev.kanata.kanata.plist
    ```

If you edit your Kanata config and want to reload the daemon with your changes, run:

```shell
sudo launchctl kickstart -k system/dev.kanata.kanata
```

</details>

## Other example configs

>   [!NOTE]
>   Learn more about any Kanata feature used below in the [Configuration Guide](https://jtroo.github.io/config.html).

-   [`hold-backtick-to-switch-layouts.kbd`](layouts/hold-backtick-to-switch-layouts.kbd)
    -   Makes holding the `` ` ``/`~` key  toggle between your alt layout and QWERTY
-   [`alt-layout-with-qwerty-shortcuts.kbd`](layouts/alt-layout-with-qwerty-shortcuts.kbd)
    -   Makes holding `Control`, `Alt`, or `Super` temporarily switch to QWERTY
-   [`graphite.kbd`](layouts/graphite.kbd)
    -   A layout that uses non-standard shift pairs (e.g. typing `Shift + ,` outputs `?`, not `<`)
-   [`night.kbd`](layouts/night.kbd)
    -   A [thumb-alpha](https://layouts.wiki/guides/start/recommendations/#thumb-alpha) layout
-   [`whirl.kbd`](layouts/whirl.kbd)
    -   A layout that uses a [magic key](https://layouts.wiki/reference/terminology/magic/)
-   [`afterburner.kbd`](layouts/afterburner.kbd)
    -   A layout that uses a skip magic key
-   [`nordrassil.kbd`](layouts/nordrassil.kbd)
    -   A layout that uses chiral magic keys
-   [`d5.kbd`](layouts/d5.kbd)
    -   A layout that uses chiral skip magic keys
-   [`power.kbd`](layouts/power.kbd)
    -   A layout with 162 Layers

## See also

-   [vscode-kanata](https://github.com/rszyma/vscode-kanata)
    -   A VS Code extension that adds language support for Kanata config files
-   [Windows: Enable Kanata in elevated windows](https://jtroo.github.io/config.html#windows-only-work-elevated)

## Feedback

If anything in this guide is unclear or doesn’t work, please open an [issue](https://github.com/zachpoblete/kanata-guide-for-alt-layouts/issues) or message me (@novachromatic) on the [Alt Keyboard Layouts Discord](https://discord.gg/4kVZu7uWdy).

Suggestions appreciated!
