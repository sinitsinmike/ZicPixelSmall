
Beside the user interface, there is as well hardware controllers, like external midi controller or the builtin buttons and pots. To be able to interact with the user interface, those hardware controllers must also be loaded in the application, using `PLUGIN_CONTROLLER: ../path/of/the/controller.so`

```coffee
PLUGIN_CONTROLLER: ../plugins/build/libzic_MidiEncoderController.so
DEVICE: Arduino Leonardo:Arduino Leonardo MIDI 1
```

Some controller can get extra configuration. Any `KEY: VALUE` following `PLUGIN_CONTROLLER: ` will be forwarded to the controller. In this example, we say to the controller to load the midi device `Arduino Leonardo:Arduino Leonardo MIDI 1`.


## EncoderController

EncoderController is a controller for rotary encoders.


**Config:**

- `ENCODER: id gpioA gpioB [gpioBtn]` will connect to gpioA and gpioB as an encoder. If gpioBtn is set, then it will connect to gpioBtn as a button.

## Mpr121Controller

Mpr121Controller is a controller for MPR121 capacitive touch sensor.

Those sensors used i2c bus. To be able to use it, you need to install pigpio library:

```sh
sudo apt-get install libpigpio-dev
```

You will need to activate the i2c interface in your rasberry pi using raspi-config.

> [!TIP]
> You can use i2cdetect to find the address of your i2c device.
> `sudo apt-get install i2c-tools`
> Use the command `i2cdetect -y 1` to list the addresses.


**Config:**

- `ADDRESS: 0x5c` will connect to i2c device at address `0x5c` and watch all touch inputs. This can be called multiple times to instantiate multiple i2c devices

## NeotrellisController

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/controllers/NeotrellisController.png" />

Keypad interface using [Adafruit Neotrellis M4](https://learn.adafruit.com/adafruit-neotrellis-m4/overview).


- `SERIAL: /dev/ttyACM0` open connection using serial port