node-startup-manager
--------------

[![npm version](https://badge.fury.io/js/node-startup-manager.svg)](http://badge.fury.io/js/node-startup-manager)



Manage Startup tasks for OSX, Windows & Linux ([Ubuntu](http://www.ubuntu.com) & [distros based off of Ubuntu](http://www.omgubuntu.co.uk/2014/06/5-ubuntu-based-distros-better-than-the-real-thing)) for [Node.js](http://nodejs.org) apps.


```js
var startupManager = require('node-startup-manager');

var opts = {
    appPath: 'C:/Program Files/RealVNC/VNC Server/vncserver.exe', //Remeber to path.normalize() any path to make sure its os compatable 
    appName: 'My_Awesome_App' //What your app shows up in startup list
};

startupManager.addStartup(opts)
    .then(function() {
        console.log('App added to startup')
    })
    .catch(function(e) {
        Console.log('Something went wrong; Perms?', e)
    });

startupManager.removeStartup('My_Awesome_App')
    .then(function() {
        console.log('App removed from startup')
    })
    .catch(function(e) {
        Console.log('Something went wrong; Perms?', e)
    });

startupManager.checkStartup('My_Awesome_App')
    .then(function(status) {
        console.log('App statup status:', status) // status returned as a boolen
    });

```

## Installation

```bash
$ npm install node-startup-manager --save
```
