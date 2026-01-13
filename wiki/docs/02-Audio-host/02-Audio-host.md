
ZicBox can be used with or without user interface, either by using zicHost application or by loading zicHost shared library into another application. By default, zicHost is loaded as a shared library into zicBox to provide a UI on top of it.

The audio host can be configured using a config file (by default `config.cfg`):

```coffee
# Here we define the Digitone as midi controller
MIDIIN: Elektron Digitone MIDI 1

AUDIO_PLUGIN: AudioInput ./plugins/audio/build/libzic_AudioInputPulse.so
  DEVICE: alsa_input.usb-Elektron_Music_Machines_Elektron_Digitone_000000000001-00.analog-stereo

AUDIO_PLUGIN: Distortion ./plugins/audio/build/libzic_EffectDistortion.so
# Here we assign message to control the drive distortion
# Where xx is the variable value that will be from 0 to 127
# And b0 48 is the fixed part of message corresponding to CC channel 1 number 0x48 (or 72)
  MIDI_CC: DRIVE b0 48 xx

AUDIO_PLUGIN: MultiModeFilter ./plugins/audio/build/libzic_EffectFilterMultiMode.so
  MIDI_CC: CUTOFF b0 4c xx
  MIDI_CC: RESONANCE b0 4d xx
```


## Global and generic config

> [!NOTE]
> Generic config are configs that can be used by any plugin. This must be passed after a plugin has been defined.


- `MIDI_CC: CUTOFF b0 4c xx` assign a midi CC command to a given plugin value (this is a generic config).

- `MIDI_CHANNEL: 1` assign a midi channel to a given plugin for a note on/off (this is a generic config).

- `TRACK_MIDI_CHANNEL: track channel` assign a midi channel to a given track for a note on/off, e.g. `TRACK_MIDI_CHANNEL: 1 2`

> Find an example on how to use the host embedded in your own application: `use_host_demo.cpp`.
