# VL.SuperMonitor

A VL lib to do all sorts of things with Renderers and monitors

## Disclaimer

*This project is still at a research stage and clearly **not** meant to be used for production!*

## Installation

Open VL's command-line (Quad Menu/Manage Nugets/Command Line) and type

```
nuget install VL.SuperMonitor -pre
```

## What's inside

First, this library wraps the [Monitor Details Reader](https://github.com/allanrodriguez/MonitorDetailsReader) nuget, that allows to "retrieve current settings and useful information about the monitors connected to the host computer, including pixel dimensions, physical measurements, EDID, monitor handles, and virtual screen coordinates."

Thanks to that useful set of nodes, the library also offers the following nodes :

- `GetMonitorDetails` : outputs a `Spread<Monitor>`, containing some detailed informations about each of your connected monitors
- `OnMonitorSetupChanged` : outputs an `Observable<Spread<Monitor>>` when a device is added/removed from the computer. In practice, this one fires on each device add/remove (even your mouse) since I could not find a way to filter monitor only hardware change events
- `MonitorHelper` : spawns a fullscreen Renderer on each of your monitors with some usefull information about them. Press <kbd>ESC</kbd> to destroy the Renderers
- `AssignToSerialNumber` : a small node that allows to place a Renderer on a specific monitor based on its serial number. For now, it does not make it fullscreen since I encoutered some issues when doing that, but that's the next thing to dig

There's a small help patch for each of those, check the help browser.

## Contributing ?

If you'd like to participate to this research, don't hesitate to create a PR!
