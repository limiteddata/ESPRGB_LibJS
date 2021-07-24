# ESPRGB_LibJS

This is a library made to simplify the development of ESPRGB clients in javascript by handling everything in the back so you'll only need to bind buttons and change variables with the provided events.<br>

It creates the websocket connection required, it parses all the messages, emits events when a variable changes and it includes all the function you need to change the animations and parameters.

## Include

```
<script src="./ESPRGB_LibJS.js" ></script>
or
const ESPRGB = require("esprgb_libjs")
```

## Usage

```
<button onclick="myDevice.ConnectToggle()">Connect</button>
<button onclick="myDevice.restart()">restart</button>
<button onclick="myDevice.format()">format</button>
<button onclick="myDevice.removeUserData()">remove user data</button>

var myDevice = new ESPRGB('esprgb-test.local');
// events
myDevice.SolidColor.on('Color:change', (e)=>{
    document.getElementById("SolidColorR").value = e.Color[0];
    document.getElementById("SolidColorG").value = e.Color[1];
    document.getElementById("SolidColorB").value = e.Color[2];
});
myDevice.SolidColor.on('Brightness:change', (e)=> document.getElementById('SolidColor_Brightness').value = e.Brightness*100 );
```

For more code check the demo.html 