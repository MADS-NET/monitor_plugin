# monitor_plugin plugin for MADS

This is a Sink plugin for [MADS](https://github.com/MADS-NET/MADS). 

It keeps track of all agents publishing on the network and of how long since they have been publishing. There's of course no way to track pure sinks.

*Required MADS version: 2.0.0.*


## Supported platforms

Currently, the supported platforms are:

* **Linux** 
* **MacOS**
* **Windows**


## Installation

Linux and MacOS:

```bash
cmake -Bbuild -DCMAKE_INSTALL_PREFIX="$(mads -p)"
cmake --build build -j4
sudo cmake --install build
```

Windows:

```powershell
cmake -Bbuild -DCMAKE_INSTALL_PREFIX="$(mads -p)"
cmake --build build --config Release
cmake --install build --config Release
```


## INI settings

The plugin supports the following settings in the INI file:

```ini
[monitor]
sub_topic = [""] # Subscribe to all topics
col_widths = [18, 15, 15] # Widths of first three columns
yellow = 0.1 # seconds: color yellow periods larger than that
red = 0.1    # seconds: color red periods larger than that
silent = true
```

All settings are optional; if omitted, the default values are used.



---