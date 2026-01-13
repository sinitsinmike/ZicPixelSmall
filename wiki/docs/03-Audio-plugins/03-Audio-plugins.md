
ZicHost take care to load and handle audio plugins. Each plugins have access to the 32 audio tracks buffer to manipulate them. Those plugins are called in loop in the same order as they have been instanciated. A plugin can be loaded multiple times under a different name, see `AUDIO_PLUGIN` configuration in previous section.


## AudioInputAlsa

AudioInputAlsa plugin is used to read audio input from ALSA.

**Value**:
- `DEVICE: name` to set input device name. If not defined, default device will be used.


## AudioInputPulse

AudioInputPulse plugin is used to read audio input from PulseAudio.

**Value**:
- `DEVICE: name` to set input device name. If not defined, default device will be used.


## AudioOutputAlsa

AudioOutputAlsa plugin is used to write audio output to ALSA.

**Value**:
- `DEVICE: name` to set output device name. If not defined, default device will be used.


## AudioOutputPulse

AudioOutputPulse plugin is used to write audio output to PulseAudio.

**Value**:
- `DEVICE: name` to set output device name. If not defined, default device will be used.


## AudioSpectrogram

AudioSpectrogram plugin is used to keep track of audio buffer.


**Data ID**:

- `BUFFER` return a representation of the current audio track

## EffectDelay

EffectDelay plugin is used to apply delay or reverb effect on audio buffer.

> [!NOTE]
> - `TODO` load/save different kind of delay and reverb from a config file
> - `TODO` add lfo on time ratio


**Values**:

- Delay has 8 voices

- `AMPLITUDE_0` to set amplitude on voice 0.

- `AMPLITUDE_1` to set amplitude on voice 1.

- ...

- `FEEDBACK_0` to set feedback on voice 0.

- `FEEDBACK_1` to set feedback on voice 1.

- ...

- `TIME_0` to set time ratio for voice 0.

- `TIME_1` to set time ratio for voice 1.

- ...

- `TIME_RATIO` to modulate time ratio for all voices.

- `MASTER_AMPLITUDE` to set master amplitude.

- `VOICE_EDIT` select the step to edit

- `VOICE_AMPLITUDE` to set amplitude on selected voice.

- `VOICE_FEEDBACK` to set feedback on selected voice.

- `VOICE_SEC` to set sec on selected voice.

- `CUTOFF` to set cutoff on delay buffer.

- `RESONANCE` to set resonance on delay buffer.

- `MODE` to set filter mode.

## EffectDistortion

EffectDistortion plugin is used to apply distortion effect on audio buffer.


**Values**:

- `DRIVE` to set drive.

- `DRIVE2` to set drive2.

- `GAIN_RATIO` to set makeup gain.

- `DB` to set the clipping level threshold.

- `ENABLED` to enable the effect.

## EffectDistortion2

EffectDistortion2 plugin is used to apply distortion effect on audio buffer.


**Values**:

- `LEVEL` to set distortion mix level.

- `DRIVE` to set distortion drive.

- `COMPRESS` to set distortion compression.

- `BASS` to set bass boost.

- `WAVESHAPE` to set waveshape.

## EffectDrum

EffectDrum plugin is used to apply effect to drum tracks.


**Values**:

- `VOLUME` to set volume. Till 100, it is the volume percentage, after 100 it is the gain.

- REVERB controls delay time, feedback, and mix with one parameter.

- `CUTOFF` to set cutoff frequency and switch between low and high pass filter.

- `RESONANCE` to set resonance.

## EffectFilter

EffectFilter is a simple resonant filter.


**Values**:

- `CUTOFF` set cutoff.

- `RESONANCE` set resonance.

- `MODE` set filter mode.

## EffectFilterMultiMode

EffectFilterMultiMode plugin is used to apply filter effect on audio buffer.
Cutoff frequency will switch from low pass filter to high pass filter when reaching 50%.


**Values**:

- `CUTOFF` to set cutoff frequency and switch between low and high pass filter.

- `RESONANCE` to set resonance.

- `STRING_CUTOFF_FORMAT` set the string value format for the cutoff.

## EffectFilterMultiModeMoog

EffectFilterMultiModeMoog plugin is used to apply a simulation of the Moog filter on audio buffer.
Cutoff frequency will switch from low pass filter to high pass filter when reaching 50%.


**Values**:

- `CUTOFF` to set cutoff frequency and switch between low and high pass filter.

- `RESONANCE` to set resonance.

## EffectGainVolume

EffectGainVolume plugin is used to apply gain and volume on audio buffer.


**Values**:

- `VOLUME` to set volume.

- `GAIN` to set gain.

## EffectGrain

EffectGrain plugin is used to apply granular effect to a buffer audio.


**Values**:

- `LENGTH` set the duration of the grain.

- `DENSITY` set the density of the effect, meaning how many grains are played at the same time.

- `DENSITY_DELAY` set the delay between each grains.

- `ENVELOP` set the envelop of the grains.

- `PITCH` Modulate the pitch.

- `DELAY_RANDOMIZE` set the density delay randomize. If randomize is set, the density starting delay is random and while change on each sustain loop.

- `PITCH_RANDOMIZE` set the pitch randomize. If randomize is set, the pitch is random and while change on each sustain loop.`

- `DIRECTION` set the direction of the grain.

## EffectSampleRateReducer

EffectSampleRateReducer plugin is used to reduce sample rate on audio buffer.


**Values**:

- `SAMPLE_STEP` to set sample step reduction.

## EffectVolumeClipping

EffectVolumeClipping plugin is used to clipping and volume on audio buffer.


**Values**:

- `VOLUME` to set volume. Till 100, it is the volume percentage, after 100 it is the gain.

- `GAIN_CLIPPING` set the clipping level.

- `DRIVE` to set drive and compression.

## EffectVolumeDrive

EffectVolumeDrive plugin is used to apply gain and volume on audio buffer.


**Values**:

- `VOLUME` to set volume. Till 100, it is the volume percentage, after 100 it is the gain.

- `DRIVE` to set drive and compression.

## Mixer

Mixer audio plugin is used to mix tracks together.

- `Mixer4` is a 4-track mixer.
- `Mixer8` is a 8-track mixer.
- `Mixer12` is a 12-track mixer.


And input tracks start at 1, then 2, 3, ....

**Value**:

- `TRACK_1` to set volume on track 1, min = 0.0, max = 100.

- `TRACK_2` to set volume on track 2.

- ...

- `MUTE_1` to mute track 1, `0.0` to unmute, `1.0` to mute.

- `MUTE_2` to mute track 2.

- ...

**Config**:

- `TRACK_START: 7` to set track 7 as first track, then 8, 9, ...

- `DIVIDER: 0.5` to set a custom divider. By default, divider equals 1 divided by the number of tracks.

- `VALUE_1: 0.5` to set track 1 volume to 50%.

- `TRACK_1: 1` to set track input 1 on track buffer 1.

- `TRACK_2: 2` to set track input 2 on track buffer 2.

- ...

## RamTapeRecording

RamTapeRecording plugin is used to record audio buffer for a given track.


**Values**:

- `TRACK` to set the track number.

**Config**:

- `TAPE_FOLDER` set samples folder path.

- `FILENAME: filename` to set filename. By default it is `track`.

- `MAX_FILE_SIZE: 200` to set max file size. By default it is `200MB`.

- `CIRCULAR_BUFFER: true` to enable circular buffer. By default it is `true`.

**Values**:

- `STEP_VELOCITY` set selected step velocity

- `STEP_START` set selected step sample start point

- `STEP_END` set selected step sample end point

- `STEP_ENABLED` toggle selected step

- `STEP_FILENAME` select sample file for selected step

- `SELECTED_STEP` select the step to edit

## Sequencer

Sequencer audio module can be used to sequence another audio plugin on 32 steps. Each step can be triggered by a condition:

- `---` - always
- `Pair` - every second step
- `4th` - every fourth step
- `6th` - every sixth step
- `8th` - every eighth step
- `Impair` - every impair step
- `1%` - 1% probability, meaning that it has 1 chance over 100 to be triggered
- `2%` - 2% probability
- `5%` - 5% probability
- `10%` - 10% probability
- `20%` - 20% probability
- `30%` - 30% probability
- `40%` - 40% probability
- `50%` - 50% probability
- `60%` - 60% probability
- `70%` - 70% probability
- `80%` - 80% probability
- `90%` - 90% probability
- `95%` - 95% probability
- `98%` - 98% probability
- `99%` - 99% probability


**Values**:

- `DETUNE` detuning all playing step notes by semitones

- `SELECTED_STEP` select the step to edit

- `STEP_VELOCITY` set selected step velocity

- `STEP_LENGTH` set selected step length

- `STEP_CONDITION` set selected step condition

- `STEP_MOTION` set selected step motion

- `STEP_NOTE` set selected step note

- `STEP_ENABLED` toggle selected step

**Data ID**:

- `STEPS` return steps

- `STEP_COUNTER` return current played step

- `IS_PLAYING` return is playing

- `STEP_CONDITION` return current step condition

- `CLOCK_COUNTER` return clock counter

- `GET_STEP` get step by index

- `SELECTED_STEP_PTR` return selected step pointer

- `STEP_TOGGLE` toggle selected step

## SerializeTrack

SerializeTrack plugin is used to serialize track on disk. It will scan all the plugins on the given track and save them on disk.


**Values:**

- `VARIATION` switch between different track serialization variations (clip).

**Config**:

- `FILENAME: filename` to set filename. By default it is `track`.

- `WORKSPACE_FOLDER: workspaceFolder` to set workspace folder. By default it is `workspaces`.

- `MAX_VARIATION: 12` to set max variation. By default it is `12`.

- `EDIT_VARIATION: true` toggle to enable variation edit mode. If set to false variation will be read only. If set to true, every changes will be save before to switch to the next variation. Default is false`

**Data ID**:

- `SET_FILENAME` set filename

- `SERIALIZE` serialize

- `HYDRATE` hydrate

- `GET_VARIATION` get variation

- `GET_VARIATION_PATH` get variation path

- `SAVE_VARIATION` save variation

- `LOAD_VARIATION` load variation

- `LOAD_VARIATION_NEXT` load variation at the next sequencer loop

- `DELETE_VARIATION` delete variation

- `CREATE_WORKSPACE` create workspace

- `LOAD_WORKSPACE` load workspace

- `CURRENT_WORKSPACE` get current workspace

- `DELETE_WORKSPACE` delete workspace

## SynthBass

Synth engine to generate bass sounds.


**Values**:

- `PITCH` set the pitch.

- `DURATION` set the duration of the envelop.

- `DECAY_LEVEL` set the decay level.

- `DECAY_TIME` set the decay time percentage base on the total duration.

- `CUTOFF` to set cutoff frequency of low pass filter.

- `RESONANCE` to set resonance.

- `GAIN_CLIPPING` set the clipping level.

- REVERB controls delay time, feedback, and mix with one parameter.

- FREQ_RATIO sets the frequency of the bass.

- `WAVEFORM_TYPE` Select waveform type (wavetable, sawtooth, square...).

- `SHAPE` Morhp over the waveform shape.

- `MACRO` Macro is arbitrary parameter depending of selected waveform type.

- `BOOST` to set compression or bass boost.

## SynthClap

Synth engine to generate drum clap.


**Values**:

- DURATION sets the total duration of the clap envelope.

- TONE_CUTOFF sets the base high-pass filter cutoff frequency.

- TRANSIENT_SPREAD adjusts the spread between transients.

- SINE_FREQUENCY sets the frequency of the sine wave transient component.

- SINE_BLEND sets the amplitude of the sine wave transient component.

## SynthDrum23

Synth engine to generate drum sounds using wavetables.


**Values**:

- `WAVEFORM_TYPE` Select waveform type (wavetable, sine, triangle...).

- `SHAPE` Morhp over the waveform shape.

- `MACRO` Macro is arbitrary parameter depending of selected waveform type.

- `PITCH` Modulate the pitch.

- `DURATION` set the duration of the envelop.

- `GAIN_CLIPPING` set the clipping level.

- `CLICK` set the click level.

- `CLICK_DURATION` set the duration of the click.

- `CLICK_CUTOFF` set the cutoff frequency of the click.

**Data ID**:

- `ENV_AMP` update the amplitude for current step

- `ENV_AMP_EDIT` set/get the amplitude edit point for current step

- `ENV_AMP_TIME` update the amplitude time for current step

- `ENV_AMP_MOD` update the amplitude modulation value for current step

- `ENV_FREQ` get the frequency envelop

- `ENV_FREQ_EDIT` set/get the frequency edit point for current step

- `ENV_FREQ_TIME` update the frequency time for current step

- `ENV_FREQ_MOD` update the frequency modulation value for current step

- `ENV_FREQ2` get the frequency envelop

- `ENV_FREQ_MODE` update the envelop frequency mode

- `ENV_FREQ_IS_MACRO` get the envelop frequency edit mode

- `ENV_FREQ_MACRO1` set the macro 1 value for frequency envelop

- `ENV_FREQ_MACRO2` set the macro 2 value for frequency envelop

- `ENV_FREQ_MACRO3` set the macro 3 value for frequency envelop

- `WAVEFORM` return a representation of the selected waveform

## SynthDrumSample

SynthDrumSample is a very basic plugin to play one shot sample.


**Values**:

- `START` set the start position of the sample

- `END` set the end position of the sample

- `BROWSER` to browse between samples to play.

**Config**:

- `SAMPLES_FOLDER` set samples folder path.

## SynthFM

Fm synth engine using 4 operators.

Work in progress


**Values**:

- `ALGO` set the FM algorithm.

**Data ID**:

- `ALGO` return current algorithm

## SynthFM2

Fm synth engine using 4 operators.

Work in progress


**Data ID**:

- `ALGO` return current algorithm

## SynthFmDrum

Synth engine to make FM drum.


**Values**:

- CARRIER_FREQ sets the frequency of the carrier wave.

- MOD_FREQ sets the frequency of the modulator wave.

- MOD_INDEX controls the intensity of frequency modulation.

- ATTACK_TIME sets the attack time of the envelope.

- DECAY_TIME sets the decay time of the envelope.

- NOISE_LEVEL adds white noise to the output.

- `DISTORTION` to set distortion.

- REVERB controls delay time, feedback, and mix with one parameter.

## SynthHiHat

Synth engine to generate HiHat sounds.


**Values**:

- `DURATION` set the duration of the envelop.

- `BAND_FREQ` set the band frequency.

- `BAND_Q` set the band Q.

- `TRANSIENT_INTENSITY` set the transient intensity.

- `METALLIC_TONE_MIX` set the metallic tone mix.

- `TONE_BRIGHTNESS` set the tone brightness.

## SynthKick23

Synth engine to generate drum sounds using wavetables.


**Values**:

- `BROWSER` Select wavetable.

- `MORPH` Morhp over the wavetable.

- `PITCH` Modulate the pitch.

- `DURATION` set the duration of the envelop.

- `GAIN_CLIPPING` set the clipping level.

- `NOISE` set the noise level.

- `RESONANCE_ENV` set resonance using amplitude envelope.

## SynthMonoSample

SynthMonoSample is a very basic plugin to play sample.


**Values**:

- `START` set the start position of the sample

- `END` set the end position of the sample

- `BROWSER` to browse between samples to play.

- `LOOP_POSITION` set the position of the sustain loop

- `LOOP_LENGTH` set the length of the sustain loop

- `LOOP_RELEASE` set a delay before the sustain loop ends when note off is triggered

**Config**:

- `SAMPLES_FOLDER` set samples folder path.

- `SHOW_LOOP_SUSTAIN_IN_UNIT: false` show the calculated number of loop before to finish release (default: true)

**Data ID**:

- `SAMPLE_BUFFER` return a representation of the current sample loaded in buffer

- `SAMPLE_INDEX` return the current index of the playing sample

## SynthPd

SynthPd is a plugin to play puredata patches.

Patch use midi input `notein` to trigger notes. To modulate parameters, you can either use midi cc `ctlin` or float message `r KEY_MSG`.

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/audio/SynthPd.png" />

> [!NOTE]
> - `TODO` process audio input, e.g. apply effect using PD
> - `FIXME` `apt install libpd` doesnt work on RPi. Need to embded libpd or to find a artifactory to download.

On Raspberry, libpd is not available out of the box, this is why SynthPd has been commented out from makefile. To use it, you need to install [libpd](https://github.com/libpd/libpd) manually.

On ubuntu, you can directly install it from the artifactory:
```sh
sudo apt-get install libpd-dev libpd0
```

Finally, you need to compile SynthPd:
```sh
make -C plugins/audio SynthPd
```


**Config**:

- `OPEN_PD: filename` open puredata patch.

- `ASSIGN_CC: cc label default_val` assign CC value to be sent to pd `ctlin cc`. To use value in the UI, use `CC_1`, `CC_2`, ...

- `ASSIGN_FLOAT: key label default_val` assign float value to be sent to pd `r key`. To use value in the UI, use the key as reference. So if you pd receiver is `r FREQ`, then the config is `ASSIGN_FLOAT FREQ Frequency 440` and the value key is `FREQ`.

## SynthPerc

Synth engine to generate percussion.


**Values**:

- `DURATION` controls the duration of the envelope.

- `BASE_FREQ` sets the base frequency of the percussive tone.

- `RESONATOR` controls the strength of the resonator.

- `TIMBRE` adjusts the tonal character by shaping the harmonic content.

- `BOOST` boost transient or add some distortion.

- `TONE_DECAY` adjusts the decay rate of the tonal component.

- REVERB controls delay time, feedback, and mix with one parameter.

## SynthSample

SynthSample is a multi voice sample player with a bunch of tweaking to transform a simple sample to something completely different...


**Values**:

- `START` set the start position of the sample

- `END` set the end position of the sample

- `LOOP_POSITION` set the position of the sustain loop

- `LOOP_LENGTH` set the length of the sustain loop

- `LOOP_RELEASE` set a delay before the sustain loop ends when note off is triggered

- `DENSITY` set the density of the voice. Density is adding more voice (sub voice) with a little delay on each added sub voice

- `DENSITY_DELAY` set the delay between each sub voice

- `DENSITY_RANDOMIZE` set the density randomize. If randomize is set, the density starting delay is random and while change on each sustain loop.

- `BROWSER` to browse between samples to play.

**Config**:

- `SAMPLES_FOLDER` set samples folder path.

- `VOICE_ALLOW_SAME_NOTE: false` toggle voice playing the same note. If true, same note can be played at the same time on different voices. Default is `true`.

- `BASE_NOTE: 52` set the base note. The base note is used to determine how many semitone must be added compare to the original sample. Default is `60` (middle C).

## SynthSnare

Synth engine to generate snare sounds.


**Values**:

- `DURATION` set the duration of the envelop.

- `TONE_FREQ` set the frequency of the tone.

- `HARMONICS_COUNT` set the harmonics count in the tone.

- `PINK_NOISE` set the pink noise amount.

- `NOISE_MIX` set the noise mix.

- `TRANSIENT_DURATION` set the transient duration.

- `TRANSIENT_INTENSITY` set the transient intensity.

## TapeRecording

TapeRecording plugin is used to record audio buffer for a given track.


**Values**:

- `TRACK` to set the track number.

**Config**:

- `TAPE_FOLDER` set samples folder path.

- `FILENAME: filename` to set filename. By default it is `track`.

- `MAX_FILE_SIZE: 200` to set max file size. By default it is `200MB`.

- `MAX_TRACK` to set the max track number.

**Data ID**:

- `PLAY_STOP` play or stop the recorded wavfile

- `SYNC` watch for file change and set play state

- `SAVE` save the recorded wavfile

## Tempo

Tempo audio module is responsible for clocking events. The main purpose is to send clock events to other plugins.
A good example is the sequencer.

> [!NOTE]
> - `TODO` select between internal vs midi clock


**Values**:

- `BPM` in beats per minute

**Config**:

- `BPM: 120.0` to set default beat per minute