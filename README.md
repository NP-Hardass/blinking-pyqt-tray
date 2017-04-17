# blinking-pyqt-tray
A Qt based tray icon written in Python

This repository is meant to be a companion to [weechat-tray (tnotify.py)](https://github.com/NP-Hardass/weechat-tray), but has nothing specific to that project and can be used in/with other applications.

## Requirements
* &gt;=Python-2.7
* PyQt4, PyQt5, or PySide

## How it works
systray.py creates a SystemTrayIcon object with signal handlers SIGUSR1 (start blinking) and SIGUSR2 (stop blinking).  When clicked, if a executable was passed as an arg, the tray icon executes the given command.
Due to SystemTrayIcon not supporting blinking (to the best of my knowledge at the time of writing), blinking is simulated by toggling between two icons at an interval.

### Usage:
systray.py [-h] pidfile icon_path alt_icon_path [onclick_exec]

positional arguments:
  pidfile        Path to save our PID
  icon_path      Path to primary icon
  alt_icon_path  Path to icon to emulateblinking
  onclick_exec   Command to executeon mouse click
