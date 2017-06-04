# Homebridge Dyson
HomeBridge interface to Dyson Link smart purifiers.

This HomeBridge plugin is Beta and not affiliated with, or endorsed by Dyson.

## Configuration

Connection to the Dyson Link smart accessory requires a username and password, both of which you can derive from your front sticker or user manual.

The username is your device serial ID - you can derive this from your product SSID by removing `DYSON-` from the start and `-475` from the end.  It is also shown on the Dyson Link app.

The password is a base-64 encoded SHA-512 hash of the password shown on your front sticker or user manual.  [You can use this online tool to help derive your encoded hash.](http://hash.online-convert.com/sha512-generator)

Each fan also has its own region, you need to make sure your region code lines up with the region code set in the `index.js` this can be discovered by using some form of MQTT spy on your local network to determine what region code your device is using, for exmaple the United Kingdom code is `469` and the US code is `475`. You can define the region code at line `113`.

## Example HomeBridge config.json entry

```
"accessories": [
  {
    "accessory": "dyson-coollink",
    "name": "Dyson Tower",
    "ip": "10.0.1.x",
    "username": "...",
    "password": "..."
  }
],
```
