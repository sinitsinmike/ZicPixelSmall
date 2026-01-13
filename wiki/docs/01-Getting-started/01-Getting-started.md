
ZicBox is working on Linux plateform, the end target is to run on RaspberryPi but it should run on any linux machine. In my case, I am actively using it on my Ubuntu desktop for development purpose. I beleive that it could also easily run on MacOs, but I don't have a Mac, so I cannot try out (if you manage to do so, please let me know).

## Configuration

ZicBox is fully customizable using configuration files. Everyhting is build base on plugins, from user interface, to audio module and hardware controller. ZicBox then wire everything so that everything can communicate together.

The main configuration file is `./config.ui`.

> To get styling for .ui extension in VScode, use `Ctrl` + `Shift` + `P` and type `Change Language Mode`. Then select `Configure File Association for '.ui'...` and select `CoffeScript`.

Those `.ui` files are simple configuration files. It is base on [DustScript](https://github.com/apiel/dustscript) mainly using `KEY:VALUE` to set the configuration and providing some basic extra feature on top of it, like variable, if statement and while loop. However, using those script features are not mandatory and the UI can be fully configured without it.

> [!TIP]
> Instead to use DustScript, Lua can be used or any other configuration plugin, see [06-Config-plugins](https://github.com/apiel/zicBox/wiki/06-Config-plugins).

The user interface is composed of views and components. A view is composed of multiple components. A component is for example a button or a rotary encoder. Each of the UI components are external shared library that can be loaded dynamically when the application start.

From the audio perspective, there is an audio buffer splitted in tracks (32 by default). Audio plugins are assign per track but can also manipulate multiple tracks, like the audio mixer.

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/zicbox.drawio.svg" />

## Installation

```ssh
git clone --recurse-submodules https://github.com/apiel/zicBox.git
```

> If repo has already been cloned but submodule are missing, use `git submodule update --init` to pull them.
> For `ssh` submodule `git submodule update --init .gitmodules_ssh`

Compiler:
```sh
sudo apt install build-essential
```

Audio:

```sh
sudo apt install librtmidi-dev libsndfile1-dev
```

User interface:

```sh
sudo apt-get install fonts-roboto libsdl2-dev libsdl2-ttf-2.0-0 libsdl2-ttf-dev
```

Controller:

```sh
sudo apt-get install liblo-dev
```

Config:

```sh
sudo apt-get install liblua5.4-0 liblua5.4-dev
```


### On RPi

Might Need to install pulse audio as well:

```sh
sudo apt-get install alsa-base pulseaudio
```

If not started automatically, it can be started with:

```sh
pulseaudio --start
```

Get list of audio card:

```sh
cat /proc/asound/cards
# or
arecord -l
# or
aplay -l
```


### PLUGIN_COMPONENT

        A component must be load from a shared library (those `.so` files). To load those plugin components, use `PLUGIN_COMPONENT: given_name_to_component ../path/of/the/component.so`.

        ```coffee
        PLUGIN_COMPONENT: Encoder ../plugins/build/libzic_EncoderComponent.so
        ```

        In this example, we load the shared library `../plugins/build/libzic_EncoderComponent.so` and we give it the name of `Encoder`. The `Encoder` name will be used later to place the components in the view.


### COMPONENT

        To place previously loaded components inside a view, use `COMPONENT: given_name_to_component x y w h`.

        ```coffee
        COMPONENT: Encoder 100 0 100 50
        ENCODER_ID: 1
        VALUE: MultiModeFilter RESONANCE
        ```

        A component can get extra configuration settings and any `KEY: VALUE` following `COMPONENT: ` will be forwarded to the component.
        In this example, we assign the hardware encoder id 1 to this component and we assign it to the resonance value from the multi mode filter audio plugin.


### VIEW

The user interface is composed of multiple views that contain the components. A view, represent a full screen layout. Use `VIEW: name_of_the_veiw` to create a view. All the following `COMPONENT: ` will be assign to this view, till the next view.

```coffee
# VIEW: ViewName

VIEW: Main

# some components...

VIEW: Mixer

# some components...
# ...
```
