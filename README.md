## Xbringup – Brings up last used windows via the keyboard quickly

Activate last used windows easily with this bash script.
Here's how it works:

- If no window of the app exist, execute a custom command ie. launch the app.
- If only one instance of the app exist and it's currently active, minimize it.
- If one or more instances of the app exist, activate the _last_ used window.

## Installation

### Prerequisites

Xbringup requires a EWMH/NetWM compatible X Window Manager that manages `_NET_ACTIVE_WINDOW` and `_NET_CLIENT_LIST_STACKING` properties. Most window managers support these by default.

Xbringup uses two existing automation tools created for the X server, `xdotool` and `wmctrl` to activate, query and minimize X windows.

```sh
sudo apt install xdotool wmctrl
```

### Cloning the repository

```sh
git clone https://github.com/jdqo/xbringup.git ~/xbringup.git
```

### Usage

```
./xbringup -h
# Usage: xbringup [-h] WM_CLASS CMD ...
#
#   Xbringup – Brings up last used WM_CLASS or alternatively execs the given CMD.
#
# Options:
#   -h,                   Show this message and exit.
#
# Arguments:
#   WM_CLASS,             Bring up last used given WM_CLASS, if only one instance
#                         exists and it's currently active, minimize it.
#   CMD,                  Executes the command if no given WM_CLASS was found.
#
# Examples:
#   xbringup "Navigator.firefox" "firefox"
#   xbringup "Sandboxed.firefox" "xdg-open /home/foobar/Desktop/sandbox.desktop"
```

## License

Distributed under the AGPLv3 License. See `LICENSE` for more information.
