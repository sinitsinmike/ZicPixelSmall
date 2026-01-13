
By default ZicBox use [DustScript](https://github.com/apiel/dustscript) to set configuration. Configuration are set using a plugin, script language can be used, like Lua.

To load a different scripting language call zicBox like this:
```sh
./zicBox myconfig_file path/to/configLib.so
```

Lua extension will be recognized by default, so calling `./zicBox myconfig_file.lua` is enough, there is no need to specify the config plugin. If the extension is not recognized and no config plugin specified, it will by default use DustScript.



## JsConfig

JsConfig is a plugin for ZicBox that allows you to set config from a js script. It is based on [Duktape](https://duktape.org/) javascript interpreter.
To use it, you need to install Duktape and Duktape-dev:

```sh
apt-get install libduktape207 duktape-dev
```

To set config from a js script, you need to call `zic(key, value);` in the js script:

```js
zic("print", "Call ZicBox print from Lua.")
zic("PLUGIN_COMPONENT", "Encoder2 ./plugins/components/build/libzic_Encoder2Component.so")
zic("LOAD_HOST", "config.cfg")
zic("VIEW", "Main")

// Let's create an encoder function
function setEncoder(x, y, width, height, encoder_id, value) {
  zic("COMPONENT", "Encoder2 " + x + " " + y + " " + width + " " + height);
  zic("ENCODER_ID", encoder_id);
  zic("VALUE", value);
}

setEncoder(10, 10, 100, 100, 1, "FM DECAY_1");

// ...
```

Finally run zicBox like this:
```sh
./zicBox config.js plugins/config/build/libzic_JsConfig.so
```

> [!NOTE]
> Duktape is a subset of JavaScript and might not support all features.


## LuaConfig

To set config from a lua script, you need to call `zic(key, value)` in the lua script:

```lua
zic("print", "Call ZicBox print from Lua.")
zic("PLUGIN_COMPONENT", "Encoder2 ./plugins/components/build/libzic_Encoder2Component.so")
zic("LOAD_HOST", "config.cfg")
zic("VIEW", "Main")

-- Let's create an encoder function
function setEncoder (x, y, width, height, encoder_id, value)
  zic("COMPONENT", "Encoder2" .. x .. " " .. y .. " " .. width .. " " .. height)
  zic("ENCODER_ID", encoder_id)
  zic("VALUE", value)
end

setEncoder(10, 10, 100, 100, 1, "FM DECAY_1")

-- ...
```

It might be necessary to install liblua5.4-dev:
```sh
sudo apt-get install liblua5.4-dev
```
