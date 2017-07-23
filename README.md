# MMM-IndoorTemp

This is an extension for the [MagicMirror²](https://github.com/MichMich/MagicMirror).  It emits the notification "INDOOR_TEMPERATURE" to display the indoor temperature received via a subscribed MQTT topic. The module is based on Javier Ayala's module [MMM-mqtt](https://github.com/javiergayala/MMM-mqtt).

It's working with every temperatur MQTT topic. If you're looking for a sensor, you can easily start with a WeMos D1 mini in combination with a DHT Shield and the firmware based on Homie. You can find it in the other folders.

## MagicMirror Module Installation
1. Ensure that you have the necessary libraries/clients for mqtt installed on the computer that will be running this extension.  (For example, running `sudo apt-get install mosquitto mosquitto-clients` on Debian-based distributions.)
2. Install  [mqtt](https://www.npmjs.com/package/mqtt) via `npm install mqtt`.
3. Navigate into your MagicMirror's `modules` folder and execute `git clone https://github.com/sebastianhodapp/MMM-IndoorTemp.git`. A new folder will appear, likely called `MMM-IndoorTemp`.  Navigate into it.
3. Execute `npm install` to install the node dependencies.

## Using the module
To use this module, add it to the modules array in the `config/config.js` file:
````javascript
modules: [
	{
		module: 'MMM-IndoorTemp',
		position: 'top_right',							// This can be any of the regions..
		header: 'Living Room Temperature', 	// This is optional and only needed if you want to display the temperature
		config: {
			// See 'Configuration options' for more information.
		}
	}
]
````

## Configuration options

The following options can be configured:

| Option  | Description  |
|---|---|
| `mqttServer`  | Connection string for the server to connect to (`mqtt://localhost`)  |
| `topic`  | MQTT Topic to subscribe to on the server (`sensors/temperature/livingroom`)  |
| `interval`  | Refresh interval, not including MQTT subscription deliveries. (default: `300000`)  |
| `debug`  | Do you want to see the received information in a seperate module posiiton?. (default: false)  |
| `showAlerts`  | Should Alerst in case of connection issues with the broker be shown??. (default: true)  |
| `showTitle`  | Boolean to show/hide a title (default: `false`)  |
| `title`  | Title to show if `showTitle` is `true`  |
| `postText`  | Text to append after the data received from MQTT (default: `''`)  |


## Known Limitations
- Currently only supports unencrypted/unauthenticated MQTT connections.  

## Dependencies
- [mqtt](https://www.npmjs.com/package/mqtt) (installed via `npm install`)

## Contributing Guidelines

Contributions of all kinds are welcome, not only in the form of code but also with regards bug reports and documentation.

Please keep the following in mind:

- **Bug Reports**:  Make sure you're running the latest version. If the issue(s) still persist: please open a clearly documented issue with a clear title.
- **Minor Bug Fixes**: Please send a pull request with a clear explanation of the issue or a link to the issue it solves.
- **Major Bug Fixes**: please discuss your approach in an GitHub issue before you start to alter a big part of the code.
- **New Features**: please please discuss in a GitHub issue before you start to alter a big part of the code. Without discussion upfront, the pull request will not be accepted / merged.

The MIT License (MIT)
=====================

Copyright © 2017 Sebastian Hodapp

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the “Software”), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

**The software is provided “as is”, without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages or other liability, whether in an action of contract, tort or otherwise, arising from, out of or in connection with the software or the use or other dealings in the software.**
