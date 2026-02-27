# irc (dot) py

A lightweight, minimalist IRC client written in pure Python. It provides a modern tabbed interface within your terminal using `curses`, supporting multiple simultaneous server connections and SSL by default.

## Features

+ **Zero Dependencies:** Runs on any system with Python 3.7+ (uses only the standard library).
+ **Multi-Server Support:** Connect to several networks at once, each with its own set of tabs.
+ **Tabbed Interface:** Easily switch between channels and NickServ panes with hotkeys.
+ **Auto-Reconnect:** Automatically attempts to restore dropped connections.
+ **SSL/TLS:** Secure connections enabled by default for all servers.
+ **Clean TUI:** Integrated input history, unread message indicators, and color-coded segments.

---

## Installation & Setup

1. **Download the script:** Save the code to `~/.local/bin/irc`.
2. **Make it executable:**
```bash
chmod +x ~/.local/bin/irc
```

> Update your PATH (if needed):
> For your terminal to recognize the irc command from anywhere, `~/.local/bin` must be in your system's PATH. Check if it's already there by running echo $PATH. > If it isn't, add it to your .bashrc with this command:
> 
> `echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc`


## Configuration

Before launching, open the script in your favorite editor and locate the `SERVERS` section (at the top) & update the configuration with your preferred networks etc:

```python
SERVERS = [
    {
        "name":     "Libera",
        "host":     "irc.libera.chat",
        "port":     6697,
        "nick":     "YourNick",
        "pass":     "YourPassword",
        "channels": ["#python", "#linux"],
    },
]
```

## Navigation

| Key | Action |
| --- | --- |
| **Alt + 1...9** | Switch to Tabs 1 through 9 |
| **Alt + 0** | Switch to Tab 10 |
| **Ctrl + N** / **Ctrl + →** | Cycle to the next tab |
| **Ctrl + P** / **Ctrl + ←** | Cycle to the previous tab |
| **Ctrl + L** | Force a full UI redraw |
| **Up / Down Arrow** | Scroll through your sent message history |

## Commands

Type these directly into the input box at the bottom of the screen:

+ `/join #channel` — Join a new channel on the active server.
+ `/part` — Leave the current channel.
+ `/ns <command>` — Send a command directly to NickServ (e.g., `/ns identify password`).
+ `/msg <nick> <text>` — Send a private message to a specific user.
+ `/server <Name>` — Set the context for the next `/join` command to a different connected server.
+ `/quit` — Disconnect from all servers and exit the application.


## Tips

Every server has a dedicated `NS` tab. Direct notices from the server and private messages that don't belong to a specific channel will appear here to keep your chat logs clean.
